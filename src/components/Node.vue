<template>
  <div>
    <input type="text" placeholder="enter name" v-model="node.name">
    <button @click="addChild">add child</button>
    <button v-if="!noRemove" @click="$emit('remove')">delete</button>
    <ul v-if="node.children">
      <li v-for="(child, index) in node.children" :key="index">
        <node :node="child" @remove="remove(index)"></node>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "node",
  props: {
    node: {
      type: Object,
      required: true
    },
    noRemove: {
      type: Boolean
    }
  },
  methods: {
    remove(index) {
      this.node.children.splice(index, 1);
    },
    addChild() {
      this.node.children.push({
        name: "",
        children: []
      })
    }
  },
}
</script>
