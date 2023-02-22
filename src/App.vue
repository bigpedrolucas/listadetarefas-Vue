<template>
	<div id="app">
		<div class="bubbles">
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
			<div class="bubble"></div>
		</div>
		<div class="row box shadow p-3 mb-5 bg-body-tertiary rounded">
			<BarraProgresso :progressWidth="progressWidth"></BarraProgresso>
			<div class="cell-12 mt-4">
				<div class="input-group mb-3">
					<input 
						v-model="title" 
						type="text"
						class="form-control" 
						placeholder="Digite a sua tarefa"
						aria-label="Recipient's username" 
						aria-describedby="button-addon2"
					>
					<button 
						@click="addItem"
						class="btn btn-outline-primary" 
						type="button" id="button-addon2"
					>Adicionar</button>
				</div>
			</div>
			<ListaTarefas :list="list" @onDeleteItem="deleteItem"></ListaTarefas>
		</div>
	</div>
</template>

<script>

import BarraProgresso from './components/BarraProgresso.vue'
import ListaTarefas from './components/ListaTarefas.vue'

export default {
	components: { ListaTarefas, BarraProgresso },
	data () {
		return {
			title: '',
			list: [],
		}
	},
	computed: {
		progressWidth() {
			let listSize = this.list.length
			let doneItems = this.list.filter(el => el.done === true).length
			let progressBarWidth = (listSize === 0) ? 0 : Math.round(doneItems / listSize * 100)
			return progressBarWidth
		}
	},
	methods: {
		addItem() {
			this.list.push({title: this.title, done: false}) 
			this.title = ''
		},
		deleteItem(index) {
			this.list.splice(index, 1)
		}
	}
}
</script>


<style>
@import './background.css';

#app {
	display: flex;
	flex: 1;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	height: 100vh;
	width: 100vw;
}

#app h1 {
	margin-bottom: 5px;
	font-weight: 300;
	font-size: 3rem;
}

.progress-bar {
	position: relative;
}

.box {
	display: flex;
	flex-direction: column;
	min-width: 500px;
	min-height: 500px;
	background-color: #ffffff;
	position: absolute;
}
</style>
