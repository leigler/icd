<template>
	<main>
		<ul class="main_list">
			<li>February 10 – March 23, 2020*</li>
			<li>Monday, 7:00pm – 9:30pm</li>
			<li>411 E. 9th St.</li>
			<li><br>Lukas Eigler-Harding</li>
			<li>eiglerhardingl@gmail.com</li>
			<li><small><i>*No class March 16th</i></small></li>
		</ul>

		<p v-if="loading">loading...</p>
		<p v-if="error">failed to load...</p>
		<section class="Post" v-html="post">
		</section>
	</main>
</template>

<script>
import showdown from 'showdown'


export default {
  name: 'Main',
  data: function(){
		return {
			loading: false,
			post : null,
			error : false
		}
  },
  props: {
    title: String,
    subtitle: String,
    link: Array
  },
  created () {
		this.fetchData();
	},
	methods: {
		fetchData () {
			this.loading = true;
			fetch('/sections/primary.md')
			.then((response) => { return response.text() })
			.then((textResponse) => {
				let converter = new showdown.Converter(),
						html      = converter.makeHtml(textResponse);
				this.loading = false;
				this.post = html;
			})
			.catch(() => {
				this.loading = false
				this.error = true
			})
		}
	}

}	
</script>

<style scoped>
	
	main h2{
		margin-left: 0;
	}

	.main_list{
		margin-left: 0; 
	}

	@media(max-width: 768px){
		.main_list li{
			margin-bottom: 0.25rem;
		}
	}
	

</style>