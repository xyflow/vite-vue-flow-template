<script lang="ts" setup>
import { shallowRef } from 'vue'
import { addEdge, Background, Controls, MiniMap, VueFlow, type Connection, type Edge, type Node } from '@xyflow/vue'
import CustomNode from './CustomNode.vue'
import CustomEdge from './CustomEdge.vue'

const nodes = shallowRef<Node[]>([
  { id: '1', type: 'input', data: { label: 'Node 1' }, position: { x: 250, y: 5 } },
  { id: '2', type: 'output', data: { label: 'Node 2' }, position: { x: 100, y: 100 } },
  { id: '3', type: 'custom', data: { label: 'Node 3' }, position: { x: 400, y: 100 } },
])

const edges = shallowRef<Edge[]>([
  { id: 'e1-2', source: '1', target: '2', type: 'custom' },
  { id: 'e1-3', source: '1', target: '3', animated: true },
])

function onConnect(connection: Connection) {
  edges.value = addEdge(connection, edges.value)
}
</script>

<template>
  <VueFlow
    v-model:nodes="nodes"
    v-model:edges="edges"
    fit-view
    class="vue-flow-basic-example"
    :min-zoom="0.2"
    :max-zoom="4"
    @connect="onConnect"
  >
    <Background color="#aaa" :gap="8" />
    <MiniMap />
    <Controls />
    <template #node-custom="nodeProps">
      <CustomNode v-bind="nodeProps" />
    </template>
    <template #edge-custom="edgeProps">
      <CustomEdge v-bind="edgeProps" />
    </template>
  </VueFlow>
</template>
