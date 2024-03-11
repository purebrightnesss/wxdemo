<template>
		<view>
			   <view style="width: 90%; margin: 200rpx auto;">
				  <view style="margin-bottom: 70rpx; font-size: 60rpx; color:#00B386; text-align: center;">登录</view>
				  
				  <uni-forms ref="form" :modelValue="form" :rules="rules">
				   
					<uni-forms-item name="username">
				     <uni-easyinput v-model="form.username" prefixIcon="person" placeholder="请输入登录用户名" ></uni-easyinput>
		 	        </uni-forms-item>
				   
				   <uni-forms-item name="password">
				      <uni-easyinput type="password" v-model="form.password" prefixIcon="locked" placeholder="请输入登录密码" ></uni-easyinput>
				   </uni-forms-item>
				  </uni-forms>
				   
				   <view style="margin: 40rpx 0;">
					   <button type="primary" @click="login">登录</button>
				   </view>
				   
				<view  style=" flexDirection: 'row', align-items: center; justify-content: center;width:200rpx ;margin-left: 280rpx;">    
				 <!-- alignItems: 'center',display: flex;  -->
				 <view>
					 <navigator url='/pages/register/register'>注册</navigator>  
				 </view>
				 <view>
				    <navigator url='/pages/secret/secret'>忘记密码？</navigator>
				 </view>
			  
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
								// 对name字段进行必填验证
								username: {
									rules: [{required: true,errorMessage: '请输入用户名'}],
									validateTrigger:'submit'
								},
								password:{
									rules: [{required: true,errorMessage: '请输入密码'}],
									validateTrigger:'submit '
								},
							}
			}
		},
		methods: {
			login(){
					this.$refs.form.validate().then(res=>{
						console.log('表单数据信息：', res);
					}).catch(err =>{
						console.log('表单错误信息：', err);
					})
				
				
				console.log(this.form)
				const baseUrl = "https://api.watercuckoo.top"
				uni.request({
					url:baseUrl + '/user/login',
					method:'POST',
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
								title:'登录成功',
								duration: 2000
							})
							uni.setStorageSync('user',data.data)
							uni.switchTab({
								url:'/pages/bio/bio'
							})
						}
				}
				})
			}
		}
	}
</script>

<style>
</style>