<template>
    <div>  
        <the-footer :theType="filterType"
                    @needChangeType="needChangeType"></the-footer>
        <div class="just-line"></div>
        <hero-lists :theType="filterType"></hero-lists>
    </div>
</template>
 
<script>
    import theFooter from './components/theFooter.vue';
    import heroLists from './components/heroLists.vue';
    export default {
        data () {
            return {
                filterType:[
                    {
                        type:'力量',
                        on:false
                    },{
                        type:'智力',
                        on:false
                    },{
                        type:'敏捷',
                        on:false
                    }
                ]
            }
        },
        components:{theFooter,heroLists},
        methods: {
            needChangeType(index){
                this.filterType[index].on = !this.filterType[index].on;
            }
        }
    }
</script>
 
<style scoped>
    *{
        margin: 0;
        padding: 0;
    }
    .just-line{
        width: 750px;
        height: 2px;
        background-color: black;
        margin-top: 4px;
    }
</style>