<template>
<div>
	<Nav/>
	<div class="main">
		<h1 id="about">Survey of Climate Artists</h1>
		<hr>
		<div class="aboutText">
		<div class="aboutContent">
		<Content/>
 <i>Part of the inker-ring webring: &nbsp;&nbsp;</i><span></span> <a title="web ring" href="https://ring.inkering.com/?from=https://climateartsurvey.netlify.app/"><img class="ring" role="none" src="@theme/assets/lines.png" alt="link to webring" /></a>
    </div>
		</div>
		<hr>
		<ArtistList/>
		<hr>
		<Footer/>
	</div>
</div>
</template>

<script>
import Vue from 'vue'
// internal components
import Nav from "@theme/components/Nav";
import Footer from "@theme/components/Footer";
import ArtistList from "@theme/components/ArtistList";

export default {
		components: {
				Nav,
				Footer,
				ArtistList,
		},
		name: "Layout",
		methods: {
		},
};
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Goudy+Bookletter+1911|Lato&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Libre+Baskerville:ital,wght@0,400;0,700;1,400&display=swap');
@import url('https://fonts.googleapis.com/css2?family=IM+Fell+French+Canon&display=swap');
@import '../styles/theme.css';

.aboutText .icon.outbound {
    display: none;
}
</style>
