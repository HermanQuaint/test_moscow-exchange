<template>
  <div class="order">
    <OrderingForm/>
  </div>
</template>

<script>
// @ is an alias to /src
import OrderingForm from "../components/OrderingForm";
export default {
  name: 'Order',
  components: {
    OrderingForm
  }
}
</script>
