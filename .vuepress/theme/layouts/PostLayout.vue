<template>
  <div>
		<Nav/>
		<div class="main">
			<h1 id="about">Survey of Climate Artists</h1>
			<hr>
			<router-link to="/"><p>Back</p></router-link>
			<hr>
			<div class="artist-title">
					<h2 class="pageTitle p-name">{{$page.frontmatter.title}}</h2>
					<div class="artistImgContainer">
						<img class="artistImg" :src="$page.frontmatter.img" alt="">
						<p class="caption">{{$page.frontmatter.caption}} - <a :href="$page.frontmatter.link">link</a></p>
						<hr class="cursed-line">
						<article class="h-entry">
							<Content/>
						</article>
					</div>
				</div>
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

<style scoped> 
@import url('https://fonts.googleapis.com/css?family=Goudy+Bookletter+1911|Lato&display=swap');
@import url('https://fonts.googleapis.com/css2?family=IM+Fell+French+Canon&display=swap');
@import '../styles/theme.css';

article {
	float: right;
	text-align: left;
}
.pageTitle {
	padding-bottom: 1rem;
	padding-right: 2rem;
}
.artist-title {
	display: flex;
	flex-direction: row;
	text-align: right;
}
.artistImgContainer {
	max-width: 70rem;
	padding-left: 5px;
}
.artistImg {
	max-width: 100%;
}

@media all and (max-width: 750px) {
	.artist-title {
	display: flex;
	flex-direction: column;
	text-align: left;
	}
	.artistImgContainer {
		padding-right: 0;
		padding-left: 0;
	}
}
</style>