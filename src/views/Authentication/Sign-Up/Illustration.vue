
<template>
	<div class="sign-in">
		
		<a-row type="flex" :gutter="[24,24]" justify="space-around" align="middle" class="row-main">

			<!-- Sign Up Form Column -->
			<a-col :span="24" :md="{ span: 14, offset: 2 }" :lg="10" :xl="6" class="col-form mr-auto">
				<h4 class="mb-15">Se connecter</h4>
				<p class="text-muted">Entrez le code de connexion pour se connecter</p>

				<!-- Sign Up Form -->
				<a-form
					id="components-form-demo-normal-login"
					:form="form"
					class="login-form"
					@submit="handleSubmit"
					:hideRequiredMark="true"
				>
					<a-form-item class="mb-10" label="Entrez le code secret" :colon="false">
						<a-input 
						v-decorator="[
						'code',
						{ rules: [{ required: true, message: 'Veuillez entrer le code secret' }] },
						]" placeholder="Code secret" />
					</a-form-item>
					
					</a-form-item>
					<a-form-item>
						<router-link to="/sign-up/edit-credentials" class="font-bold text-dark">
							<a-button type="primary" block html-type="submit" class="login-form-button">
							SUIVANT
							</a-button>
						</router-link>
							
					</a-form-item>
				</a-form>
				<!-- / Sign Up Form -->

			<p class="font-semibold text-muted text-center">Vous n'avez pas réçu de code secret ou vous l'avez perdu ? <router-link to="/sign-in" class="font-bold text-dark">(Re)demandez-les</router-link></p>
			</a-col>
			<!-- / Sign Up Form Column -->

			<!-- Sign Up Image Column -->
			<a-col :span="24" :md="12" :lg="12" :xl="12" class="col-img">
				<div>
					<div class="img">
						<img src="images/info-rocket-ill.png" alt="rocket">
					</div>
					<h4 class="text-white">Bienvenue Professeur <br><b>Daniel MWEMA</b></h4>
					<p class="text-white">Utilisez le code réçu <b> du decanat</b> pour vous connecter et gérer tout ce qui vous concerne en rapport avec la faculté</p>
				</div>
			</a-col>
			<!-- / Sign Up Image Column -->

		</a-row>
		
	</div>
</template>

<script>

	export default ({
		data() {
			return {
				// Sign up form object.
				form: this.$form.createForm(this, { name: 'signup_illustration' }),
			}
		},
		methods: {
			// Handles input validation after submission.
			handleSubmit(e) {
				e.preventDefault();
				this.form.validateFields((err, values) => {
					if ( !err ) {
						console.log('Received values of form: ', values) ;
					}
				});
			},
		},
	})

</script>

<style lang="scss">
</style>