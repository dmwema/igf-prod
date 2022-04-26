<template>

	<!-- Layout Header ( Navbar ) -->
	<a-layout-header>
		<div class="header-col header-brand">
			<h6>Muse Dashboard PRO</h6>

			<!-- Trigger Button For Navigation Menu For Small Screens -->
			<a-button type="link" @click="collapseNav = collapseNav ? 0 : 1 " class="btn-menu-trigger">
				<svg width="20" height="20" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="M16 132h416c8.837 0 16-7.163 16-16V76c0-8.837-7.163-16-16-16H16C7.163 60 0 67.163 0 76v40c0 8.837 7.163 16 16 16zm0 160h416c8.837 0 16-7.163 16-16v-40c0-8.837-7.163-16-16-16H16c-8.837 0-16 7.163-16 16v40c0 8.837 7.163 16 16 16zm0 160h416c8.837 0 16-7.163 16-16v-40c0-8.837-7.163-16-16-16H16c-8.837 0-16 7.163-16 16v40c0 8.837 7.163 16 16 16z"/></svg>
			</a-button>
			<!-- Trigger Button For Navigation Menu For Small Screens -->

		</div>
		<div class="header-col header-nav">

			<!-- Navigation Menu For Large Screens -->
			<a-menu mode="horizontal" class="menu-large">
				<a-sub-menu>
					<span slot="title" class="submenu-title-wrapper">
						<a-icon type="dashboard" theme="filled" class="m-0" />
						<span>Dashboards</span>
					</span>
					<a-menu-item>
						<router-link to="/dashboards/" class="nav-link">
							<span>Default</span>
						</router-link>
					</a-menu-item>
					<a-menu-item>
						<router-link to="/dashboards/crm/" class="nav-link">
							<span>CRM</span>
						</router-link>
					</a-menu-item>
				</a-sub-menu>
				<a-sub-menu>
					<span slot="title" class="submenu-title-wrapper">
						<a-icon type="code" theme="filled" class="m-0" />
						<span>Pages</span>
					</span>
					<a-sub-menu>
						<span slot="title" class="submenu-title-wrapper">
							<span>Profile</span>
						</span>
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
					</a-sub-menu>
					<a-sub-menu>
						<span slot="title" class="submenu-title-wrapper">
							<span>Account</span>
						</span>
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
					</a-sub-menu>
					<a-sub-menu>
						<span slot="title" class="submenu-title-wrapper">
							<span>Users</span>
						</span>
						<a-menu-item>
							<router-link to="/pages/users/new-user">
								<span class="label">New User</span>
							</router-link>
						</a-menu-item>
					</a-sub-menu>
					<a-sub-menu>
						<span slot="title" class="submenu-title-wrapper">
							<span>Projects</span>
						</span>
						<a-menu-item>
							<router-link to="/pages/projects/timeline">
								<span class="label">Timeline</span>
							</router-link>
						</a-menu-item>
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
				</a-sub-menu>
				<a-sub-menu>
					<span slot="title" class="submenu-title-wrapper">
						<a-icon type="appstore" theme="filled" class="m-0" />
						<span>Applications</span>
					</span>
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
				</a-sub-menu>
				<a-sub-menu>
					<span slot="title" class="submenu-title-wrapper">
						<a-icon type="dollar-circle" theme="filled" class="m-0" />
						<span>Ecommerce</span>
					</span>
					<a-sub-menu>
						<span slot="title" class="submenu-title-wrapper">
							<span>Products</span>
						</span>
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
					</a-sub-menu>
					<a-sub-menu>
						<span slot="title" class="submenu-title-wrapper">
							<span>Orders</span>
						</span>
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
					</a-sub-menu>
				</a-sub-menu>
				<a-sub-menu>
					<span slot="title" class="submenu-title-wrapper">
						<a-icon type="lock" theme="filled" class="m-0" />
						<span>Authentication</span>
					</span>
					<a-sub-menu>
						<span slot="title" class="submenu-title-wrapper">
							<span>Sign Up</span>
						</span>
						<a-menu-item>
							<router-link to="/authentication/sign-up/basic">
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
					</a-sub-menu>
				</a-sub-menu>
			</a-menu>
			<!-- / Navigation Menu For Large Screens -->

			<!-- Collapsible Navigation Menu For Small Screens -->
			<div class="menu-small">
				
				<!-- Collapsible Component For Navigation Menu For Small Screens -->
				<a-collapse v-model="collapseNav" accordion>
					<a-collapse-panel key="1">

						
						<a-menu mode="inline"
							:open-keys="openKeys"
							@openChange="onOpenChange"
						>
							<a-sub-menu key="dashboards" style="padding: 0;">
								<span slot="title">
									<span class="icon">
										<a-icon type="dashboard" theme="filled" class="m-0" />
									</span>
									<span class="label">Dashboards</span>
								</span>
								<a-menu-item-group>
									<a-menu-item>
										<router-link to="/dashboards/">
											<span class="label">Default</span>
										</router-link>
									</a-menu-item>
									<a-menu-item>
										<router-link to="/dashboards/crm">
											<span class="label">CRM</span>
										</router-link>
									</a-menu-item>
								</a-menu-item-group>
							</a-sub-menu>
							<a-menu-item class="menu-item-header">
								Pages
							</a-menu-item>
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
												<router-link to="/authentication/sign-up/basic">
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
							<a-sub-menu key="basic" style="padding: 0;">
								<span slot="title">
									<span class="icon">
										<a-icon type="read" theme="filled" class="m-0" />
									</span>
									<span class="label">Basic</span>
								</span>
								<a-menu-item-group>
									<a-menu-item>
										<router-link to="/docs/basic/links-to-the-Docs">
											<span class="label">links to the Docs</span>
										</router-link>
									</a-menu-item>
								</a-menu-item-group>
							</a-sub-menu>
							<a-sub-menu key="components" style="padding: 0;">
								<span slot="title">
									<span class="icon">
										<a-icon type="rocket" theme="filled" class="m-0" />
									</span>
									<span class="label">Components</span>
								</span>
								<a-menu-item-group>
									<a-menu-item>
										<router-link to="/docs/components/links-to-the-Docs">
											<span class="label">links to the Docs</span>
										</router-link>
									</a-menu-item>
								</a-menu-item-group>
							</a-sub-menu>
							<a-menu-item>
								<a href="https://github.com/creativetimofficial/ct-muse-vue-ant-design-dashboard-pro/blob/main/CHANGELOG.md" target="_blank">
									<span class="icon">
										<a-icon type="switcher" theme="filled" class="m-0" />
									</span>
									<span class="label">Changelog</span>
								</a>
							</a-menu-item>
						</a-menu>
						<!-- / Navigation Menu For Small Screens -->

					</a-collapse-panel>
				</a-collapse>
				<!-- / Collapsible Component For Navigation Menu For Small Screens -->

			</div>
			<!-- / Collapsible Navigation Menu For Small Screens -->

		</div>
		<div class="header-col header-btn">
			<a-button size="small" type="dark" class="px-30 border-dark" shape="round" href="https://www.creative-tim.com/product/muse-vue-ant-design-dashboard-pro" target="_blank">BUY NOW</a-button>
		</div>
	</a-layout-header>
	<!-- / Layout Header ( Navbar ) -->

</template>

<script>

	export default ({
		data() {
			return {
				// Collapse navigation value.
				// Binded model property for "Collapsible Navigation Menu" collapsed status .
				collapseNav: 0,
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
      			rootSubmenuKeys: ['dashboards', 'pages', 'applications', 'ecommerce', 'authentication', 'basic', 'components', 'changelog'],
				openKeys: null,
			}
		},
		methods: {
			onOpenChange(openKeys)
			{
				this.openKeys = this.openKeys ? this.openKeys : this.$route.meta.sidebarMap ;
				
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

<style lang="scss" scoped>

	.nav-link svg {
		margin-right: 5px;
		vertical-align: middle;
	}
	.nav-link span {
		vertical-align: middle;
	}
	.ant-menu-submenu-popup {
		width: 100%;
	}

</style>