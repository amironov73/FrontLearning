<template>
  <div>
    <h2 class="content-block">Buttons</h2>
    <div class="content-block">
      <DxButton
          text="Нажми меня"
          @click="firstClicked"
      >
      </DxButton>
      <div>&nbsp;</div>
      <br/>
      <DxButton
          text="Нажми меня"
          type="danger"
          @click="secondClicked"
      >
      </DxButton>
    </div>
  </div>
</template>

<script>
import DxButton from "devextreme-vue/button";
import notify from "devextreme/ui/notify";

export default {
  components: {
    DxButton
  },

  methods: {
    firstClicked() {
      notify("Первая пошла!")
    },

    secondClicked() {
      notify("Вторая пошла!")
    }
  }

}
</script>

<style lang="scss">
</style>