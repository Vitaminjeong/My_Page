<template>
	<div class="main">
		<v-main>
			<!-- <HelloWorld /> -->
			<MyPage />
		</v-main>
	</div>
</template>

<script>
// @ is an alias to /src
import MyPage from "@/components/MyPage.vue";

export default {
	name: "Main",
	components: {
		MyPage,
	},
};
</script>
