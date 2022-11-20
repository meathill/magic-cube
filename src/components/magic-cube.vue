<script lang="ts" setup>
import {ref} from "vue";

const colors = ['white', 'yellow', 'green', 'blue', 'orange', 'red'];
const rows = ref<number>(3);
const columns = ref<number>(3);
</script>

<script lang="ts">
export default {
  name: 'MagicCube',
}
</script>

<template lang="pug">
.mgaic-cube
  template(v-for="(color, colorIndex) in colors")
    template(v-for="item in rows * columns" :key="color + item")
      .face(
        :class="color"
        :style="{'--face': colorIndex, '--index': item, '--color': color }"
      )

</template>
