<template>
	<div class="view">
		<h1 class="title">
			{{title}}
		</h1>		
		<ul>
			<li v-for="item in items" v-bind:class="{finish:item.isFinished}">
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
				{
					text: "今天晚上18:00跑步",
				isFinished: false
				},
				{
					text: "今天早餐",
					isFinished: true
				}
			]
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