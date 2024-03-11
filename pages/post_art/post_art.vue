<template>
<view>
  <view class="postdetail">
    <view class="title">{{ categorize }} {{ title }}</view>
    <view class="header">
        <navigator url='/pages/otherzone/otherzone' >
		  <image
		      :src="useravatar"
		      mode="scaleToFill"
			  class="avatar"
		  />
		</navigator>
        <view>
            <text class="name">{{ username }}</text>
            <br>
            <text class="time">{{ time }}</text>
        </view>
		
        <button type="primary" @click="followuser" :plain="isFollowed">{{ followstring }}</button>
		
      </view>
      <view class="article">
        <rich-text :nodes="articleContent"></rich-text>
      </view>
      <view class="time">编辑于 {{ time }}</view>
      <view class="options">
        <image
            src="/static/img/up-btn.png"
            mode="scaleToFill"
        />
      </view>
  </view>
  
  <view style="background-color:#00B386;
	  height: 80rpx;
	  padding:0 10px;
	  display: flex;
	  justify-content: flex-start;
	  position: sticky;
	  bottom:0;">
	  <button style=" 
	   font-size: 18px;
	  line-height: 65rpx;
	  height: 70rpx;
	  background-color: #ffffff;
	  border-radius: 20px;
	  width:70%; margin-top: 5rpx; margin-left: 10rpx;" @click="open" >评论</button>
  <uni-popup ref="popup" type="dialog">
  	<uni-popup-dialog title="评论" placeholder="发表我的见解~" mode="input" message="成功消息" :duration="2000" :before-close="true" @close="close" @confirm="confirm"></uni-popup-dialog>
  </uni-popup>
  <image style="width: 70rpx;
	  height: 70rpx;
	  margin-top: 3rpx ;" mode="scaleToFill" src="/static/image/good.png"></image>
  <image style="width: 70rpx;
	  height: 70rpx;
	  margin-top: 3rpx; margin-left: 10rpx" mode="scaleToFill" src="/static/image/star.png"></image>
  	</view>
  
  
  
  </view>
</template>

<script>
export default {
    data() {
        return {
            categorize: "",
            title: "",
            useravatar: "",
            username: "",
            time: '',
            comment: "",
            follow: new Number,
            save: new Number,
            isFollowed: false,
            followstring: "+ 关注",
            articleContent: `<p>臣密言：臣以险衅，夙遭闵凶。生孩六月，慈父见背；行年四岁，舅夺母志。祖母刘愍臣孤弱，躬亲抚养。臣少多疾病，九岁不行，零丁孤苦，至于成立。既无伯叔，终鲜兄弟，门衰祚薄，晚有儿息。外无期功强近之亲，内无应门五尺之僮，茕茕孑立，形影相吊。而刘夙婴疾病，常在床蓐，臣侍汤药，未曾废离。</p>
            <p>逮奉圣朝，沐浴清化。前太守臣逵察臣孝廉，后刺史臣荣举臣秀才。臣以供养无主，辞不赴命。诏书特下，拜臣郎中，寻蒙国恩，除臣洗马。猥以微贱，当侍东宫，非臣陨首所能上报。臣具以表闻，辞不就职。诏书切峻，责臣逋慢。郡县逼迫，催臣上道；州司临门，急于星火。臣欲奉诏奔驰，则刘病日笃；欲苟顺私情，则告诉不许：臣之进退，实为狼狈。</p>
            <p>伏惟圣朝以孝治天下，凡在故老，犹蒙矜育，况臣孤苦，特为尤甚。且臣少仕伪朝，历职郎署，本图宦达，不矜名节。今臣亡国贱俘，至微至陋，过蒙拔擢，宠命优渥，岂敢盘桓，有所希冀。但以刘日薄西山，气息奄奄，人命危浅，朝不虑夕。臣无祖母，无以至今日；祖母无臣，无以终余年。母、孙二人，更相为命，是以区区不能废远。</p>
            <p>臣密今年四十有四，祖母今年九十有六，是臣尽节于陛下之日长，报养刘之日短也。乌鸟私情，愿乞终养。臣之辛苦，非独蜀之人士及二州牧伯所见明知，皇天后土实所共鉴。愿陛下矜悯愚诚，听臣微志，庶刘侥幸，保卒余年。臣生当陨首，死当结草。臣不胜犬马怖惧之情，谨拜表以闻。</p>`
        }
    },
    onLoad(options) {
		this.getPost()
        this.categorize = options.categorize
        this.title = options.title
        this.useravatar = options.useravatar
        this.username = options.username
        this.time = options.time
        this.comment = options.comment
        this.follow = options.follow
        this.save = options.save
    },
    methods: {
        followuser(){
            this.isFollowed = !this.isFollowed
            if(this.isFollowed)
                this.followstring = "已关注"
            else
                this.followstring = "+ 关注"
        },
		
		//获取详细页贴文
		getPost(){
			uni.request({
				url:"https://api.watercuckoo.top/post/{1}",
			    success:res=>{
				console.log(res)
			}
			})
			
		},
		
		open() {
					this.$refs.popup.open()
				},
				/**
				 * 点击取消按钮触发
				 * @param {Object} done
				 */
				close() {
					// TODO 做一些其他的事情，before-close 为true的情况下，手动执行 close 才会关闭对话框
					// ...
					this.$refs.popup.close()
				},
				/**
				 * 点击确认按钮触发
				 * @param {Object} done
				 * @param {Object} value
				 */
				confirm(value) {
					// 输入框的值
					console.log(value)
					// TODO 做一些其他的事情，手动执行 close 才会关闭对话框
					// ...
					this.$refs.popup.close()
				}
		
    }
}
</script>

<style scoped>
    .postdetail {
        margin: 50rpx auto;
        width: 700rpx;
    }
    .postdetail .title{
        font-size: 22px;
        font-weight: 500;
    }
    .postdetail .header {
        display: flex;
        align-items: center;
        vertical-align: middle;
        margin-top: 30rpx;
        position: relative;
    }
    .postdetail .header image {
        width: 80rpx;
        height: 80rpx;
    }
    .postdetail .header .name, .postdetail .header .time {
        color: rgb(126, 126, 126);
        margin-left: 15rpx;
        font-size: 14px;
    }
    .postdetail .header button {
        position: absolute;
        right: 10rpx;
        padding: 0;
        font-size: 12px;
        line-height: 55rpx;
        width: 120rpx;
        height: 55rpx;
    }
    .article {
        margin-top: 30rpx;
        text-indent: 2em;
        line-height: 50rpx;
    }
    .time {
        margin: 20rpx;
        font-size: 14px;
        color: rgb(163, 163, 163);
    }
    .options image{
        width: 50rpx;
        height: 50rpx;
    }

		
</style>