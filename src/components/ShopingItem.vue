<template>
		<li>
			{{shopItem.model}}
			${{shopItem.cost}}
			<br>
			<button @click="quantityInc(shopItem.cost)">Buy</button>
			Quantity : {{quantity}}
			<hr/>
		</li>
</template>
<script>
export default {
name:"ShopingItem",
props:['shopItem'],
data:function(){
return {
quantity:0
}
},
methods:{
quantityInc(cost){
this.quantity=this.quantity+1;
this.$emit('addToTotal',cost);
}
}
}
</script>