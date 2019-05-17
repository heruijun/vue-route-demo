<template>
  <div class="pageB">
    <h1>Page B, Hello {{ this.$route.params.userId }}</h1>
    <span class="router-button" @click="pageBack">返回</span> |
    <span class="router-button" @click="toPageCReplace">PageC(replace方式)</span>
  </div>
</template>

<script>
export default {
  mounted () {
    alert(this.$route.params.userId)
  },

  methods: {
    pageBack() {
      this.$router.go(-1)
    },
    toPageCReplace() {
      this.$router.replace({ name: 'pageC', params: { userId: 123 }})
    }
  },
}
</script>
