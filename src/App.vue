<script>
import home from "./component/home.vue"
import formSection from "./component/formSection.vue"
import lottery from "./component/lottery.vue"
import shop from "./component/shop.vue"
export default {
  components:{
    home,
    formSection,
    lottery,
    shop,
  },
};
</script>

<template>
  <div>
    <home></home>
    <formSection></formSection>
    <lottery></lottery>
    <shop></shop>
  </div>
</template>

<style lang="scss" scoped>

</style>
