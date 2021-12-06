<template>
  <div>
    <input v-model="checked" type="checkbox"> 全选<br>
    <input :checked="checked" type="checkbox"> java <br>
    <input :checked="checked" type="checkbox"> c++ <br>
    <input :checked="checked" type="checkbox"> js <br>
  </div>
</template>

<script>
export default {
  name: 'About',
  data () {
    return {
      checked: false
    }
  }
}
</script>

<style>

</style>
