<template>
	<div>
		<div>
			<h1>Todos</h1>
			<div class="todos">
				<div v-for="todo in allTodos" 
				class="todo" 
				v-bind:key="todo.key">
					{{todo.title}}

					<button v-on:click="deleteTodo(todo.id)">Delete</button>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
import {mapGetters, mapActions} from 'vuex'

export default {
name: "Todos",
methods: {
	...mapActions(["fetchTodos", "deleteTodo"])
},
computed: mapGetters(["allTodos"]),
created(){
	this.fetchTodos()
}
}
</script>

<style scoped>

</style>