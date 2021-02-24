<template>
<div class="artistLists">
	<div class="artistlist">
		<div class="artistContainer" v-for="post in artists" :key="post.frontmatter.order">
		<div class="artistItem">
			<div class="artistImgContainer">
				<router-link
					:to="post.path">
						<img class="artistImg" :src="post.frontmatter.img" alt="">
				</router-link>
				<p class="caption">{{post.frontmatter.caption}} - <a :href="post.frontmatter.link">link</a></p>
			</div>
			<router-link
				:to="post.path">
				<div>
					<div class="postDisplay"><h2 class="artistName">{{post.title}}</h2></div>
				</div>
			</router-link>
		</div>	
		</div>
	</div>
</div>
</template>

<script>
export default {
	name: "ArtistList",
	methods: {
	},
	computed: {
			artists: function () {
				return this.$site.pages
							.filter(x => x.path.startsWith("/artists/"));
			},
	}
};
</script>

<style scoped>
.artistlist {
		display: flex;
		flex-direction: column;
		margin-top: 10px;
		clear: left;
}
.artistItem {
	display: flex;
	flex-direction: row;
	text-align: left;
}
.artistContainer:nth-child(odd) > .artistItem {
	display: flex;
	flex-direction: row-reverse;
	text-align: right;
}

.artistContainer:nth-child(odd) > .artistItem > .artistImgContainer {
padding-left: 2rem;
}

.artistImgContainer {
		padding-right: 2rem;
}

.active {
		color:black;
		transition-property: color;
		transition-duration: 0.5s;
		transition-delay: 0s;
}
.artistImg {
		/* padding-top: 10px; */
		width: 100%;
}
.artistName {
		font-size: 4rem;
		line-height: 5rem;
		font-weight:400;
}
.projectExcerpt {
		width: 100%;
		margin-left: 1.5rem;
}
@media all and (max-width: 480px) {
	.artistItem {
		display: flex;
		flex-direction: column;
		text-align: left;
	}
	.artistContainer:nth-child(odd) > .artistItem {
		display: flex;
		flex-direction: column;
		text-align: left;
	}
	.artistImgContainer {
		padding-right: 0;
	}
	.artistContainer:nth-child(odd) > .artistItem > .artistImgContainer {
		padding-left: 0;
	}
}
</style>
