<template>
	<div class="s">
		<div id="clouds">
			<div class="cloud x1"></div>
			<!-- Time for multiple clouds to dance around -->
			<div class="cloud x2"></div>
			<div class="cloud x3"></div>
			<div class="cloud x4"></div>
			<div class="cloud x5"></div>
			<div class="cloud x2"></div>
			<div class="cloud x1"></div>
			<div class="cloud x3"></div>
		</div>
	</div>
    
</template>

<style scoped>
#clouds{
	padding: 100px 0;
    position: absolute;
    top: 20%;
    z-index: -1;
	
}
.s{
	overflow-x: hidden;
}

/*Time to finalise the cloud shape*/
.cloud {
	
	width: 200px; height: 60px;
	background: #fff;
	z-index: -1;
	border-radius: 200px;
	
	position: relative; 
}

.cloud:before, .cloud:after {
	content: '';
	position: absolute; 
	background: #fff;
	width: 100px; height: 80px;
	position: absolute; top: -15px; left: 10px;
	
	border-radius: 100px;
	-moz-border-radius: 100px;
	-webkit-border-radius: 100px;
	
	-webkit-transform: rotate(30deg);
	transform: rotate(30deg);
	-moz-transform: rotate(30deg);
}

.cloud:after {
	width: 120px; height: 120px;
	top: -55px; left: auto; right: 15px;
}

/*Time to animate*/
.x1 {
    animation: moveclouds 15s linear infinite;
}

/*variable speed, opacity, and position of clouds for realistic effect*/
.x2 {
	left: v-bind(window/2)+200px;
	

	transform: scale(0.6);
	opacity: 0.6; /*opacity proportional to the size*/
	
	/*Speed will also be proportional to the size and opacity*/
	/*More the speed. Less the time in 's' = seconds*/
	animation: moveclouds 25s linear infinite;
}

.x3 {
	left: v-bind(window/2)-250px; top: -200px;
	

	transform: scale(0.8);
	opacity: 0.8; /*opacity proportional to the size*/
	
	animation: moveclouds 20s linear infinite;

}

.x4 {
	left: v-bind(window/2)+470px; top: -250px;
	
	transform: scale(0.75);
	opacity: 0.75; /*opacity proportional to the size*/
	
	animation: moveclouds 18s linear infinite;

}

.x5 {
	left: v-bind(window/2)-150px; top: -150px;
	
	-webkit-transform: scale(0.8);
	-moz-transform: scale(0.8);
	transform: scale(0.8);
	opacity: 0.8; /*opacity proportional to the size*/
	
	animation: moveclouds 22s linear infinite;
}

@keyframes moveclouds {
	0% {margin-left: v-bind(width);}
	100% {margin-left: -1000px;}
}

</style>

<script>
    export default {
        name:'CloudsBg',
		data(){
			return{
				width:'',
				window:this.innerWidth
			}
		},
		methods: {
			resizeHandler() {
				this.window = window.innerWidth
				this.width = ''
				this.width += this.window-230 + 'px'
			}
		},
		mounted(){
			this.window = window.innerWidth
			this.width += this.window-230 + 'px'
			window.addEventListener("resize",  this.resizeHandler);
		}
    }
</script>