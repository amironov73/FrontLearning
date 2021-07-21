<template>
  <div>
    <div class="box-title">Столбец в боксе</div>
    <br/>
    <DxBox
        class="demo-box"
        :height="130"
        :width="600"
        direction="row"
    >
      <DxItem :ratio="1">
        <template #default>
          <div class="my-box-row first">
            Под старыми телегами рабочие лежат
          </div>
        </template>
      </DxItem>
      <DxItem :ratio="1">
        <template #default>
          <div class="my-box-row second">
            Через четыре года здесь будет город-сад
          </div>
        </template>
      </DxItem>
      <DxItem :ratio="1">
        <template #default>
          <div class="my-box-row third">
            Ну, или не будет...
          </div>
        </template>
      </DxItem>
    </DxBox>

    <br/>

    <div class="box-title">Колонка в боксе</div>
    <br/>
    <DxBox
        class="demo-box"
        :height="130"
        :width="600"
        direction="col"
    >
      <DxItem :ratio="1">
        <template #default>
          <div class="my-box-column first">
            Под старыми телегами рабочие лежат
          </div>
        </template>
      </DxItem>
      <DxItem :ratio="1">
        <template #default>
          <div class="my-box-column second">
            Через четыре года здесь будет город-сад!
          </div>
        </template>
      </DxItem>
      <DxItem :ratio="1">
        <template #default>
          <div class="my-box-column third">
            Ну, или не будет...
          </div>
        </template>
      </DxItem>
    </DxBox>

  </div>
</template>

<script>
import 'devextreme/dist/css/dx.light.css';
import {DxBox, DxItem} from 'devextreme-vue/box';

export default {
  name: "HelloBox",

  components: {
    DxBox, DxItem
  },
}
</script>

<style scoped>
.demo-box {
  background: aqua;
}

.box-title {
  font-weight: bold;
  font-size: large;
  text-align: center;
}

.my-box-column {
  text-align: center;
  align-content: center;
  margin: 1mm 5mm;
  padding: 1mm;
}

.my-box-row {
  text-align: center;
  align-content: center;
  margin: 3mm;
  padding: 3mm;
}

.first {
  background: yellow;
}

.second {
  background: chartreuse;
}

.third {
  background: papayawhip;
}

</style>
