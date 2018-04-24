<template>
    <div
        class="rvt-tabs__panel"
        role="tabpanel"
        :hidden="!isActive"
        :aria-describedby="tabId"
        tabindex="0"
    >
        <slot>Butts</slot>
    </div>
</template>

<script>
export default {
    name: 'TabsPanel',

    props: {
        name: {
            required: true
        },
        selected: {
            default: false
        }
    },

    data() {
        return {
            isActive: false
        }
    },

    mounted() {
        this.isActive = this.selected;
    },

    computed: {
        tabId() {
            return this.name.toLowerCase().replace(/ /g, '-');
        }
    }
}
</script>
