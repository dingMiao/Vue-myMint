<template>
		<div class="footer">
		 <nav class="bottombar">
			<router-link  to="/Zhuye"  exact tag="li">
 					<span class="icon icon-home"></span>
 				 <p class="home_text">主页</p>
 			</router-link>
		    <router-link  to="Find" tag="li">
				<span class="icon icon-find"></span>
			 	<p class="home_text">发现时尚</p>
		  </router-link>
		  <router-link  to="Personal" tag="li" :to="isLogin">
				<span class="icon icon-info"></span>
			 	<p class="home_text">我的</p>
		  </router-link>
		  <!-- <router-link  :to="isLogin" tag="li">
		  				<span class="icon icon-info"></span>
		  			 	<p class="home_text">我的</p>
		  </router-link> -->
		</nav>
	</div>

</template>
<script>
export default{
	computed: {
		isLogin(){
			console.log('登录')
			if(this.$store.state.check === false){
				return '/Login'
		   }else{
				return  '/Personal'
				}
		}	
	}
}
</script>

<style scoped>
	.footer{
		position: fixed;
		left: 0;
		right: 0;
		bottom: 0;
		width: 100%;
		height: 50px;
		z-index: 10;
		font-size:0.4rem;
		border-top: 2px solid #f1f1f1;
	}
	.bottombar{
	  width: 100%;
		height: 50px;
	  display: flex;
		padding-top: 5px;
	  background-color: #f6f6f6;
	}
	.bottombar li{
		flex: 1;
		height: 55px;
	  list-style: none;
	}
	.icon {
	  display:block;
	  width: 100%;
		height: 30px;
		margin: 0;
		padding: 0;
	}
	.icon-home{
		background: url('../../assets/img/tabbar/zhuye_gray.png') no-repeat;
	  background-position: center center;
	}
	.icon-find{
	 background: url('../../assets/img/tabbar/find_gray.png') no-repeat;
	  background-position: center center;
	}
	.icon-info{
		background: url('../../assets/img/tabbar/me_gray.png') no-repeat;
	  background-position: center center;
	}
	.router-link-active .icon-home {
	  background: url('../../assets/img/tabbar/zhuye_orange.png')no-repeat;
	  background-position: center center;
	}
	.router-link-active .icon-find {
	  background: url('../../assets/img/tabbar/find_orange.png')no-repeat;
	  background-position: center center;
	}
	.router-link-active .icon-info {
	  background: url('../../assets/img/tabbar/me_orange.png')no-repeat;
		  background-position: center center;
	}
	 p {
		text-align: center;
	}
	.router-link-active .home_text{
	  color: #fb8a2e;
		text-align: center;
		font-size:0.4rem;
	}
</style>