<template>
  <div id="app" style="padding:40px">
    <div style="height: 500px; width: 800px; border: 4px solid red; position: relative; border-radius: 5px;">
    <VueDraggableResizable :w="200" :h="200" @dragging="onDrag" @resizing="onResize" :parent="true">
      <p>Draggable And Resizable Component For Vue.js<br>
      X: {{ x }} / Y: {{ y }} - Width: {{ width }} / Height: {{ height }}</p>
    </VueDraggableResizable>
  </div>
  </div>
</template>

<script>
import 'vue-draggable-resizable/dist/VueDraggableResizable.css'
import VueDraggableResizable from 'vue-draggable-resizable'
export default {
  data: function () {
    return {
      width: 0,
      height: 0,
      x: 0,
      y: 0
    }
  },
  components:{
    VueDraggableResizable
  },
  methods: {
    onResize: function (x, y, width, height) {
      this.x = x
      this.y = y
      this.width = width
      this.height = height
    },
    onDrag: function (x, y) {
      this.x = x
      this.y = y
    }
  }
}
</script>