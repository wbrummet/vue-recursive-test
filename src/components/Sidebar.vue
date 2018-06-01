<template>
    <div class="sidebar-wrapper">
        <div class="sidebar-body">
            <SidebarRow v-for="account in accounts"
                :account="account"
                :name="account.id"
                :key="account.id">
            </SidebarRow>
        </div>
    </div>
</template>

<script lang="ts">
    import { Component, Vue } from 'vue-property-decorator';
    import SidebarRow from './SidebarRow.vue';

    @Component({
		components: {
			SidebarRow
		}
	})
    export default class Sidebar extends Vue {
        data() {
            return {
                accounts: [
                    {
                        id: '0',
                        name: 'grand-parent',
                        children: [
                            {
                                id: '1',
                                name: 'parent',
                                children: [
                                    {
                                        id: '2',
                                        name: 'child',
                                        children: []
                                    }
                                ]
                            }
                        ]
                    },
                ]
            }
        }
    }
</script>