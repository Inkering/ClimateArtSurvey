<template>
  <div>
			<Nav/>
			<div class="main">
					<router-link to="/"><h1 class="article-home">Back</h1></router-link>
					<article class="h-entry">
							<h2 class="pageTitle p-name">{{$page.frontmatter.title}}</h2>
							<Content/>
					</article>
			</div>
			<Footer/>

  </div>
</template>

<script>
import Nav from "@theme/components/Nav";
import Footer from "@theme/components/Footer";

export default {
		components: {
				Nav,
				Footer,
		},
		name: "Layout",
		methods: {
		},
};
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Goudy+Bookletter+1911|Lato&display=swap');
@import url('https://fonts.googleapis.com/css2?family=IM+Fell+French+Canon&display=swap');
@import '../styles/theme.css';
</style>