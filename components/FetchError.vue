<template>
  <div>
    This component should trigger a 404 (in 2000ms)
  </div>
</template>

<script>
export default {
  async fetch() {
    await new Promise(res => setTimeout(res, 2000));

    this.$nuxt.error({ statusCode: 404, message: "Not found" });
  }
}
</script>
