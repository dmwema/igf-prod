<!-- 
	This is the DataTables page, it uses the dashboard layout in: 
	"./layouts/Dashboard.vue" .
 -->

<template>

	<div>

		<!-- Searchable Datatable card -->
		<a-card :bordered="false" class="header-solid mb-24" :bodyStyle="{padding: 0, paddingTop: '16px'}">
			<template #title>
				<h5 class="font-semibold">Toutes les Épreuves</h5>
			</template>

			<div class="mx-25">
				<a-row type="flex" :gutter="24">
					<a-col :span="24" :md="12">
						<a-select v-model="pageSize2" @change="onPageSize2Change" style="width: 70px">
							<a-select-option value="5">5</a-select-option>
							<a-select-option value="10">10</a-select-option>
							<a-select-option value="15">15</a-select-option>
							<a-select-option value="20">20</a-select-option>
							<a-select-option value="25">25</a-select-option>
						</a-select>
						<label for="" class="ml-10">entries per page</label>
					</a-col>
					<a-col :span="24" :md="12" class="text-right">
    					<a-input-search placeholder="input search text" style="max-width: 200px;" v-model="query" @change="onSearchChange" />
					</a-col>
				</a-row>
			</div>
			
			<a-table class="mt-20" :columns="columns2" :data-source="data2" :pagination="{pageSize: pageSize2,}" />
		</a-card>
		<!-- / Searchable Datatable card -->
		
	</div>

</template>

<script>

	// Second table's list of columns.
	const columns2 = [
		{
			title: '#',
			dataIndex: 'id',
			sorter: (a, b) => a.id.length - b.id.length,
			sortDirections: ['descend', 'ascend'],
		},
		{
			title: 'INTITULÉ',
			dataIndex: 'name',
			sorter: (a, b) => a.name.length - b.name.length,
			sortDirections: ['descend', 'ascend'],
		},
		{
			title: 'TYPE',
			dataIndex: 'type',
			sortDirections: ['descend', 'ascend'],
			sorter: (a, b) => a.type.length - b.type.length,
		},
		{
			title: 'DATE',
			dataIndex: 'startDate',
			sorter: (a, b) => a.startDate.length - b.startDate.length,
			sortDirections: ['descend', 'ascend'],
		},
		{
			title: 'MAX',
			dataIndex: 'max',
			sorter: (a, b) => a.max.length - b.max.length,
			sortDirections: ['descend', 'ascend'],
		},
	];
	
	// Second table's list of rows.
	const data2 = [
		{
			key: 1,
			id: 1,
			name: "Prémière interrogation",
			type: "Intérrogation",
			startDate: "2022/04/25",
			max: 20
		},
		{
			key: 2,
			id: 2,
			name: "Exposé sur les chatbots",
			type: "Exposé",
			startDate: "2022/04/25",
			max: 50
		},
		{
			key: 3,
			id: 3,
			name: "Examen première session",
			type: "Examen",
			startDate: "2022/04/25",
			max: 20
		},
	] ;

	export default {
		components: {
		},
		data() {
			return {

				// Second table's list of columns.
				columns2,
	
				// Second table's list of rows.
				data2,

				// First table's number of rows per page.
				pageSize: 10,

				// Second table's number of rows per page.
				pageSize2: 10,
				
				// Second table's search query.
				query: '',

			}
		},
		methods: {

			// Event handler for first table's size change.
			onPageSizeChange() {
				this.pageSize = parseInt( this.pageSize ) ;
			},

			// Event handler for second table's size change.
			onPageSize2Change() {
				this.pageSize2 = parseInt( this.pageSize2 ) ;
			},

			// Event handler for second table's search.
			onSearchChange() {
				if( this.query.length > 0 ) {
					this.data2 = data2.filter( (row) => {
						for( const key in row ) {
							if( row[ key ]
								.toString()
								.toLowerCase()
								.includes( this.query.trim().toLowerCase() ) )
								return true;
						}
						return false;
					}) ;
				}
				else {
					this.data2 = data2 ;
				}
			},
			
		},
	}

</script>

<style lang="scss">
</style>