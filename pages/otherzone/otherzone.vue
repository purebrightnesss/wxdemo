<template>
  <view class="BackGrd">
   <!-- <uni-popup v-model="showPopup"> -->
         <!-- 弹出层内容 -->
    
   <view class="container">
	   <view class="allschnav">
	    <navigator url='/pages/pszone/pszone'>
		  <image class="schicon" mode="scaleToFill" src="/static/image/more.png"></image>
		 </navigator> 
		 
		 <navigator url='/pages/pszone/pszone'>
		   <image class="schicon" mode="scaleToFill" src="/static/image/search.png"></image>
		  </navigator>
		  
		  <navigator url='/pages/pszone/pszone'>
		    <image class="schicon" mode="scaleToFill" src="/static/image/message-language.png"></image>
		   </navigator>
	   </view> 
	
	<view class="Header">
	    <view class="person"><!-- <navigator url='/pages/myzone/myzone' > -->
		<image class="userAvatar" mode="scaleToFill" src="/static/image/user.png"></image>
		<!-- </navigator> -->
		
	      <text class="username">{{name}}</text>
	      <!-- <view class="education">
	        <text>{{campus}}</text>
			<br>
	        <text>{{level}}</text>
			<br>
	        <text>{{major}}</text>
	      </view> --> 
	    </view>
	<view class="header-right">
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
	
	<button type="primary" >{{ followstring }}</button>
	<!-- @click="followuser" :plain="isFollowed" -->
	</view>
	</view>

	
	<view class="commentchart">
	  <navigator v-for="item in CommentList" :url="`/pages/post_art/post_art?categorize=${item.categorize}&title=${item.title}&useravatar=${item.useravatar}&username=${item.username}&time=${item.time}&comment=${item.comment}&follow=${item.follow}&save=${item.save}`" :key="item.id" class="eachComment">
	    <view class="title">【{{ item.categorize }}】{{ item.title }}</view>
	    <view class="header">
	      <image
	        :src="item.useravatar"
	        mode="scaleToFill"
	        class="avatar"
	      />
	    <text class="name">{{ name }}</text>
	    <text class="time">{{ item.time }}</text>
	    </view>
	    <view class="comment">{{ item.comment }}</view>
	    <view class="footer">
	      <text class="follow">
	        关注: {{ item.follow }}
	      </text>
	      <text class="save">
	        评论: {{ item.save }}
	      </text>
	    </view>
	  </navigator>
	</view>
	
	
	</view>
	
   </view>  
   <!-- </uni-popup> -->
  </view>
   
</template>

<script>
	export default{
		data(){
			return {
				showPopup:true,
				name: 'tourist',
				campus:'哈尔滨工程大学',
				level:'本科生',
				major:'计算机科学与技术',
	            following:"12",
				fan:"34",
				like:"56",
				star:"78",
				isFollowed: false,
				followstring: "+ 关注",
				
				CommentList: [
				  {
				    id: 1,
				    categorize: '讨论',
				    title: "程序员最大的悲哀是什么？",
				    useravatar: "/static/image/user.png",
				    username: "、不经意间",
				    time: '2024-02-08 17:00:00',
				    comment: "公司卸磨杀驴，项目开发完就把我裁了。领导觉得，换个便宜的新人来做维护更划算。但他不知道，因...",
				    follow: 300,
				    save: 12345
				  },
				  {
				    id: 2,
				    categorize: '求助',
				    title: "女生最想收到的什么礼物？",
				    useravatar: "/static/image/user.png",
				    username: "GoodLuckHF",
				    time: '2024-02-08 17:00:00',
				    comment: "作为一个在送礼物方面得到老婆连续多年认可的人，我必须答一下这个题。熟悉我的朋友都知道，过去...",
				    follow: 99,
				    save: 59143
				  },
				  {
				    id: 3,
				    categorize: '求助',
				    title: "有没有高格调的情人节礼物推荐？",
				    useravatar: "/static/image/user.png",
				    username: "木凳先生",
				    time: '2024-02-08 17:00:00',
				    comment: "写在前面：选择什么样的礼物，才能更好的表达出心中的万千情谊，是一件十分具有技术含量的事情：不...",
				    follow: 3050,
				    save: 18660
				  },
				  {
				    id: 4,
				    categorize: '讨论',
				    title: "本科绩点会是无法洗白的污点吗？",
				    useravatar: "/static/image/user.png",
				    username: "我有一头小毛驴",
				    time: '2024-02-08 17:00:00',
				    comment: "对于我来说，如果本科绩点太高（3.8+/4.0）才会成为无法洗白的污点，因为它会在后面的日子里一直提...",
				    follow: 1999,
				    save: 9999
				  },
				  {
				    id: 5,
				    categorize: '讨论',
				    title: "学计算机不打ACM就没有出路吗？",
				    useravatar: "/static/image/user.png",
				    username: "1044失业出国",
				    time: '2024-02-08 17:00:00',
				    comment: "我的看法，ACM的这些所谓的“锻炼xx能力、提高xx能力”什么的，就是一种成功学，就和我们说某某...",
				    follow: 5560,
				    save: 502194
				  },
				],
				
			}
		}
      // methods: {
      //     followuser(){
      //         this.isFollowed = !this.isFollowed
      //         if(this.isFollowed)
      //             this.followstring = "已关注"
      //         else
      //             this.followstring = "+ 关注"
      //     }
      // }
	}
	
