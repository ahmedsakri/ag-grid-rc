<template>
	<div>
		<ag-grid-vue
			style="height: 500px"
			class="ag-theme-alpine"
			:columnDefs="columnDefs"
			:rowData="rowData"
		>
		</ag-grid-vue>
	</div>
</template>
<script>
import { AgGridVue } from "ag-grid-vue";
export default {
	components: {
		AgGridVue,
	},
	data() {
		return {
			columnDefs: [
				{ headerName: "Make", field: "make" },
				{ headerName: "Model", field: "model" },
				{ headerName: "Price", field: "price" },
			],
			rowData: [
				{ make: "Toyota", model: "Celica", price: 35000 },
				{ make: "Ford", model: "Mondeo", price: 32000 },
				{ make: "Porsche", model: "Boxster", price: 72000 },
			],
		};
	},
};
</script>
<style lang="scss">
@import "~ag-grid-community/styles/ag-grid.css";
@import "~ag-grid-community/styles/ag-theme-alpine.css";
</style>
