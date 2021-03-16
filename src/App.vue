<template>
	<v-app>
		<!-- <v-card class="mx-auto overflow-hidden" height="400"> -->
		<v-app-bar color="black" dense dark app>
			<v-app-bar-nav-icon @click="drawer = true"></v-app-bar-nav-icon>
			<v-toolbar-title>Title</v-toolbar-title>
		</v-app-bar>

		<v-main>
			<v-fade-transition mode="out-in">
				<router-view> </router-view>
			</v-fade-transition>
		</v-main>

		<v-navigation-drawer v-model="drawer" absolute temporary>
			<v-list nav dense>
				<v-list-item-group v-model="group" active-class="black--text text--accent-4">
					<v-list-item @click="goMain">
						<v-list-item-icon>
							<v-icon>mdi-home</v-icon>
						</v-list-item-icon>
						<v-list-item-title>Main</v-list-item-title>
					</v-list-item>

					<v-list-item @click="goAbout">
						<v-list-item-icon>
							<v-icon>mdi-account</v-icon>
						</v-list-item-icon>
						<v-list-item-title>About</v-list-item-title>
					</v-list-item>
				</v-list-item-group>
			</v-list>
		</v-navigation-drawer>
		<!-- </v-card> -->
	</v-app>
</template>

<script>
export default {
	name: "App",

	methods: {
		goMain() {
			this.$router.push("/");
		},
		goAbout() {
			this.$router.push("/about");
		},
	},

	components: {},

	data: () => ({
		drawer: false,
	}),
};
</script>
