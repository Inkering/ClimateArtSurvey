<template>
  <div>
		<Nav/>
		<div class="main">
			<h1 id="about">Survey of Climate Artists</h1>
			<router-link to="/"><p>Back</p></router-link>
			<hr>
			<article class="h-entry">
					<img class="artistImg" :src="$page.frontmatter.img" alt="">
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