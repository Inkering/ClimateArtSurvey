<template>
<div class="artistLists">
	<div class="artistlist">
		<div class="artistItem" v-for="post in artists" :key="post.frontmatter.date">
			<router-link
				:to="post.path">
				<img class="artistImg" :src="post.frontmatter.img" alt="">
			</router-link>
			<router-link
				:to="post.path">
				<div>
					<div class="postDisplay"><h2 class="artistName">{{post.title}}</h2></div>
				</div>
			</router-link>
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
	/* padding: 10px; */
	/* width: 80%; */
	display: flex;
	flex-direction: row;
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
		padding-right: 10px;
}
.artistName {
		font-size: 5rem;
		line-height: 4rem;
}
.projectExcerpt {
		width: 100%;
		margin-left: 1.5rem;
}
@media all and (min-width: 1200px) {
	.projectlist {
		flex-direction: row;
		flex-wrap: wrap;
		justify-content: flex-start;
		/* align-items: baseline; */
		width: 70rem;
	}
	.projectImg {
		width: 30rem;
	}
	.projectExcerpt {
		width: 30rem;
	}
	.projectItem {
		width: 35rem;
	}
}
</style>
