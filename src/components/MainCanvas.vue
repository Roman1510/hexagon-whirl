<script>
export default {
  mounted() {
    const renderer = this.$refs.renderer
    const box = this.$refs.box.mesh
    renderer.onBeforeRender(() => {
      box.rotation.x += 0.01
    })
  },
}
</script>

<template>
  <Renderer ref="renderer">
    <Camera :position="{ z: 10 }" />
    <Scene>
      <PointLight :position="{ y: 50, z: 50 }" />
      <Box ref="box" :rotation="{ y: Math.PI / 4, z: Math.PI / 4 }">
        <LambertMaterial />
      </Box>
    </Scene>
  </Renderer>
</template>

