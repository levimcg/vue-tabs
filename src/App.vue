<template>
    <div class="rvt-container rvt-m-top-xl">
        <Tabs label="Vue tabs">
            <TabsPanel name="About us" :selected="true">
                About panel
            </TabsPanel>
            <TabsPanel name="Team">
                Team panel
            </TabsPanel>
            <TabsPanel name="Contact">
                Contact panel
            </TabsPanel>
            <TabsPanel name="Schedule">
                Schedule panel
            </TabsPanel>
        </Tabs>
    </div>
</template>

<script>
    import Tabs from './components/Tabs';
    import TabsPanel from './components/TabsPanel';

    export default {
        name: 'app',
        components: {
            Tabs, TabsPanel
        }
    }
</script>

<style>
    body {
        font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    }

    html * {
        box-sizing: border-box;
    }

    #app {
        padding: 3rem;
    }
</style>
