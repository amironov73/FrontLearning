<template>
  <div>
    <h2 class="content-block">Adder</h2>
    <div class="content-block">
      <DxTextBox width=20% v-model="firstValue" />
      <DxTextBox width=20% v-model="secondValue" />
      <DxTextBox width=20% v-model="thirdValue" />
      <br/>
      <DxButton
          text="Add"
          @click="handleAdd">
      </DxButton>
    </div>
  </div>
</template>

<script>
import DxButton from "devextreme-vue/button";
import DxTextBox from 'devextreme-vue/text-box';

export default {
  components: {
    DxButton,
    DxTextBox
  },

  data() {
    return {
      firstValue: "",
      secondValue: "",
      thirdValue: ""
    };
  },

  methods: {
    handleAdd: function() {
      this.thirdValue = parseInt(this.firstValue)
          + parseInt(this.secondValue);
    }
  }
}
</script>

<style lang="scss">
</style>
