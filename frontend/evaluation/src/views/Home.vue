<template>
	<div class="home">
		<UserNav />
		<ul class="nav nav-tabs" id="myTab" role="tablist">
			<li class="nav-item">
				<a class="nav-link active" id="home-tab" data-toggle="tab" href="#home" role="tab" aria-controls="home"
				 aria-selected="true">组间评分表</a>
			</li>
			<li class="nav-item" v-if="this.$store.state.loginState === 2">
				<a class="nav-link" id="profile-tab" data-toggle="tab" href="#profile" role="tab" aria-controls="profile"
				 aria-selected="false">组内评分表</a>
			</li>
		</ul>
		<div class="tab-content" id="myTabContent">
			<div class="tab-pane fade show active" id="home" role="tabpanel" aria-labelledby="home-tab">
				<OuterFormList />
			</div>
			<div v-if="this.$store.state.loginState === 2" class="tab-pane fade" id="profile" role="tabpanel" aria-labelledby="profile-tab">
				<InnerFormList />
			</div>
		</div>
	</div>
</template>

<script>
	import OuterFormList from '../components/OuterFormList.vue'
	import InnerFormList from '../components/InnerFormList.vue'
	import UserNav from '../components/UserNav.vue'

	export default {
		name: 'Home',
		components: {
			OuterFormList,
			InnerFormList,
			UserNav
		}
	}
</script>
