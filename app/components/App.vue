<template lang="html">
    <TabView androidTabsPosition="bottom">
        <TabViewItem title="Menu">
            <Frame id="items">
                <Items/>
            </Frame>
        </TabViewItem>

        <TabViewItem title="Tafels">
            <Frame id="browse">
                <Browse/>
            </Frame>
        </TabViewItem>

        <TabViewItem title="Order">
            <Frame id="search">
                <Search/>
            </Frame>
        </TabViewItem>

        <TabViewItem title="Client">
            <Frame id="client">
                <Client/>
            </Frame>
        </TabViewItem>

        <TabViewItem title="Settings">
            <Frame id="settings">
                <Settings/>
            </Frame>
        </TabViewItem>
    </TabView>
</template>

<script>
  import Items from "./Items.vue";
  import Browse from "./Browse.vue";
  import Search from "./Search.vue";
  import Client from "./Client.vue";
  import Settings from "./Settings.vue";

  export default {
    components: {
      Items,
      Browse,
      Search,
      Client,
      Settings
    }
  };
</script>

<style lang="scss">
    // Start custom common variables
    @import "@nativescript/theme/scss/variables/blue";
    // End custom common variables

    // Custom styles

</style>
