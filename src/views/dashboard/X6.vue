<template>
  <div style="display: flex">
    <div id="container" style="flex: 1;height:100vh;"></div>
  </div>
</template>

<script>
import { Graph } from '@antv/x6'

const data = {
  // 节点
  nodes: [
    {
      id: 'node1', // String，可选，节点的唯一标识
      x: 40, // Number，必选，节点位置的 x 值
      y: 40, // Number，必选，节点位置的 y 值
      width: 80, // Number，可选，节点大小的 width 值
      height: 40, // Number，可选，节点大小的 height 值
      label: 'hello' // String，节点标签
    },
    {
      id: 'node2', // String，节点的唯一标识
      x: 160, // Number，必选，节点位置的 x 值
      y: 180, // Number，必选，节点位置的 y 值
      width: 80, // Number，可选，节点大小的 width 值
      height: 40, // Number，可选，节点大小的 height 值
      label: 'world' // String，节点标签
    }
  ],
  // 边
  edges: [
    {
      source: 'node1', // String，必须，起始节点 id
      target: 'node2' // String，必须，目标节点 id
    }
  ]
}
export default {
  name: 'X6',
  mounted () {
    this.init()
  },
  methods: {
    init () {
      const graph = new Graph({
        container: document.getElementById('container'),
        autoResize: true,
        grid: true
      })

      graph.fromJSON(data)
    }
  }
}

</script>

<style scoped>

</style>
