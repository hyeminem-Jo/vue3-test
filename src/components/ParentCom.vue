<template>
  <ChildCom :msg="msg" />
</template>

<script>
  import ChildCom from '~/components/ChildCom.vue';
  export default {
    components: {
      ChildCom,
    },
    props: {
      msg: {
        type: String,
        default: '',
      }
    }
  }
</script>