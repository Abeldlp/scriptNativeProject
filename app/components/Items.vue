<template>
    <Page backgroundColor="#dedede">
      <StackLayout orienatation="vertical" >
        <StackLayout style="background-color: #dedede;" height="1"></StackLayout>
        <StackLayout 
          orientation="vertical" 
          backgroundColor="#dedede" 
          height="18%" 
          marginLeft="15px" 
          marginRight="15px"
          marginBottom="20px"
          borderWidth="0 0 2 0"
          borderColor="#878787"
        >
          <StackLayout class="search_bar" orientation="horizontal" iosOverflowSafeArea="true">
            <Image src="~/images/sync-32.png" stretch="aspectFill" height="10%" width="10%" />
            <TextField :text="searchTerm" hint="Zoeken..." width="85%" style="border-color:white;"/>
          </StackLayout>
          <StackLayout orientation="horizontal" class="sub_menu" width="100%">
            <StackLayout orientation="horizontal" class="bezorgen" width="60%">
              <label :class="bezorgen ? 'active' : ''" text="Bezorgen" width="50%" padding="35px 0px" borderRadius="10px"  textAlignment="center" @tap="bezorgen = true"/>
              <label :class="!bezorgen ? 'active' : ''" text="Afhalen" width="50%" padding="35px 0px" borderRadius="10px" textAlignment="center" @tap="bezorgen = false"/>
            </StackLayout>
            <StackLayout orientation="horizontal" width="40%" class="ham_grid">
              <StackLayout width="40%" :class="hamburguer ? 'checked' : 'image_holder'" >
                <Image src="~/images/hamburger.png" height="40%" width="40%" padding="33px" @tap="hamburguer != hamburguer"/>
              </StackLayout>
              <StackLayout width="40%" :class="grid ? 'checked' : 'image_holder'" >
                <Image src="~/images/grid.png" height="40%" width="40%" padding="33px" @tap="grid != grid"/>
              </StackLayout>
            </StackLayout>
          </StackLayout>
        </StackLayout>

        <ScrollView orientation="vertical" paddingTop="35px" marginLeft="15px" marginRight="15px">
           <FlexboxLayout flexWrap="wrap" justifyContent="space-between" alignItems="center" width="100%">
             <FlexboxLayout
               v-for="(item, index) in items"
               justifyContent="center"
               flexDirection="column"
               alignItems="flex-start"
               :key="index" 
               width="49%" 
               height="200px" 
               marginBottom="15px"
               borderRadius="10px"
               :backgroundColor="item.backColor" 
               paddingLeft="30px"
             >
               <label 
               :text="item.name" 
               textAlignment="center"
               color="white" 
               fontWeight="bold"
               />
               <label 
               :text="'$ ' + item.price" 
               textAlignment="center"
               color="white" />
             </FlexboxLayout>
           </FlexboxLayout>
         </ScrollView>
        
      </StackLayout>
    </Page>
</template>

<script>
  import ItemDetails from "./ItemDetails";

  export default {
    data() {
      return {
        searchTerm: '',
        bezorgen: true,
        hamburguer: true,
        grid: false,
        items: [
          {
            name: "Xiangyi",
            price: 2.34,
            backColor: "#313549"
          },
          {
            name: "Xiangyi",
            price: 2.34,
            backColor: "#313549"
          },
          {
            name: "Xiangyi",
            price: 2.34,
            backColor: "#313549"
          },
          {
            name: "Xiangyi",
            price: 2.34,
            backColor: "#313549"
          },
          {
            name: "Xiangyi",
            price: 2.34,
            backColor: "#313549"
          },
          {
            name: "Xiangyi",
            price: 2.34,
            backColor: "#E06633"
          },
          {
            name: "Xiangyi",
            price: 2.34,
            backColor: "#E06633"
          },
          {
            name: "Abel",
            price: 2.34,
            backColor: "#E06633"
          },
          {
            name: "Xiangyi",
            price: 2.34,
            backColor: "#E06633"
          },
          {
            name: "Xiangyi",
            price: 2.34,
            backColor: "#5332DE"
          },
          {
            name: "Xiangyi",
            price: 2.34,
            backColor: "#5332DE"
          },
          {
            name: "Xiangyi",
            price: 2.34,
            backColor: "#5332DE"
          },
          {
            name: "Xiangyi",
            price: 2.34,
            backColor: "#5332DE"
          },
          {
            name: "Xiangyi",
            price: 2.34,
            backColor: "#5332DE"
          }
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
      },
      checkItem(item){
        item != item
      }
    }
  };
</script>

<style scoped lang="scss">
    // Start custom common variables
    @import "@nativescript/theme/scss/variables/blue";
    // End custom common variables
    
    *{
      font-size: 18px;
    }

    // Custom styles
    .search_bar{
      box-shadow: 0px 1px 15px 2px #dedede;
      font-size: 20px;
      padding : 10px 40px;
      background-color : #FFFFFF;
      border-radius : 10px;
      color: #878787;
    }

    .sub_menu{
      margin-top: 20px;

    }

    .bezorgen{
      background-color: #c4c4c4;
      border-radius: 10px;
      color: #878787;
      font-weight: bold;
      transition: all ease-in-out 0.2s;

      .active {
        background-color : #313549;
        color: white;
      }
    }

    .ham_grid{
      margin-left: 33px;

      .image_holder{
        border-radius: 10px;
        background-color: #878787;
        margin-left: 15px;
        border-color: #878787;
        border-width: 2;
        opacity: 0.3;
      }

      .checked{
        opacity: 0.6;
        border-radius: 10px;
        background-color: #a4a4a4;
        margin-left: 15px;
        border-width: 2;
        }

    }



</style>


        // <ScrollView orientation="vertical">
        //   <WrapLayout orientation="horizontal">
        //     <StackLayout
        //       v-for="(item, index) in items"
        //       orientation="vertical"
        //       :key="index" 
        //       width="48%" 
        //       height="200px" 
        //       marginLeft="10px"
        //       marginBottom="15px"
        //       borderRadius="10px"
        //       :backgroundColor="item.backColor" 
        //     >
        //       <label 
        //       :text="item.name" 
        //       textAlignment="center"
        //       color="white" />
        //       <label 
        //       :text="item.price" 
        //       textAlignment="center"
        //       color="white" />
        //     </StackLayout>
        //   </WrapLayout>
        // </ScrollView>