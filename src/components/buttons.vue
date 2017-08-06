<template>
    <div class="theButton"
            @click="giveType">
            <text class="text"
                  :style="{borderColor:active}">{{heroType}}</text></div>
</template>

<script>
    //用weex.requireModule(),调用内建模块
    let modal = weex.requireModule('modal')
	export default {
		props:['type','canClick'],
	    data () {
            return {
                heroType: this.type,
                active: 'transparent'
            }
	    },
	    methods:{
	    	giveType(){
                if (this.active == 'transparent') {
                    if (this.canClick) {
                        this.active = 'silver';
	    		        this.$emit('filterOn')
                    } else {
                        modal.toast({
                            message: '只能选择一项',
                            duration: 1
                        })
                    }
                } else {
                    this.active = 'transparent';
	    		        this.$emit('filterOn')
                }
	    	}
	    }
  	}
</script>

<style scoped>
    .text{
		width: 240px;
		height: 100px;
        font-size: 50px;
        text-align: center;
        line-height: 100px;
        border-radius: 6px;
        border-style: solid ;
        border-width: 4px;
        border-color: transparent;
    }
</style>
