<template>
  <div>
    <ul>
      <li><node :node="node" no-remove/></li>
    </ul>
  </div>
</template>

<script>
import Node from './components/Node.vue'

export default {
  components: {
    Node
  },
  data() {
    return {
      node: {
        name: "root",
        children: []
      }
    }
  }
}
</script>
