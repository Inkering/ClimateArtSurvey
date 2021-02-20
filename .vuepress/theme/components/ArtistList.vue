<template>
<div class="artistLists">
	<div class="artistlist">
		<template>
			<div class="artistItem" v-for="post in artists" :key="post.frontmatter.date">
				<router-link
						:to="post.path">
						<img class="artistImg" :src="post.frontmatter.img" alt="">
				</router-link>
				<router-link
						:to="post.path">
						<div>
							<div class="postDisplay"><h3>{{post.title}}</h3></div>
						</div>
				</router-link>
			</div>
		</template>
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

.project-btn {
		float: left;
		margin: 0;
		margin-right: 5px;
		margin-bottom: 10px;
		color: grey;
}
.projectlist {
		display: flex;
		flex-direction: column;
		margin-top: 10px;
		clear: left;
}
.projectItem {
	padding: 10px;
	width: 80%;
}
.active {
		color:black;
		transition-property: color;
		transition-duration: 0.5s;
		transition-delay: 0s;
}
.artistImg {
		padding-top: 10px;
		width: 100%;
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
