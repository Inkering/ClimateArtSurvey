<template>
<div class="artistLists">
	<div class="artistlist">
		<div v-for="post in artists" :key="post.frontmatter.order">
		<div v-if="post.frontmatter.direction === 'left'">
			<div class="artistItemRev">
				<div class="artistImgContainerRev">
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
		<div v-else>
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
	text-align: left;
}
.artistItemRev {
	display: flex;
	flex-direction: row-reverse;
	text-align: right;
}
.artistImgContainer {
		padding-right: 2rem;
}
.artistImgContainerRev {
		padding-left: 2rem;
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
@media all and (min-width: 1200px) {
	.artistlist {
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
