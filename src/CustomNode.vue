<script lang="ts" setup>
import { Handle, Position } from "@xyflow/vue";
import { ref } from "vue";

const counter = ref(0);
</script>

<template>
  <div class="custom-node">
    <Handle type="target" :position="Position.Top" />
    <button class="increment nodrag" @click="counter++">Increment</button>

    <div v-if="counter > 0" class="counter">
      <div class="count" v-for="count of counter" :key="`count-${count}`">
        {{ count }}
      </div>
    </div>
  </div>
</template>

<style>
.custom-node {
  min-width: 100px;
  gap: 4px;
  padding: 8px;
  color: var(--xy-node-color, var(--xy-node-color-default));
  background: var(--xy-node-background-color, var(--xy-node-background-color-default));
  border: var(--xy-node-border, var(--xy-node-border-default));
  border-radius: 4px;
}

.increment {
  border-radius: 4px;
  background: #08754b;
  font-size: 10px;
  color: #fff;
  cursor: pointer;
  border: none;
}

.increment:hover {
  box-shadow:
    0 10px 15px -3px rgb(0 0 0 / 0.1),
    0 4px 6px -4px rgb(0 0 0 / 0.1);
}

.counter {
  margin-top: 8px;
  display: grid;
  grid-template-columns: repeat(4, minmax(0, 1fr));
  gap: 4px;
}

.count {
  font-size: 6px;
  color: inherit;
  border: var(--xy-node-border, var(--xy-node-border-default));
  border-radius: 8px;
}
</style>
