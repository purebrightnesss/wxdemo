<template>
		<view>
			   <view style="width: 90%; margin: 200rpx auto;">
				 
				  <uni-forms ref="form" :modelValue="form" :rules="rules">
				   
				   <uni-forms-item name="email">
				   		<uni-easyinput v-model="form.email" prefixIcon="email" placeholder="请输入邮箱" />
				   	</uni-forms-item>
				   
				  </uni-forms>
				   
				   <view style="margin: 40rpx 0;">
					   <button type="primary" @click="register">注册</button>
				   </view>
				   
				
			   </view>
			  
		  <!-- <button class="logbutton" hover-class="is-hover" @click="setIsShow()">登录</button> -->
		  
		</view> 
</template>

<script>
	export default {
		data() {
			return {
				form:{},
				rules: {
								// 对email字段进行必填验证
								email: {
									rules: [{
																required: true,
																errorMessage: '请输入邮箱'
															}, {
																format: 'email',
																errorMessage: '请输入正确格式的邮箱'
															}],
									validateTrigger:'submit'
								}
							}
			}
		},
		methods: {
			// console.log(this.form)
			register(){
					this.$refs.form.validate().then(res=>{
						
				const baseUrl = "https://api.watercuckoo.top"
				uni.request({
					url:baseUrl + '/user/signup',
					method:'PUT',
					data: this.form,
				    success:(res)=>{
						const data = res.data
						if (data.code =='0'){
							uni.showToast({
								icon:"none",
								title:data.msg
							})
						}else{
							uni.showToast({
								title:'验证成功',
								duration:2000
							})
							//跳转页面
							uni.navigateTo({
								url:'/pages/login/login'
							})
						}
				}
				})
						console.log('表单数据信息：', res);
					}).catch(err =>{
						console.log('表单错误信息：', err);
					})
			}
		}
	}
</script>

<style>
</style>
