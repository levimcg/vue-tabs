<template>
    <div class="rvt-tabs" :aria-label="label">
        <div class="rvt-tabs__tablist" role="tablist">
            <button
                v-for="(tab, index) in tabs"
                :key="index"
                @click="changeTab(tab)"
                @keydown="handleKeydown(tab, $event)"
                :aria-selected="tab.isActive"
                :id="getId(tab.name)"
                class="rvt-tabs__tab"
            >
                {{ tab.name }}
            </button>
        </div>
        <slot></slot>
    </div>
</template>

<script>
    export default {
        name: 'Tabs',

        props: {
            label: {
                required: true,
                type: String
            }
        },

        data() {
            return {
                tabs: []
            }
        },

        created() {
            this.tabs = this.$children;
        },

        methods: {
            changeTab(selectedTab) {
                this.tabs.forEach(tab => {
                    tab.isActive = (tab.name == selectedTab.name);
                });
            },

            handleKeydown(tab, $event) {
                console.log($event.keyCode);
            },

            getId(value) {
                return value.toLowerCase().replace(/ /g, '-');
            }
        }
    }
</script>
