<template>
  <content class="KNN">
    <section class="wrapper" id="inputSection">
      <section id="titleSection">
        <label>Variables</label>
        <label>Values</label>
      </section>
      <section class="inputs">
        <label>X0 </label>
        <base-input placeholder="Value of x in the plot"></base-input>
      </section>

      <section class="inputs">
        <label>X1 </label>
        <base-input placeholder="Value of y in the plot"></base-input>
      </section>
      <input type="button" class="ml-5 btn btn-primary expand" value="Create charts" />
      <input type="button" class="ml-5 btn btn-primary expand" value="Select dataset" />
    </section>
    <section id="outputSection">

      <base-radio name="Iris" class="mb-3" v-model="radio.dataframesSelection">Iris</base-radio>
      <base-radio name="Other" class="mb-3" v-model="radio.dataframesSelection">Other</base-radio>


    </section>

    <div class="mb-4 flex-nowrap">
      <el-select v-validate="'required'" name="dataFrame" class="col-sm-3 select-danger" placeholder="Data-frame"
        v-model="dataFrame">
        <el-option v-for="(dataFrame, i) in dataframes" class="select-danger" :value="dataFrame" :label="dataFrame"
          :key="'dataFrame' + i"></el-option>
      </el-select>
    </div>
  </content>
</template>

<script>
import BaseCheckbox from '../../../components/Inputs/BaseCheckbox.vue';
import BaseRadio from '../../../components/Inputs/BaseRadio.vue';
import Charts from '../../../pages/Charts.vue'

export default {
  name: "KNN",
  data() {
    return {
      dataframes: ["Iris"],
      dataFrame: " ",
      radio : {
        dataframesSelection : "df"
      }
    };
  },
  components: { Charts, BaseCheckbox, BaseRadio }
}
</script>

<style scoped>
#titleSection label {
  margin-right: 23%;
}

.inputs {
  display: flex;
  gap: 25%;
  margin-bottom: 15px;
}

.inputSection label {
  margin-right: 23%;
}

#wrapper {
  display: grid;
  grid-template-columns: 1fr 1fr;
}

.inputSection {
  display: grid;
  grid-template-columns: 1fr 1fr;
}

#outputSection {
  grid-column: 1fr;
}

.textInput {
  display: grid;
  grid-template-columns: 1fr;
}
</style>
