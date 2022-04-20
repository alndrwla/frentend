<template>
  <v-app>
    <h1 class="title">Rick and Morty</h1>
			<button class="btn" @click="getData">Search data</button>
    <v-main>
			<section class="main-container">
				<div class="cards-container">
					<Character
					v-for="character in characters"
					:key="character.id"
					:character="character"/>
				</div>
			</section>
    </v-main>
  </v-app>
</template>

<script>
import axios from 'axios'
import Character from './components/Character.vue'

function data() {
	return {
		characters: [],
	}
}

function created() {
	this.getData()
}

function getData() {
	axios.get('https://rickandmortyapi.com/api/character/')
	.then((response) =>{
		this.characters = response.data.results;
	})
	.catch(function (error) {
		console.log(error)
	})
}

export default {

  name: 'App',
	created,
	data,
	methods: {
		getData,
	},
  components: {
		Character,
  },
};
</script>


<style scoped>
:root {
	--white: #FFFFFF;
	--black: #000000;
	--very-light-pink: #C7C7C7;
	--text-input-field: #F7F7F7;
	--hospital-green: #ACD9B2;
	--sm: 14px;
	--md: 16px;
	--lg: 18px;
}

body {
	margin: 0;
	font-family: 'Quicksand', sans-serif;
}

.title {
	text-align: center;
}

.btn {
	background-color: #ACD9B2;
	margin: 15px auto;
	padding: 10px;
	color: #FFFFFF;
	border-radius: 10px;
}

.cards-container {
	display: grid;
	grid-template-columns: repeat(auto-fill, 240px);
	gap: 26px;
	place-content: center;
}
</style>
