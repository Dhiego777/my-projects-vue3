<template>
    <section class="pr-3">
        <strong class="display">{{ tempoDecorrido }}</strong>
    </section>
</template>
<script>
export default {
    name: 'ProgressiveClock',
  props: {
    timeInSeconds: {
      type:Number,
      default: 0
    }
  },
  computed: {
    tempoDecorrido() {
      return new Date(this.timeInSeconds * 1000).toISOString().substring(11, 19)
    }
  },
}
</script>
<style>
.display {
    color: var(--texto-primario);
}
</style>