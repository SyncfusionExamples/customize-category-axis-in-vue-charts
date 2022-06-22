<template>
  <div id="app">
    <ejs-chart :primaryXAxis="chartPrimaryXAxis" >
      <e-series-collection>
        <e-series type="Column" :dataSource="weatherReport1" xName="country" yName="temperature">
        </e-series>
        <e-series type="Column" :dataSource="weatherReport2" xName="country" yName="temperature"></e-series>
      </e-series-collection>
    </ejs-chart>
    <!-- <ejs-chart :primaryXAxis="chartPrimaryXAxis" :title="chartTitle" 
    :primaryYAxis="chartPrimaryYAxis">
      <e-series-collection>
        <e-series type="Column" :dataSource="chartData" xName="country" yName="value">
        </e-series>
      </e-series-collection>
    </ejs-chart> -->
  </div>
</template>

<script>
import Vue from "vue";
import { ChartPlugin, ColumnSeries, Category } from '@syncfusion/ej2-vue-charts';
Vue.use(ChartPlugin);

export default {
  provide : {
    chart : [ColumnSeries, Category]
  },
  data() {
    return {
      weatherReport1 : [
         { country : "Myanmar", temperature : 7.3 },
         { country : "India", temperature : 7.9 },
         { country : "Bangladesh", temperature : 6.8 },
         { country : "Cambodia", temperature : 7.0 },
         { country : "China", temperature : 6.9 }
      ],
      weatherReport2 : [
         { country : "Poland", temperature :2.7 },
         { country : "Australia", temperature :2.5 },
         { country : "Singapore", temperature :2.0 },
         { country : "Canada", temperature :1.4 },
         { country : "Germany", temperature :1.8 }
      ],
      chartPrimaryXAxis : {
        valueType: 'Category',
        isIndexed : true
      },
      chartTitle : 'Olympic Medals',
      // chartPrimaryYAxis : {
      //   title : 'Medals Count'
      // },
      // chartPrimaryXAxis : {
      //   valueType: 'Category',
      //   title: 'Country',
      //   minimum : 1,
      //   maximum : 5,
      //   interval : 2,
      //   labelPlacement : 'OnTicks'
      // },
      // chartData : [
      //  { country : "USA", value : 46 },
      //  { country : "GBR", value : 27 },
      //  { country : "CHN", value : 26 },
      //  { country : "UK",  value : 23 },
      //  { country : "AUS", value : 16 },
      //  { country : "IND", value : 36 },
      //  { country : "DEN", value : 12 },
      //  { country : "MEX", value : 20 }
      // ]
    };
  }
}
</script>

