
<template>
	<div class="sign-in">   
		<a-row type="flex" :gutter="[24,24]" justify="space-around" align="middle" class="row-main">
			<!-- Sign Up Form Column -->
			<a-col :span="24" :md="{ span: 14, offset: 2 }" :lg="10" :xl="6" class="col-form mr-auto">
				<h4 class="mb-15">Modifiez vos information de connexion</h4>
				<p class="text-muted">Pour des raisons de sécurité, nous vous recommendons d'enrégistrer une adresse mail et un mot de passe avec les quelles vous vous connecterez.</p>

				<!-- Sign Up Form -->
				<a-form
					id="components-form-demo-normal-login"
					:form="form"
					class="login-form"
					@submit="handleSubmit"
					:hideRequiredMark="true"
				>
					<a-form-item class="mb-10" label="Email" :colon="false">
						<a-input 
						v-decorator="[
						'email',
						{ rules: [{ required: true, message: 'Veuillez entrer votre adresse mail' }] },
						]" placeholder="Adresse email" />
					</a-form-item>

                    <a-form-item class="mb-10" label="Mot de passe" :colon="false">
						<a-input 
						v-decorator="[
						'password',
						{ rules: [{ required: true, message: 'Veuillez entrer un mot de passe' }] },
						]" placeholder="Mot de passe" />
					</a-form-item>

                    <a-form-item class="mb-10" label="Confirmez le mot de passe" :colon="false">
						<a-input 
						v-decorator="[
						'password_c',
						{ rules: [{ required: true, message: 'Veuillez entrer de nouveau le mot de passe' }] },
						]" placeholder="Confirmer le mot de passe" />
					</a-form-item>
					
					</a-form-item>
					<a-form-item>
						<router-link to="/dashboards" class="font-bold text-dark">
							<a-button type="primary" block html-type="submit" class="login-form-button">
							SE CONNECTER
							</a-button>
						</router-link>
					</a-form-item>
				</a-form>
				<!-- / Sign Up Form -->

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