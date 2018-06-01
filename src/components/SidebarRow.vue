<template>
	<div class="sidebar-row-wrapper">
		<div class="outer-flex" @click="$emit('idSelected', account.id)">
			<div class="name-row">
				<div class="account-name">
					{{account.name}}
				</div>
			</div>
		</div>
		<div class="child" v-for="child in account.children" :name="child.id" :key="child.id">
			<SidebarRow
                :account="child"
                :name="child.id"
                :key="child.id">
            </SidebarRow>
		</div>
	</div>
</template>

<script lang="ts">
	import { Component, Vue, Prop } from 'vue-property-decorator';

	@Component({
		components: {
			SidebarRow
		}
	})
	export default class SidebarRow extends Vue {
		@Prop()
		public account: object|undefined;
	}
</script>