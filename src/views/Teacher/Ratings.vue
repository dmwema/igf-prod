<!-- 
	This is the DataTables page, it uses the dashboard layout in: 
	"./layouts/Dashboard.vue" .
 -->

<template>

	<div>
        <a-tabs default-active-key="1" @change="callback">
            <a-tab-pane key="1" tab="Mathématique">
               <a-button type="primary" icon="search" @click="showModal">
                ENREGISTRER UNE COTE
                </a-button>
                <br>
                <br>
                <!-- Searchable Datatable card -->
                <a-card :bordered="false" class="header-solid mb-24" :bodyStyle="{padding: 0, paddingTop: '16px'}">
                    <template #title>
                        <h5 class="font-semibold">Première Intérrogation / <small>20 Juillet 20222</small></h5>
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
            </a-tab-pane>
            <a-tab-pane key="2" tab="Informatique" force-render>
                Content of Tab Pane 2
            </a-tab-pane>
            <a-tab-pane key="3" tab="Bilogie Animale">
                Content of Tab Pane 3
            </a-tab-pane>
        </a-tabs>
        
        <a-modal v-model="visible" title="Basic Modal" @ok="handleOk">
            ici un formulaire
        </a-modal>
		
	</div>

</template>

<script>

	// Second table's list of columns.
	const columns2 = [
		{
			title: '#',
			dataIndex: 'id',
			sorter: (a, b) => a.id - b.id,
			sortDirections: ['descend', 'ascend'],
		},
		{
			title: 'ETUDIANT',
			dataIndex: 'name',
			sorter: (a, b) => a.name.length - b.name.length,
			sortDirections: ['descend', 'ascend'],
		},
		{
			title: 'MAX / 20',
			dataIndex: 'ponderation',
			sortDirections: ['descend', 'ascend'],
			sorter: (a, b) => a.ponderation - b.ponderation,
		}
	];
	
	// Second table's list of rows.
	const data2 = [
		{
			key: 1,
			id: 1,
			name: "Jhon Doe",
			ponderation: 4,
		},
		{
			key: 2,
			id: 2,
			name: "Jhon Doe",
			ponderation: 6,
		}
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