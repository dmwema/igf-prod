<template>
	
	<!-- Main Sidebar -->
	<a-layout-sider
		collapsible
		class="sider-primary"
		breakpoint="lg"
		collapsed-width="0"
		width="250px"
		:collapsed="sidebarCollapsed"
		@collapse="$emit('toggleSidebar', ! sidebarCollapsed)"
		:trigger="null"
		:class="['ant-layout-sider-' + sidebarColor, 'ant-layout-sider-' + sidebarTheme]"
		theme="light"
		:style="{ backgroundColor: 'transparent',}">
			<div class="brand"><img src="images/logo-ct-black.png" alt=""> <span>Fac Pharmacie</span></div>
			<hr>

			<!-- Sidebar Navigation Menu -->
			<a-menu theme="light" mode="inline"
      			:open-keys="openKeys"
				@openChange="onOpenChange">
				<a-menu-item>
					<router-link to="/dashboards/">

					<a href="#" style="padding-left:0">
						<span class="icon">
							<a-icon type="read" theme="filled" class="m-0" />
						</span>
						<span class="label">Tableau de bord</span>
					</a>
					</router-link>
				</a-menu-item>
				
				<a-menu-item>
					<router-link to="/t/courses">

					<a href="#" style="padding-left:0">
						<span class="icon">
							<a-icon type="read" theme="filled" class="m-0" />
						</span>
						<span class="label">Cours</span>
					</a>
					</router-link>
				</a-menu-item>

				<a-menu-item>
					<router-link to="/t/epreuves">

					<a href="#" style="padding-left:0">
						<span class="icon">
							<a-icon type="read" theme="filled" class="m-0" />
						</span>
						<span class="label">Épreuves</span>
					</a>
					</router-link>
				</a-menu-item>

				<a-sub-menu key="applications" style="padding: 0;">
					<span slot="title">
						<span class="icon">
							<a-icon type="appstore" theme="filled" class="m-0" />
						</span>
						<span class="label">Gérer les cotes</span>
					</span>
					<a-menu-item-group>
						<a-menu-item>
							<router-link to="/t/c/mathematiques">
								<span class="label">G1 Informatique</span>
							</router-link>
						</a-menu-item>
						<a-menu-item>
							<router-link to="#">
								<span class="label">G2 Informatique</span>
							</router-link>
						</a-menu-item>
						</a-menu-item-group>
				</a-sub-menu>
				
				<!--
				<a-sub-menu key="pages" style="padding: 0;">
					<span slot="title">
						<span class="icon">
							<a-icon type="code" theme="filled" class="m-0" />
						</span>
						<span class="label">Pages</span>
					</span>
					<a-menu-item-group>
						<a-sub-menu key="profile" style="padding: 0;" title="Profile">
							<a-menu-item-group>
								<a-menu-item>
									<router-link to="/pages/profile/profile-overview">
										<span class="label">Profile Overview</span>
									</router-link>
								</a-menu-item>
								<a-menu-item>
									<router-link to="/pages/profile/all-projects">
										<span class="label">All Projects</span>
									</router-link>
								</a-menu-item>
							</a-menu-item-group>
						</a-sub-menu>
						<a-sub-menu key="users" style="padding: 0;" title="Users">
							<a-menu-item-group>
								<a-menu-item>
									<router-link to="/pages/users/new-user">
										<span class="label">New User</span>
									</router-link>
								</a-menu-item>
							</a-menu-item-group>
						</a-sub-menu>
						<a-sub-menu key="account" style="padding: 0;" title="Account">
							<a-menu-item-group>
								<a-menu-item>
									<router-link to="/pages/account/settings">
										<span class="label">Settings</span>
									</router-link>
								</a-menu-item>
								<a-menu-item>
									<router-link to="/pages/account/billing">
										<span class="label">Billing</span>
									</router-link>
								</a-menu-item>
								<a-menu-item>
									<router-link to="/pages/account/invoice">
										<span class="label">Invoice</span>
									</router-link>
								</a-menu-item>
							</a-menu-item-group>
						</a-sub-menu>
						<a-sub-menu key="projects" style="padding: 0;" title="Projects">
							<a-menu-item-group>
								<a-menu-item>
									<router-link to="/pages/projects/timeline">
										<span class="label">Timeline</span>
									</router-link>
								</a-menu-item>
							</a-menu-item-group>
						</a-sub-menu>
						<a-menu-item>
							<router-link to="/pages/pricing">
								<span class="label">Pricing</span>
							</router-link>
						</a-menu-item>
						<a-menu-item>
							<router-link to="/pages/rtl">
								<span class="label">RTL</span>
							</router-link>
						</a-menu-item>
						<a-menu-item>
							<router-link to="/pages/charts">
								<span class="label">Charts</span>
							</router-link>
						</a-menu-item>
						<a-menu-item>
							<router-link to="/pages/alerts">
								<span class="label">Alerts</span>
							</router-link>
						</a-menu-item>
						<a-menu-item>
							<router-link to="/pages/notifications">
								<span class="label">Notifications</span>
							</router-link>
						</a-menu-item>
					</a-menu-item-group>
				</a-sub-menu>
				<a-sub-menu key="applications" style="padding: 0;">
					<span slot="title">
						<span class="icon">
							<a-icon type="appstore" theme="filled" class="m-0" />
						</span>
						<span class="label">Applications</span>
					</span>
					<a-menu-item-group>
						<a-menu-item>
							<router-link to="/applications/kanban">
								<span class="label">Kanban</span>
							</router-link>
						</a-menu-item>
						<a-menu-item>
							<router-link to="/applications/wizard">
								<span class="label">Wizard</span>
							</router-link>
						</a-menu-item>
						<a-menu-item>
							<router-link to="/applications/datatables">
								<span class="label">DataTables</span>
							</router-link>
						</a-menu-item>
						<a-menu-item>
							<router-link to="/applications/calendar">
								<span class="label">Calendar</span>
							</router-link>
						</a-menu-item>
					</a-menu-item-group>
				</a-sub-menu>
				<a-sub-menu key="ecommerce" style="padding: 0;">
					<span slot="title">
						<span class="icon">
							<a-icon type="dollar-circle" theme="filled" class="m-0" />
						</span>
						<span class="label">Ecommerce</span>
					</span>
					<a-menu-item-group>
						<a-sub-menu key="products" style="padding: 0;" title="Products">
							<a-menu-item-group>
								<a-menu-item>
									<router-link to="/ecommerce/products/new-product">
										<span class="label">New Product</span>
									</router-link>
								</a-menu-item>
								<a-menu-item>
									<router-link to="/ecommerce/products/edit-product">
										<span class="label">Edit Product</span>
									</router-link>
								</a-menu-item>
								<a-menu-item>
									<router-link to="/ecommerce/products/product-page">
										<span class="label">Product Page</span>
									</router-link>
								</a-menu-item>
							</a-menu-item-group>
						</a-sub-menu>
						<a-sub-menu key="orders" style="padding: 0;" title="Orders">
							<a-menu-item-group>
								<a-menu-item>
									<router-link to="/ecommerce/orders/orders-list">
										<span class="label">Order List</span>
									</router-link>
								</a-menu-item>
								<a-menu-item>
									<router-link to="/ecommerce/orders/orders-details">
										<span class="label">Order Details</span>
									</router-link>
								</a-menu-item>
							</a-menu-item-group>
						</a-sub-menu>
					</a-menu-item-group>
				</a-sub-menu>
				<a-sub-menu key="authentication" style="padding: 0;">
					<span slot="title">
						<span class="icon">
							<a-icon type="lock" theme="filled" class="m-0" />
						</span>
						<span class="label">Authentication</span>
					</span>
					<a-menu-item-group>
						<a-sub-menu key="sign-up" style="padding: 0;" title="Sign Up">
							<a-menu-item-group>
								<a-menu-item>
									<router-link to="/sign-up">
										<span class="label">Basic</span>
									</router-link>
								</a-menu-item>
								<a-menu-item>
									<router-link to="/authentication/sign-up/cover">
										<span class="label">Cover</span>
									</router-link>
								</a-menu-item>
								<a-menu-item>
									<router-link to="/authentication/sign-up/illustration">
										<span class="label">Illustration</span>
									</router-link>
								</a-menu-item>
							</a-menu-item-group>
						</a-sub-menu>
					</a-menu-item-group>
				</a-sub-menu>
				<a-menu-item class="menu-item-header">
					<hr class="mt-5">
					Docs
				</a-menu-item>
				<a-menu-item>
					<a href="https://demos.creative-tim.com/muse-vue-ant-design-dashboard-pro/documentation/overview" target="_blank">
						<span class="icon">
							<a-icon type="read" theme="filled" class="m-0" />
						</span>
						<span class="label">Getting Started</span>
					</a>
				</a-menu-item>
				<a-menu-item>
					<a href="https://demos.creative-tim.com/muse-vue-ant-design-dashboard-pro/documentation/components/alert" target="_blank">
						<span class="icon">
							<a-icon type="rocket" theme="filled" class="m-0" />
						</span>
						<span class="label">Components</span>
					</a>
				</a-menu-item>
				<a-menu-item>
					<a href="https://github.com/creativetimofficial/ct-muse-vue-ant-design-dashboard-pro/blob/main/CHANGELOG.md" target="_blank">
						<span class="icon">
							<a-icon type="switcher" theme="filled" class="m-0" />
						</span>
						<span class="label">Changelog</span>
					</a>
				</a-menu-item>-->
			</a-menu>
			<!-- / Sidebar Navigation Menu -->

			<!-- Sidebar Footer -->
			<div class="aside-footer">
				<div class="footer-box">
					<span class="icon">
						<svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
							<path d="M3 4C3 3.44772 3.44772 3 4 3H16C16.5523 3 17 3.44772 17 4V6C17 6.55228 16.5523 7 16 7H4C3.44772 7 3 6.55228 3 6V4Z" fill="#111827"/>
							<path d="M3 10C3 9.44771 3.44772 9 4 9H10C10.5523 9 11 9.44771 11 10V16C11 16.5523 10.5523 17 10 17H4C3.44772 17 3 16.5523 3 16V10Z" fill="#111827"/>
							<path d="M14 9C13.4477 9 13 9.44771 13 10V16C13 16.5523 13.4477 17 14 17H16C16.5523 17 17 16.5523 17 16V10C17 9.44771 16.5523 9 16 9H14Z" fill="#111827"/>
						</svg>
					</span>
					<h6>Besoin d'aide ?</h6>
					<p>Veuillez contacter le support technique</p>
					<a-button block size="small" href="#" target="_blank">
						SUPPORT
					</a-button>
				</div>
			</div>
			<!-- / Sidebar Footer -->

	</a-layout-sider>
	<!-- / Main Sidebar -->

</template>

<script>

	export default ({
		props: {
			// Sidebar collapsed status.
			sidebarCollapsed: {
				type: Boolean,
				default: false,
			},
			
			// Main sidebar color.
			sidebarColor: {
				type: String,
				default: "primary",
			},
			
			// Main sidebar theme : light, white, dark.
			sidebarTheme: {
				type: String,
				default: "light",
			},
		},
		data() {
			return {
      			rootSubmenuKeys: ['dashboards', 'pages', 'applications', 'ecommerce', 'authentication', 'basic', 'components', 'changelog'],
				openKeys: this.$route.meta.sidebarMap,
			}
		},
		methods: {
			onOpenChange(openKeys)
			{
				const latestOpenKey = openKeys.find( key => this.openKeys.indexOf( key ) === -1) ;

				if ( this.rootSubmenuKeys.indexOf( latestOpenKey ) === -1 )
				{
					this.openKeys = openKeys;
				}
				else
				{
					this.openKeys = latestOpenKey ? [ latestOpenKey ] : [] ;
				}
			},
		},
	})

</script>
