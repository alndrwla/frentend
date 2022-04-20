<template>
	<div class="character-card">
	<img
		:src="character.image"
		alt="Image">
	<div class="character-info">
		<div>
			<p>{{character.name}}</p>
			<p>{{character.status}}</p>
		</div>
	</div>
</div>

</template>

<script>

export default {
	name: 'character-card',
	props: ['character'],
}

</script>


<style scoped>

.character-card {
	width: 240px;
}

.character-card img {
	width: 240px;
	height: 240px;
	border-radius: 20px;
	object-fit: cover;
}

.character-info {
	display: flex;
	justify-content: space-between;
	align-items: center;
	margin-top: 12px;
}

.character-info div p:nth-child(1) {
	font-weight: bold;
	font-size: var(--md);
	margin-top: 0;
	margin-bottom: 4px;
	color: var(--very-light-pink);
}

.character-info div p:nth-child(2) {
	font-size: var(--sm);
	margin-top: 0;
	margin-bottom: 0;
}

.character-info figure {
	margin: 0;
}
.character-info figure img {
	width: 35px;
	height: 35px;
}
@media (max-width: 640px) {
	.cards-container {
		display: grid;
		grid-template-columns: repeat(auto-fill, 140px);
		gap: 26px;
	}

	.character-card {
		width: 140px;
	}

	.character-card img {
		width: 140px;
		height: 140px;
	}
}

</style>