</script>

<style>
	.BackGrd {
	  display: flex;
	  flex-direction: column;
	  margin-top: 0%;
	  background-color:"#00E0AF";
	}
	.container {
	  display: flex;
	  flex-direction: column;
	  margin-top: 0%;
	  background-color:azure;
	}
	.allschnav{
		width: 730rpx;
		height: 50rpx;
		margin-top: 20rpx;/* 
		 display: flex;
		justify-content: flex-end;
		margin-right: 20rpx; */
	}
	.schicon{
		  width: 50rpx;
		  height: 50rpx;
		  /* margin-top: 20rpx;*/
		  float:right; 
		  margin-right: 20rpx; 
	}
	.Header{
	  margin-top: 0;
	  height: 120px;
	  width: 750rpx;
	  display: flex;
	  align-items: flex-start;
	  justify-content: left;
	}
	
	.person{
		margin-left: 20rpx;
	}
	.userAvatar{
	  width: 150rpx;
	  height: 150rpx;
	  margin-left: 15rpx;
	}
	.username {
	  font-size: 24px;
	  font-weight: bold;
	  margin-left: 25rpx;
	}
	
	.education{
	  font-size: 12px;
	  margin-bottom: 15px;
	}
	.header-right{
		display: flex;
		flex-direction: column;
	}
	.header-right button {
	    position: absolute;
	    right: 50rpx;
		top: 220rpx;
	    padding: 0;
	    font-size: 12px;
	    line-height: 55rpx;
	    width: 220rpx;
	    height: 55rpx;
	}
	.userinfo .panel{
	  margin:0 auto;
	  width: 450rpx;
	  display: flex;
	  justify-content: space-between;
	  padding: 15px 30px 10px 30px;
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
	
	.eachComment{
	  margin: 20rpx auto;
	  width: 700rpx;
	  /* height:200rpx; */
	  border-bottom: 1px solid rgba(0,0,0,0.1);
	  padding: 10rpx 10rpx 10rpx 10rpx;
	}
	.eachComment .header {
	  display: flex;
	  align-items: center;
	  vertical-align: middle;
	}
	.eachComment .title {
	  font-weight: 500;
	  font-size: 18px;
	}
	.eachComment image {
	  width: 35rpx;
	  height: 35rpx;
	}
	.eachComment .name, .eachComment .time{
	  color: rgb(163, 163, 163);
	  margin-left: 15rpx;
	  font-size: 14px;
	}
	/* .eachComment .time{ */
	/* } */
	.eachComment .comment {
	  margin-top: 15rpx;
	  overflow-wrap: break-word;
	  color: rgb(163, 163, 163);
	  font-size: 14px;
	}
	.eachComment .footer {
	  margin-top: 15rpx;
	  margin-bottom: 20rpx;
	  color: rgb(163, 163, 163);
	  font-size: 14px;
	}
	.eachComment .footer .save {
	  margin-left: 20rpx;
	}
</style>