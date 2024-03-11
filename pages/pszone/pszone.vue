<template>
   <view class="container">
	
	<view class="List">
		
			<navigator url='/pages/pszone/psin/psin'  class="List-item">
				<view class="Ltitle">头像</view>
				<image src="../../static/image/user.png" class="Licon"></image>
				<view class="Lnav">></view>
			</navigator> 
			
		    <navigator url='/pages/pszone/psin/psin'  class="List-item">
		    	<view class="Ltitle">名字</view>
				<view class="Lname">tourist</view>
		    	<view class="Lnav">></view>
		    </navigator> 
			
			<navigator url='/pages/pszone/psin/psin'  class="List-item">
				<view class="Ltitle">账号</view>
				<view class="Lname">yangly</view>
				<view class="Lnav">></view>
			</navigator> 
			
			<navigator url='/pages/pszone/psin/psin'  class="List-item">
				<view class="Ltitle">手机号</view>
				<view class="Lname">173***84</view>
				<view class="Lnav">></view>
			</navigator> 
			
			<navigator url='/pages/pszone/psin/psin'  class="List-item">
				<view class="Ltitle">密码</view>
				<view class="Lname">12***</view>
				<view class="Lnav">></view>
			</navigator> 
			
			<navigator url='/pages/pszone/psin/psin'  class="List-item">
				<view class="Ltitle">我的地址</view>
				<view class="Lname">黑龙江 哈尔滨</view>
				<view class="Lnav">></view>
			</navigator> 
		
	  <!-- <navigator v-for="item in Tools" :url="`/pages/pszone/${item.addr}`" open-type="navigate" :key="item.id" class="Tool">
	    <view class="title">{{ item.title }}</view>
		<view class="Tnav">></view>
	  </navigator> -->
	  </view>
	
	
	  
   </view>  
</template>

<script>
	export default{
		data(){
			return {
			}
		},
	
	// onLoad() {
	// 	this.signup()
	// },
	methods: {
		
		// signup(){
		// 	uni.request({
		// 		url:"https://api.watercuckoo.top/user/signup",
		// 		method:'PUT',
		// 		data: {
		// 		     "username": "yk",
		// 		        "password": "test123",
		// 		        "avatar": "http://dummyimage.com/100x100",
		// 		        "name": "yk",
		// 		        "phone": "12345678901",
		// 		        "email": "123456@qq.com",
		// 		        "career": "在读学生",
		// 		        "qualification": "本科",
		// 		        "graduate": "哈尔滨工程大学",
		// 		        "workplace": "无"
		// 		  },
		// 	    success:res=>{
		// 		console.log(res)
		// 	}
		// 	})
			
		// }
	}
}
</script>

<style>
	.container {
	  display: flex;
	  flex-direction: column;
	}
	
	.List {
	  /* background-color: sienna; */
	  margin: 15px auto;
	  padding: 12px;
	  width: 315px;
	  border: 1px solid #3f3f3f83;
	  border-radius: 10px;
	}
	.List-item {
		display: flex;
		/* justify-content: space-between; */
	  margin: 20rpx auto;
	  margin-top: 20rpx;
	  width: 300px;
	  height: 50rpx;
	  /* border-bottom: 1px solid rgba(0,0,0,0.1); */
	  padding: 10rpx 10rpx 10rpx 10rpx;
	}
    .Ltitle {
	  font-weight: 500;
	  font-size: 18px;
	}
    .Lnav {
      width: 20rpx;
      position: absolute;
      right: 100rpx;
    }
	
	.Lname {
	  color: rgb(163, 163, 163);
	  position: absolute;
	  right: 130rpx;
	}
	.Licon {
		width: 25px;
		height: 25px;
	 position: absolute;
	 right: 130rpx;	
	}
</style>