<script setup>
/*import { onMounted } from 'vue';
import * as d3 from 'd3';
import { ref } from 'vue';*/
import ComponentVue from './components/Componentvuetify';

/*
let ageData = ref([]);
let xScale;

const rectHeight = 20;
const rectSpacing = 10;
const svgWidth = 1200;
const svgHeight = 800;
const labelXPosition = svgWidth / 2;
const maleLabelXPosition = 50;
const femaleLabelXPosition = 1000;
const maxRectWidth = 500;

onMounted(async () => {
  const data = await d3.csv('gender.csv', typeConversion);
  console.log(data)

  const filtered = data.filter(r => r.Gender && r.BasePay > 0 && r.JobTitle && r.Age);
  console.log(filtered)
  filtered.sort((a, b) => a.Age - b.Age);

  const finishedData = prepareBarChart(filtered);
  console.log(finishedData);
  ageData.value = finishedData;

  const extents = d3.extent(finishedData.flatMap(item => [item.Male, item.Female]));
  xScale = d3.scaleLinear()
    .domain([0, extents[1]])
    .range([0, maxRectWidth]);
});

function typeConversion(row) {
  return {
    Gender: row.Gender.toLowerCase(),
    BasePay: +row.BasePay,
    JobTitle: row.JobTitle.toLowerCase(),
    Age: +row.Age,
  };
}

function prepareBarChart(d) {
  const dataMap = d3.rollup(
    d,
    r => d3.mean(r, x => x.BasePay),
    d => d.Age,
    d => d.Gender
  );

  const dataArray = Array.from(dataMap, ([age, genderMap]) => {
    const maleData = genderMap.get('male');
    const femaleData = genderMap.get('female');

    return {
      Age: age,
      Male: maleData,
      Female: femaleData,
    };
  });

  return dataArray;
}

function sortByAge() {
  ageData.value.sort((a, b) => a.Age - b.Age);
}

function sortByTotal() {
  ageData.value.sort((a, b) => {
    const totalA = a.Male + a.Female;
    const totalB = b.Male + b.Female;
    return totalA - totalB;
  });
}*/
</script>

<template>
  <div>
    <ComponentVue></ComponentVue>
  </div>
  <!--<div>
    <h1>Oefening 1</h1>
    <v-btn @click="sortByAge">Sort by age</v-btn>
    <v-btn @click="sortByTotal">Sort by total</v-btn>
    <svg :width="svgWidth" :height="svgHeight">
      <g v-for="(genderData, index) in ageData" :key="index" :transform="`translate(0, ${index * (rectHeight + rectSpacing)})`">

        <text :x="labelXPosition + 60" y="15">{{ genderData.Age }}</text>

        <rect
          x="700"
          y="0"
          :width="xScale(genderData.Female)"
          :height="rectHeight"
          fill="#46586b"
        ></rect>

        <text :x="femaleLabelXPosition" y="-15" text-anchor="middle">{{ genderData.Female }}</text>

        <rect
          :x="650 - xScale(genderData.Male)"
          y="0"
          :width="xScale(genderData.Male)"
          :height="rectHeight"
          fill="#2c3e50"
        ></rect>

        <text :x="maleLabelXPosition + 180" y="-15">{{ genderData.Male }}</text>
      </g>
    </svg>
  </div>-->
</template>
