<template>

<div class="black-bg" v-if="모달창 == true">
	<div class="white-bg">
		<h4>상세페이지</h4>
		<p>상세페이지 내용</p>
		<button @click="모달창 = false">닫기</button>
	</div>
</div>



<div class="menu">
    <a v-for="작명 in 메뉴들" :key="작명" href="">{{작명}}</a>
</div>

<!-- <img alt="Vue logo" src="./assets/logo.png"> -->
<!-- <div v-for="(qks,i) in products" :key="qks">
    <h4>{{products[i]}}</h4>
    <p>{{price[i]}} 만원</p>
</div> -->

<!-- <div>
	<img src="./assets/room0.jpg" class="room-img">
    <h4 @click="모달창 = true">{{products[0]}}</h4>
    <p>{{price[0]}} 만원</p>
    <button @click="신고수[0]++">허위매물신고</button> <span>신고수 : {{신고수[0]}}</span>
</div>
<div>
	<img src="./assets/room1.jpg" class="room-img">
    <h4>{{products[1]}}</h4>
    <p>{{price[1]}} 만원</p>
	<button @click="신고수[1]++">허위매물신고</button> <span>신고수 : {{신고수[1]}}</span>
</div>
<div>
	<img src="./assets/room2.jpg" class="room-img">
    <h4>{{products[2]}}</h4>
    <p>{{price[2]}} 만원</p>
	<button @click="신고수[2]++">허위매물신고</button> <span>신고수 : {{신고수[2]}}</span>
</div> -->
<div v-for="(roof,i) in 원룸들" :key="roof">
	<img :src="원룸들[i].image" class="room-img">
    <h4 @click="모달창 = true">{{원룸들[i].title}}</h4>
    <p>{{원룸들[i].price}} 만원</p>
    <button @click="신고수[i]++">허위매물신고</button> <span>신고수 : {{신고수[i]}}</span>
</div>
</template>

<script>
import data from './assets/oneroom.js'
data;


export default {
    name: 'App',
    data(){
        return{
			원룸들 : data,
			모달창 : false, 	
			신고수 : [0,0,0,0,0,0],
			price : [50,60,70],
			products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
			메뉴들 : ['Home', 'Shop', 'About']
        }
    },
	methods : {
		increase(){
			this.신고수++;
		}
	},
    components: {
    }
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
}

a {
	text-decoration: none;
}
.menu {
    background: darkslateblue;
    padding: 15px;
    border-radius: 5px;
}
.menu a {
    color: white;
    padding: 10px;
}
.room-img {
	width: 70%;
	margin-top: 40px;
}


body {
	margin: 0;
}
div {
	box-sizing: border-box;
}
.black-bg {
	width: 100%;
	height: 100%;
	background: rgba(0, 0, 0, 0.5);
	position: fixed;
	padding: 20px;
}
.white-bg {
	width: 100%;
	background: white;
	border-radius: 8px;
	padding: 20px;
}
</style>
