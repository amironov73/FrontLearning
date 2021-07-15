<template>
  <div class="container">

    <div class="row">
      <div class="col calc-title">
        Простой калькулятор, складывающий два числа
      </div>
    </div>

    <form>

      <div class="form-group row mb-2">
        <label for="first" class="col-sm-3 offset-sm-3 form-label">
          Первое слагаемое:
        </label>
        <div class="col-sm-3">
          <input id="first" type="text" class="form-control" v-model="first" />
        </div>
      </div>

      <div class="form-group row mb-2">
        <label for="first" class="col-sm-3 offset-sm-3 form-label">
          Второе слагаемое:
        </label>
        <div class="col-sm-3">
          <input id="second" type="text" class="form-control" v-model="second" />
        </div>
      </div>

      <div class="form-group row">
        <label for="first" class="col-sm-3 offset-sm-3 form-label">
          Сумма:
        </label>
        <div class="col-sm-3">
          <input readonly id="summa" type="text" class="form-control" v-model="summa" />
        </div>
      </div>

    </form>

  </div>

</template>

<script>
export default {
  name: "calc",

  data: function () {
    return {
      first: 123,
      second: 456,
    }
  },

  computed: {
    summa: function () {
      return parseFloat(this.first) + parseFloat(this.second)
    }
  },
}
</script>

<style scoped>
.calc-title {
  font-weight: bold;
  text-align: center;
  padding-bottom: 5mm;
}

</style>