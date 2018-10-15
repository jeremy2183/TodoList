<template>
	<div class="view">
		<h1 class="title">
			{{title}}
		</h1>		
		<input v-model="newStr" @keyup.enter="addData">
		<ul>
			<li v-for="item in items" v-bind:class="{finish:item.isFinished}" @click="toggleFinish(item)">
				{{item.text}}
			</li>
		</ul>
	</div>
</template>

<script>
//new Vue()
export default{
	name: "List",
	// data: function(){  ES5
	// 	return {}
	// }
	data(){  //ES6
		return{
			title: "TodoList",
			items: [				//待辦事項
				// {
				// 	text: "今天晚上18:00跑步",
				// isFinished: false
				// },
				// {
				// 	text: "今天早餐",
				// 	isFinished: true
				// }
			],
			newStr: ''
		}
	},
	methods: {
		toggleFinish: function(item){
			//改變狀態
			// console.log(1);
			item.isFinished = !item.isFinished;
		},
		addData: function(){
			// console.log(this.newStr);
			this.items.push({
				text: this.newStr,
				isFinished: false
			});

			//將輸入框中輸入 傳遞給 父組件 App
			//觸發myMsg事件並且傳遞參數
			this.$emit('myMsg',this.newStr);

			//清空輸入框內容
			this.newStr = '';
		}
	}
}
</script>

<style>
	.view{
		width: 400px;
		border: 1px solid gray;
		margin: 20px auto;
	}
	.view .title{
		border-bottom: 1px solid gray;
	}
	.view ul li{
		margin: 10px 0;
		list-style: none;
	}
	.view .finish{
		color: gray;
		text-decoration: line-through;
	}
</style>