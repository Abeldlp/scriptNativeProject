<template>
    <Page>
      <ActionBar>
        <StackLayout orientation="vertical" height="200px">
          <SearchBar
            hint="Zoeken"
            :text="searchTerm"
            @textChange="onTextChanged"
            @submit="onSubmit"
          />
          <label text="ActionBar Title" fontSize="24" verticalAlignment="center" />
          <label text="ActionBar Title" fontSize="24" verticalAlignment="center" />
        </StackLayout>
      </ActionBar>
      <ScrollView orientation="vertical" height="100%">
        <WrapLayout orientation="horizontal" margin="5px auto">
          <label 
            v-for="(item, index) in items" 
            :key="index" :text="item.name" 
            width="48%" 
            height="200px" 
            marginLeft="10px"
            marginBottom="15px"
            borderRadius="5px"
            :backgroundColor="item.backColor" 
            textAlignment="center"
            color="white" />
        </WrapLayout>
      </ScrollView>
    </Page>
</template>

<script>
  import ItemDetails from "./ItemDetails";

  export default {
    data() {
      return {
        searchTerm: '',
        items: [
          {
            name: "Xiangyi",
            backColor: "#313549"
          },
          {
            name: "Xiangyi",
            backColor: "#313549"
          },
          {
            name: "Xiangyi",
            backColor: "#313549"
          },
          {
            name: "Xiangyi",
            backColor: "#313549"
          },
          {
            name: "Xiangyi",
            backColor: "#313549"
          },
          {
            name: "Xiangyi",
            backColor: "#313549"
          },
          {
            name: "Xiangyi",
            backColor: "#313549"
          },
          {
            name: "Xiangyi",
            backColor: "#313549"
          },
          {
            name: "Xiangyi",
            backColor: "#313549"
          },
          {
            name: "Xiangyi",
            backColor: "#313549"
          },
          {
            name: "Xiangyi",
            backColor: "#313549"
          },
          {
            name: "Xiangyi",
            backColor: "#313549"
          },
          {
            name: "Xiangyi",
            backColor: "#313549"
          },
          {
            name: "Xiangyi",
            backColor: "#313549"
          },
          {
            name: "Xiangyi",
            backColor: "#313549"
          },
          {
            name: "Xiangyi",
            backColor: "#313549"
          },
          {
            name: "Xiangyi",
            backColor: "#313549"
          },
          {
            name: "Xiangyi",
            backColor: "#313549"
          },
          {
            name: "Xiangyi",
            backColor: "#313549"
          },
        ]
      };
    },
    methods: {
      onItemTap(args) {
        this.$navigateTo(ItemDetails, {
          frame: 'items',
          props: {item: args.item},
          animated: true,
          transition: {
            name: "slide",
            duration: 200,
            curve: "ease"
          }
        });
      }
    }
  };
</script>

<style scoped lang="scss">
    // Start custom common variables
    @import "@nativescript/theme/scss/variables/blue";
    // End custom common variables

    // Custom styles

</style>
