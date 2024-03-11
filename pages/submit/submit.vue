<template>	
	<view>
			<view class="mysubmit">
				<form @submit="formSubmit" @reset="formReset">
					
					<!-- 输入 -->
					<view class="uni-form-item uni-column">
						<!-- <view class="title">input</view> -->
						<input class="uni-input" name="input" placeholder="请输入标题,4~20字,精确描述您的需求" />
					    <div class="solid-line"></div>
						<textarea class="textarea" v-model="textareaValue" maxlength="300" placeholder="详细描述您的需求,300字内"></textarea>
					</view>
					
					 <!-- 单选 -->
					<!-- <view class="uni-form-item uni-column">
						<view class="title">radio</view>
						<radio-group name="radio">
							<label>
								<radio value="radio1" /><text>选项一</text>
							</label>
							<label>
								<radio value="radio2" /><text>选项二</text>
							</label>
						</radio-group>
					</view> -->
					
					<view class="uni-form-item uni-column">
						<view class="title">选择栏目</view>
						<checkbox-group name="checkbox">
							<label>
								<checkbox value="checkbox1" /><text>讨论</text>
							</label>
							<label>
								<checkbox value="checkbox2" /><text>求助</text>
							</label>
						</checkbox-group>
					</view>
					
					<!-- 允许评论 -->
					<view class="uni-form-item uni-column">
						<view class="title">此贴不接受评论</view>
						<switch name="switch" />
					</view>
					<!-- 下部按钮 -->
					<view class="uni-btn-v">
						<button type="primary" style=" width:300rpx" form-type="submit">发布</button>
						<button style="margin-top: 20rpx; width:300rpx" type="default" form-type="reset">重置</button>
					</view>
				</form>
			</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				textareaValue: ''
			}
		},
		methods: {
						formSubmit: function(e) {
							console.log('form发生了submit事件，携带数据为：' + JSON.stringify(e.detail.value))
							var formdata = e.detail.value
							uni.showModal({
								// content: '表单数据内容：' + JSON.stringify(formdata),
								 content: '发布成功！' ,
								showCancel: false
							});
						},
						formReset: function(e) {
							console.log('清空数据')
						}
		}
	}
</script>

<style>
	.mysubmit{
		margin: 15rpx auto;
		/* padding: 12rpx; */
		width: 700rpx;
	}
	
    .uni-form-item  {
    		padding: 30rpx 0;
    	}
	.uni-form-item .title{
		font-size: 20px;
	}
	.solid-line {
		  border: 1px solid #3f3f3f83; /* 设置边框为1px实线，颜色为黑色 */
		  width: 700rpx; /* 设置元素的宽度 */
		  height: 1px; /* 设置元素的高度 */
		}
	.uni-input{
			width: 700rpx;
			height: 70rpx;
		}
	.textarea{
		    margin-top: 20rpx;
			width: 700rpx;
			height: 400rpx;
		}
</style>
