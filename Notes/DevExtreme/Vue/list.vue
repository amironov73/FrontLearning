<template>
  <div>
    <div class="box-title">У лукоморья</div>
    <br/>
    <DxList
      :width="600"
      :height="200"
      :dataSource="verse"
      item-template="list-item"
    >
      <template #list-item="{ data, index }">
        <div>
          <strong>{{ index + 1 }})</strong> {{data}}
        </div>
      </template>
    </DxList>
  </div>
</template>

<script>
import 'devextreme/dist/css/dx.light.css';
import { DxList } from 'devextreme-vue/list';

const verse = ["У лукоморья дуб зелёный;",
"Златая цепь на дубе том:",
"И днём и ночью кот учёный",
"Всё ходит по цепи кругом;",
"Идёт направо — песнь заводит,",
"Налево — сказку говорит.",
"Там чудеса: там леший бродит,",
"Русалка на ветвях сидит;"]

export default {
  name: "HelloList",

  components: { DxList },

  data() {
    return {
      verse
    }
  },
}
</script>

<style scoped>
.box-title {
  font-weight: bold;
  font-size: large;
  text-align: center;
}
</style>
