<template>
  	<div class="footerBar">
        <buttons v-for="(value,index) in filterType" 
                        :type="value.type"
						:canClick="canClick"
                        :key="index"
                        @filterOn="filterHeros(index)">
        </buttons>
  	</div>
</template>

<script>
	import buttons from './buttons.vue'
  	export default {
		props:['theType'],
		data () {
			return {
				filterType:this.theType
			}
		},
		components:{buttons},
		methods:{
			filterHeros(index){
				this.$emit('needChangeType',index)
			}
		},
		computed:{
			canClick:function (){
				return this.filterType.every((e,i)=>{
						return e.on == false;
					})
			}
		}
  	}
</script>

<style scoped>
  	.footerBar{
		width: 750px;
		height: 100px;
		display: flex;
		flex-direction: row;
		justify-content: space-around;
		align-items:  flex-start;
		align-self: flex-end;
  	}
</style>
