<template>
<div>
	<h1>Mobile Store</h1>
	<addMobile @addMod="addMobileToList"/>
	<hr/>
	<ul>
		<ShopingItem v-for="(item,index) in storeData" :key="index" :shopItem="item" @addToTotal="calcTot"/>
	</ul>
	<totalComponent :total="total"/>
</div>
</template>
<script>
import ShopingItem from './ShopingItem.vue';
import totalComponent from './totalComponent.vue'
import addMobile from './addMobile.vue'
export default {
  name: 'ShoppingList',
  components: {
    ShopingItem,
	totalComponent,
	addMobile
  },
  data:function(){
	return{
	storeData:[{model:'Apple',cost:'500'},{model:'Samsung',cost:'300'},{model:'Nokia',cost:'200'}],
	total:0
	}
  },
  methods:{
  calcTot(totFromshopItem){
  this.total=this.total+parseInt(totFromshopItem);
  },
  addMobileToList(amodel,acost){
	this.storeData.push({model:amodel,cost:acost});
  }
  }
}
</script>