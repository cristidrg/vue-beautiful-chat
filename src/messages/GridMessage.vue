<template>
  <div class="sc-message--grid" :style="messageColors">
    <slot :message="data">
      <div class="sc-message--grid_container">
        <img class="sc-message--grid__entry" v-for="(entry, idx) in data.items" :key="idx" :src="entry" />
      </div>
    </slot>
  </div>
</template>


<script>
export default {
  props: {
    data: {
      type: Object,
      required: true
    },
    messageColors: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.sc-message--grid_container {
  display: flex;
  flex-wrap: wrap;
}

.sc-message--grid__entry {
  width: 48%;
  padding: 1%;
}

.sc-message--system {
  padding: 8px 20px;
  border-radius: 6px;
  font-weight: 300;
  font-size: 12px;
  line-height: 1.2;
  white-space: pre-wrap;
  -webkit-font-smoothing: subpixel-antialiased;
  font-style: italic;
  opacity: .55;
}

.sc-message--meta {
  font-size: xx-small;
  margin-bottom: 0px;
  margin-top: 5px;
  opacity: .5;
  text-align: center;
}
</style>
