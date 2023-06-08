<style>
.v-toolbar-title{
    text-align: -webkit-center;
}
</style>
<template>
	<v-app-bar>
		<v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
		<v-toolbar-title>{{applicationName}}</v-toolbar-title>
	</v-app-bar>
	<v-navigation-drawer v-model="drawer" temporary>
		<v-list>
				<div v-for="item in redirectitems">
					<v-list-item :prepend-icon="item.icon" :title="item.title" @click="redirect(item.path)"></v-list-item>
				</div>
		</v-list>
	</v-navigation-drawer>
</template>
<script>
export default {
	props: ['title'],
	name: 'AppBar',
	data: () => ({
		drawer: false,
        applicationName: null,
		redirectitems: [
			{title: 'Accueil', icon: 'mdi-home', path: "/"},
            {title: 'test', icon: 'mdi-phone', path: "/test"}
		],
	}),
    created(){
        this.applicationName = process.env.VUE_APP_APPLICATION_NAME
    },
	methods: {
		redirect(path) {
			this.$router.push(path)
		}
	}
}
</script>
