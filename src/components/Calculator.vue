<!-- The Calculaor itself -->

<template>
  <div class="p-3 rounded" style="max-width: 410px; margin: 50px auto; background: gray;">
    
    <div class="w-full rounded m-1 p-3 text-right lead font-weight-bold text-white bg-vue-darkgray">
      {{ calculatorValue || 0 }}
    </div>

    <div class="row no-gutters">
      <div class="col-3" v-for="n in calculatorObjects" :key="n">
        <div class="lead text-white text-center m-1 py-3 bg-vue-darkgray rounded hover-element"
          :class="{'bg-vue-blue': ['C','*','/','-','+','%','='].includes(n)}"
          @click="action(n)"
        >
          {{n}}
        </div>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: 'MyCalculator',
  props: {
    msg: String
  },
  data() {
    return {
      calculatorValue: '',
      calculatorObjects: ['C','*','/','-',7,8,9,'+',4,5,6,'%',1,2,3,'=',0,'.'],
      operator: null,
      previousCalculatorValue: '',
    }
  },
  methods: {
    action(n){
     
      if(!isNaN(n) || n === '.'){
        this.calculatorValue += n + '';
      }


      if(n === 'C'){
        this.calculatorValue = '';
      }

       if(['/','*','-','+'].includes(n)){
        this.operator = n;
        this.previousCalculatorValue = this.calculatorValue;
        this.calculatorValue = '';
      }

      if(n === '%'){
        this.calculatorValue = this.calculatorValue / 100 + '';
      }

      if(n === '='){
        this.calculatorValue = eval(
          this.previousCalculatorValue + this.operator + this.calculatorValue
        );
        this.previousCalculatorValue = '';
        this.operator = null;
      }
    }
  }
}
</script>


<style scoped>
  .bg-vue-darkgray {
    background: rgb(43, 43, 43);
  }
  .hover-element:hover {
    cursor: pointer;
    background: #3D5875;
  }
  .bg-vue-blue {
    background: #1b0f55;
  }
</style>
<!-- geraldabuchi@twitter -->