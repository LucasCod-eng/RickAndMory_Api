<script setup>
import { onMounted, reactive, ref } from 'vue';
import { RouterLink } from 'vue-router';

let character = reactive(ref());

onMounted(() => {
	fetch("https://rickandmortyapi.com/api/character").then(res => { res.json().then((x) => { character = x.results; console.log(character); }) })
})

</script>

<template>
	<div class="container texte-center">
		<div class="row">
			<div class="row col-12">
				<div v-for="c in character" class="col-6 d-flex justify-content-center">
					<div class="col-sm-12 col-md-6">
						<div class="card">
							<div class="card-body row">
								<div class=" "><strong>{{ c.name }}</strong></div>
								<img :src="c.image" >
								<div>
									<p class="mt-4"> <strong>Espécie:</strong> {{ c.species }}</p>
									<p class="mt-4"> <strong>Gênero:</strong> {{ c.gender }}</p>
									<p class="mt-4"><strong>Status:</strong> {{ c.status }}</p>


								</div>
								<RouterLink to="/">
									<button class="btn btn-dark">Info Skills</button>
								</RouterLink>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

