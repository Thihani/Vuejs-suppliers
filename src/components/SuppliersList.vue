<template>
<div>
<supplier 
v-for="supplier in suppliers" 
:key="supplier.id" 
:name="supplier.name" 
:status="supplier.status" 
:checkAt="supplier.checkAt"/>

</div>
</template>

<script>
import Supplier from './Supplier.vue'
export default {
  name: "SuppliersList",
  components: {
    Supplier
  },
  props: ['suppliers'],
}

</script>
