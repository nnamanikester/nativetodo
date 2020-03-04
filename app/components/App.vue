<template>
    <Page>
        <ActionBar>
            <GridLayout width="100%" columns="auto, *">
                <Label text="MENU" @tap="$refs.drawer.nativeView.showDrawer()" col="0"/>
                <Label class="title" text="NativeToDo"  col="1"/>
            </GridLayout>
        </ActionBar>

        <RadSideDrawer ref="drawer">
            <StackLayout ~drawerContent backgroundColor="#ffffff">
                <Label class="drawer-header" text="Drawer"/>

                <Label class="drawer-item yes" text="Home"/>
                <Label class="drawer-item" text="About"/>
                <Label class="drawer-item" text="Settings"/>
            </StackLayout>

            <GridLayout ~mainContent columns="*" rows="*">
                <Label class="message" :text="msg" col="0" row="0"/>
            </GridLayout>

            <GridLayout ~mainContent columns="*" rows="*">
                <NavigationButton android.systemIcon="ic_menu_back" @tap="goHome" />
            </GridLayout>
        </RadSideDrawer>
    </Page>
</template>

<script>
  import Home from '~/pages/Home.vue'
  export default {
    data() {
      return {
        msg: 'Intersting! I love this shi*, Okay'
      }
    },
    methods: {
        goHome () {
            this.$navigateTo(Home);
            
        }
    }
  }
</script>

<style scoped>
    ActionBar {
        background-color: #53ba82;
        color: #ffffff;
    }

    .title {
        text-align: left;
        padding-left: 16;
    }

    .message {
        vertical-align: center;
        text-align: center;
        font-size: 20;
        color: #333333;
    }

    .drawer-header {
        padding: 50 16 16 16;
        margin-bottom: 16;
        background-color: #53ba82;
        color: #ffffff;
        font-size: 24;
    }

    .drawer-item {
        padding: 8 16;
        color: #333333;
        font-size: 16;
    }

</style>
