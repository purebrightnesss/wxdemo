<template>
   <view class="container">
	<view class="header">
	    <navigator url='/pages/myzone/myzone' >
			<image class="userAvatar" mode="scaleToFill" src="/static/image/user.png"></image>
		</navigator>
		<view>
	      <text class="username">{{name}}</text>
	      <view class="education">
	        <text style="display: block;">{{campus}}</text>
	        <text>{{level}}</text>
			<br>
	        <text>{{major}}</text>
	      </view>    
	    </view>
	</view>
	
	<view class="userinfo">
	    <view class="panel">
	     
		  <view class="panel-item">
	        <text class="number">{{following}}</text>
			<navigator url='/pages/pszone/pszone' >关注</navigator> 
		  </view>
		  
	      <view class="panel-item">
	        <text class="number">{{fan}}</text>
	        <navigator url='/pages/pszone/pszone' >粉丝</navigator>
	      </view>
		  
	      <view class="panel-item">
	        <text class="number">{{like}}</text>
	        <navigator url='/pages/pszone/pszone' >获赞</navigator>
	      </view>
		  
	      <view class="panel-item">
	        <text class="number">{{star}}</text>
	        <navigator url='/pages/pszone/pszone' >收藏</navigator>
	      </view>
	    </view>
	</view>
	
	<view class="commentchart">
	
	<navigator url='/pages/pszone/pszone'  class="Tool">
		<image src="../../static/image/customer.png" class="Ticon"></image><view class="title">个人信息</view>
		<view class="Tnav">></view>
	</navigator> 
	
	<navigator url='/pages/pszone/pszone'  class="Tool">
		<image src="../../static/image/customer.png" class="Ticon"></image><view class="title">历史记录</view>
		<view class="Tnav">></view>
	</navigator> 
	
	<navigator url='/pages/pszone/pszone'  class="Tool">
		<image src="../../static/image/edit.png" class="Ticon"></image><view class="title">系统设置</view>
		<view class="Tnav">></view>
	</navigator> 
	
	<navigator url='/pages/pszone/pszone'  class="Tool">
		<image src="../../static/image/info.png" class="Ticon"></image><view class="title">关于</view>
		<view class="Tnav">></view>
	</navigator> 
	
	<navigator url='/pages/pszone/pszone'  class="Tool">
		<image src="../../static/image/quit.png" class="Ticon"></image><view class="title">退出登录</view>
		<view class="Tnav">></view>
	</navigator> 
	
	 <!-- <navigator v-for="item in Tools" :url="`/pages/pszone/${item.addr}`" open-type="navigate" :key="item.id" class="Tool">
	    <image src="../../static/image/customer.png" class="Ticon"></image><view class="title">{{ item.title }}</view>
		<view class="Tnav">></view>
	  </navigator> -->
	  </view>
	
	
	  
   </view>  
</template>

<script>
	export default{
		data(){
			return {
				name: 'tourist',
				campus:'哈尔滨工程大学',
				level:'本科生',
				major:'计算机科学与技术',
	            following:"12",
				fan:"34",
				like:"56",
				star:"78",
				
				
				// Tools: [
				//     {id: 1,addr:"pszone", img:'customer',title: "个人信息"},
				//     {id: 2,addr:"pszone", img:'customer',title: "历史记录"},
				//     {id: 3,addr:"pszone", img:'customer',title: "系统设置"},
				//     {id: 4,addr:"pszone", img:'customer',title: "关于" },
				//     {id: 5,addr:"pszone", img:'customer',title: "退出登录"},
				// ]
			}
		}
	}
	
</script>

<style>
	.container {
	  display: flex;
	  flex-direction: column;
	}
	
	/* .box {
	  margin-bottom: 10px;
	} */
	
	.header{
	  margin-top: 20px;
	  height: 120px;
	  display: flex;
	  align-items: center;
	  justify-content: center;
	}
	
	.userAvatar{
	  width: 200rpx;
	  height: 200rpx;
	  margin-bottom: 10rpx;
	  margin-right: 15rpx;
	}
	.username {
	  font-size: 24px;
	  font-weight: bold;
	}
	
	.education{
	  font-size: 12px;
	  margin-bottom: 15px;
	}
	
	
	.commentchart {
	  /* background-color: sienna; */
	  margin: 15px auto;
	  padding: 12px;
	  width: 315px;
	  border: 1px solid #3f3f3f83;
	  border-radius: 10px;
	}
	.Tool {
		display: flex;
		/* justify-content: space-between; */
	  margin: 20rpx auto;
	  margin-top: 20rpx;
	  width: 300px;
	  height: 50rpx;
	  /* border-bottom: 1px solid rgba(0,0,0,0.1); */
	  padding: 10rpx 10rpx 10rpx 10rpx;
	}
	.Ticon{
	  justify-content: left;
	  width: 25px;
	  height: 25px;
	  margin-right: 10rpx;
	  /* background-color: pink; */
	}

    .Tnav {
      width: 20px;
      position: absolute;
      right: 100rpx;
    }
    /* .commentchart{
      margin: 0 auto;
      width: 280px;
      display: flex;
      justify-content: space-between;
      padding: 10px 30px 10px 30px;
      border: 1px solid #3f3f3f83;
      border-radius: 10px;
    } */
	.title {
	  font-weight: 500;
	  font-size: 18px;
	}
	
	.userinfo .panel{
	  margin: 0 auto;
	  width: 280px;
	  display: flex;
	  justify-content: space-between;
	  padding: 10px 30px 10px 30px;
	  border: 1px solid #3f3f3f83;
	  border-radius: 10px;
	}
	.userinfo .panel .panel-item{
	  display: flex;
	  justify-content: center;
	  align-items: center;
	  flex-direction: column;
	}
	.userinfo .panel .panel-item .number{
	  font-size: 20px;
	  margin-bottom: 5px;
	}
	
	
</style>