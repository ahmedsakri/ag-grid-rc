<template>
	<div class="hello">
		<demo-wc></demo-wc>
	</div>
</template>

<script>
import { isElementLoaded, appendScript } from "../helper/utils";
export default {
	name: "HelloWorld",
	props: {
		msg: String,
	},
	created() {
    this.loadScripts();
	},
	methods: {
		loadScripts() {
      // import js file from the repositories dist folder...... ag-grid-rc/dist/demo-wc.min.js
			const scripts = [
        'https://cdn.jsdelivr.net/gh/ahmedsakri/ag-grid-rc/dist/demo-wc.min.js',
				"https://cdn.jsdelivr.net/npm/ag-grid-community@28.0.0/dist/ag-grid-community.min.js",
			];
			scripts.map((sUrl) => {
				if (!isElementLoaded("script", "src", sUrl)) {
					appendScript(sUrl);
				}
			});
		},
	},
};
</script>

<style scoped>
h3 {
	margin: 40px 0 0;
}
ul {
	list-style-type: none;
	padding: 0;
}
li {
	display: inline-block;
	margin: 0 10px;
}
a {
	color: #42b983;
}
</style>
