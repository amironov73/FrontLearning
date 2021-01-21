### Виджеты

### DxCheckBox

```vue
<template>
    <DxCheckBox
      style="padding: 2mm;"
      text="Чекни меня"
      v-model:value="checkBoxValue"
      @value-changed="handleValueChange"
    />
</template>

<script>
import DxCheckBox from 'devextreme-vue/check-box';
</script>
```

### DxNumberBox

```vue
<template>
  <DxNumberBox
      v-model:value="amount"
  />
</template>

<script>
import DxNumberBox from 'devextreme-vue/number-box';

</script>
```

### DxLookup

```vue
<template>
  <DxLookup
      :data-source="dataSource"
      placeholder="Выберите продукт..."
  />
</template>

<script>
import DxLookup from 'devextreme-vue/lookup';

export default
{
  components: {
    DxLookup
  },

  data() {
    return {
      dataSource: [
        'яблоки',
        'груши',
        'бананы',
        'лимоны',
        'огурцы',
        'помидоры',
        // ...
      ]
    };
  }
}

</script>

```

### DxLoadIndicator

```vue
<template>
  <DxButton
      text="Нажми"
      @click="toggleIndicator"
  />
  <DxLoadIndicator
      v-model:visible="indicatorVisible"
      width="30"
      height="30"
  />
</template>

<script>
import DxLoadIndicator from "devextreme-vue/load-indicator";
import DxButton from "devextreme-vue/button";

export default
{
  components: {
    DxLoadIndicator,
    DxButton
  },

  data() {
    return {
      indicatorVisible : true
    };
  },

  methods: {
    toggleIndicator: function () {
      this.indicatorVisible = !this.indicatorVisible;
    }
  }
}
</script>

```

### DxDateBox

```vue
<template>
  <DxDateBox
      width="20%"
      type="datetime"
      :min="minDate"
      :max="now"
      v-model:value="theDate"
      @value-changed="onValueChanged"
  />
</template>

<script>
import { DxDateBox } from 'devextreme-vue/date-box';
</script>
```

### DxList

```vue
<template>
  <DxList
      width="20%"
      :dataSource="cities"
      :show-selection-controls="true"
      selection-mode="multiple"
      v-model:selected-items="selectedItems"
  />
</template>

<script>
import DxList from "devextreme-vue/list";
</script>
```

### DxHtmlEditor

```vue
<template>
  <DxHtmlEditor
      width="40%"
      value-type="html">
    <DxToolbar>
      <DxItem format-name="bold"/>
      <DxItem format-name="italic"/>
      <DxItem format-name="alignRight"/>
      <DxItem format-name="alignLeft"/>
    </DxToolbar>
    <p>
      У попа была <b>собака</b>. Он её <i>любил</i>.
      Она съела кусок мяса. Он её убил.
      В землю закопал и надпись написал.
    </p>
  </DxHtmlEditor>
</template>

<script>
import { DxHtmlEditor, DxToolbar, DxItem } from 'devextreme-vue/html-editor';

export default
{
    components: {
      DxHtmlEditor,
      DxToolbar,
      DxItem
    }
}
</script>
```

