<template>

<div class="menu">
    <a v-for="작명 in 메뉴들" :key="작명">{{작명}}</a>
</div>

<img alt="Vue logo" src="./assets/logo.png">
<!-- <div v-for="(qks,i) in products" :key="qks">
    <h4>{{products[i]}}</h4>
    <p>{{price[i]}} 만원</p>
</div> -->

<div>
    <h4>{{products[0]}}</h4>
    <p>{{price[0]}} 만원</p>
    <button @click="신고수[0]++">허위매물신고</button> <span>신고수 : {{신고수[0]}}</span>
</div>
<div>
    <h4>{{products[1]}}</h4>
    <p>{{price[1]}} 만원</p>
	<button @mouseover="신고수[1]++">허위매물신고</button> <span>신고수 : {{신고수[1]}}</span>
</div>
<div>
    <h4>{{products[2]}}</h4>
    <p>{{price[2]}} 만원</p>
	<button @click="신고수[2]++">허위매물신고</button> <span>신고수 : {{신고수[2]}}</span>
</div>
</template>

<script>

export default {
    name: 'App',
    data(){
        return{
		신고수 : [0,0,0],
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

.menu {
    background: darkslateblue;
    padding: 15px;
    border-radius: 5px;
}
.menu a {
    color: white;
    padding: 10px;
}
</style>
