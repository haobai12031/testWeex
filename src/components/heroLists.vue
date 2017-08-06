<template>
    <div>
        <list class="lists">
            <cell v-for="(hero,index) in herosList" 
                  :key="index">
                <text class="hero-msg">{{hero.name}}</text>
            </cell> 
        </list> 
    </div>
</template>

<script>
    import heros from './data.js';
    export default {
        props:['theType'],
        data () {
            return {
            }
        },
        computed:{
            herosList(){
                let chosedType = this.theType.find((e,i)=>{
                    return e.on
                });
                if (chosedType) {
                    return heros.filter((e,i)=>{
                        return e.heroTag.includes(chosedType.type)
                    })
                } else {
                    return heros
                }
            }
        },
        methods:{
        }
    }
</script>

<style scoped>
    .lists{
        width: 750px;
        height:1111px;
    }
    .hero-msg{
        width: 750px;
        height: 120px;
        line-height: 120px;
        text-align: center;
        font-size: 40px;
        background-color: rgba(0, 0, 0, 0.4);
        color: white;
    }
</style>