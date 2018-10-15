<template>
<div class="headerview">
	<h1>
		{{msg}}
	</h1>
</div>
</template>

<script>
	export default{
		data(){
			return {
				title: "我是標題部份…"
			}
		},
		//第一步: props
		props: {	//可以是數組或對象，用於接收來自父組件的數據
				msg: {	//自定義屬性
					type: String,
					default: "我是誰？"
				}
		}
	}
</script>

<style>

</style>