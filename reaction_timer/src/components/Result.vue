<template>
  <div>
    <p>Result is {{ score }} ms</p>
    <div v-if="score<=250">
        <p>You are too fast</p>
    </div>
    <div v-else-if="score>250 && score<=500">
        <p>You are normal</p>
    </div>
    <div v-else>
        <p>You are too slow! Try again!</p>
    </div>
  </div>
</template>

<script>
export default {
    props: ['score']
}
</script>

<style>

</style>