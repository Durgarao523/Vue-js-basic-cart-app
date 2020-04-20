<template>
<div>
Model Name : <input v-model="modelName" type="text" />
Cost : <input v-model="modelCost" type="Number"/>
<button @click=addClick>Add</button>
</div>
</template>
<script>
export default {
name:"addMobile",
data:function(){
	return {
	modelName:"",
	modelCost:"",
	}
},
methods:{
addClick:function(){
this.$emit("addMod",this.modelName,this.modelCost);
this.modelName="";
this.modelCost="";
}
}
}
</script>