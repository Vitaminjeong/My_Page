<template>
	<v-container class="fill-height">
		<v-row justify="center" align="center" class="fill-height">
			<v-col cols="12" sm="6" md="8" lg="10" xl="12">
				<v-row>
					<v-text-field v-model="icon" label="icon"></v-text-field>
					<v-text-field v-model="title" label="title" class="mx-3"></v-text-field>
					<v-text-field v-model="subtitle" label="subtitle"></v-text-field>
					<v-btn depressed @click="createItem">+</v-btn>
				</v-row>
				<v-card max-width="1000" class="mx-auto elevation-10">
					<v-img src="../assets/cat.jpg" height="300px"> </v-img>
					<v-list two-line>
						<template v-for="(item, i) in items">
							<v-list-item id="about" :key="item.icon">
								<v-list-item-icon>
									<v-icon color="indigo">{{ item.icon }}</v-icon>
								</v-list-item-icon>

								<v-list-item-content>
									<v-list-item-title>{{ item.title }}</v-list-item-title>
									<v-list-item-subtitle>{{ item.subtitle }}</v-list-item-subtitle>
								</v-list-item-content>
							</v-list-item>
							<v-divider v-if="i < items.length - 1" inset :key="item.icon"></v-divider
						></template>
					</v-list>
				</v-card>
			</v-col>
		</v-row>
	</v-container>
</template>

<script>
export default {
	name: "Main",

	data: () => {
		return {
			items: [
				{ icon: "mdi-account-circle", title: "김민정", subtitle: "Name" },
				{ icon: "mdi-city", title: "명지대학교 컴퓨터공학과", subtitle: "University" },
				{ icon: "mdi-email", title: "ehfrhfo519@gmail.com", subtitle: "E-mail" },
				{ icon: "mdi-map-marker", title: "경기도 안산시", subtitle: "Home" },
			],
			icon: "",
			title: "",
			subtitle: "",
		};
	},

	methods: {
		createItem() {
			this.items.push({
				icon: this.icon,
				title: this.title,
				subtitle: this.subtitle,
			});
			this.icon = "";
			this.title = "";
			this.subtitle = "";
		},
	},
};
</script>
