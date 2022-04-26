<!-- 
	This is the 404 error page, it uses the dashboard layout in: 
	"./layouts/Default.vue" .
 -->

<template>
	<a-result status="404" title="404" sub-title="Sorry, the page you visited does not exist.">
		<template #extra>
			<router-link class="ant-btn ant-btn-primary" to="/">Back Home</router-link>
		</template>
	</a-result>
</template>