<template>
    <Page>
        <GridLayout ~mainContent columns="*" rows="*">
            <Label class="message" :text="msg" col="0" row="0"/>
        </GridLayout>
    </Page>
</template>
<script>
    export default {
        name: 'Home',
        data () {
            return {
                msg: "Hello World!"
            };
        }
    }
</script>