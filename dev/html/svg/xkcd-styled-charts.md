# xkcd styled charts

{% embed url="https://timqian.com/chart.xkcd/" %}



## Introduction

Chart.xkcd is a chart library plots “sketchy”, “cartoony” or “hand-drawn” styled charts.

[![donate](https://flat.badgen.net/badge/support%20me/donate/?color=e85b46)](https://patreon.com/timqian) [![slack](https://flat.badgen.net/badge/chat%20with%20us/slack/green)](https://join.slack.com/t/t9tio/shared_invite/enQtNjgzMzkwMDM0NTE3LTE5ZTUzYjU4Y2I0YzRiZjNkYTkzMzE1ZmM0NDdmYzRlZmMxNGY1MzZlN2EwYjYyNWVlMWY0Nzk2MDBhNWZlY2I) [![stars](https://flat.badgen.net/github/stars/timqian/chart.xkcd?icon=github)](https://github.com/timqian/chart.xkcd) [![npm](https://flat.badgen.net/npm/v/chart.xkcd/?color=fb3e44)](https://www.npmjs.com/package/chart.xkcd)

## Getting started

It’s easy to get started with chart.xkcd. All that’s required is the script included in your page along with a single `<svg>` node to render the chart.

In the following example we create a line chart.

**JS part of the example**

```text
  const svg = document.querySelector('.line-chart')
  new chartXkcd.Line(svg, {
    title: '',
    xLabel: '',
    yLabel: '',
    data: {...},
    options: {},
  });
```

### Parameters description

* `title`: optional title of the chart
* `xLabel`: optional x label of the chart
* `yLabel`: optional y label of the chart
* `data`: the data you want to visulize
* `options`: optional configurations to customize how the chart looks

## Installation

You can install chart.xkcd via script tag in HTML or via npm

### Via Script Tag

```text
<script src="https://cdn.jsdelivr.net/npm/chart.xkcd@1/dist/chart.xkcd.min.js"></script>
<script>
    const myChart = new chartXkcd.Line(svg, {...});
</script>
```

### Via npm

**Install**

```text
npm i chart.xkcd
```

**Usage**

```text
import chartXkcd from 'chart.xkcd';
const myChart = new chartXkcd.Line(svg, {...});
```

**Other ways**

* React wrapper: [chart.xkcd-react](https://github.com/obiwankenoobi/chart.xkcd-react)  
* Vue wrapper:
  * [chart.xkcd-vue](https://github.com/shiyiya/chart.xkcd-vue)
  * [chart.xkcd-vue-wrapper](https://github.com/wistcc/chart.xkcd-vue-wrapper)

## Line chart

Line chart displays series of data points in the form of lines. It can be used to show trend data, or comparison of different data sets.

### JS part

```text
const lineChart = new chartXkcd.Line(svg, {
  title: 'Monthly income of an indie developer', // optional
  xLabel: 'Month', // optional
  yLabel: '$ Dollors', // optional
  data: {
    labels: ['1', '2', '3', '4', '5', '6', '7', '8', '9', '10'],
    datasets: [{
      label: 'Plan',
      data: [30, 70, 200, 300, 500, 800, 1500, 2900, 5000, 8000],
    }, {
      label: 'Reality',
      data: [0, 1, 30, 70, 80, 100, 50, 80, 40, 150],
    }],
  },
  options: { // optional
    yTickCount: 3,
    legendPosition: chartXkcd.config.positionType.upLeft
  }
})
```

### Customize chart by defining options

* `yTickCount`: customize tick numbers you want to see on the y axis \(default `3`\)
* `legendPosition`: specify where you want to place the legend. \(default `chartXkcd.config.positionType.upLeft`\) Possible values:
  * up left: `chart.Xkcd.positionType.upLeft`
  * up right: `chart.Xkcd.positionType.upLeft`

## XY chart

XY chart is used to plot points by specifing there XY coordinates.

You can also plot XY line chart by connecting the points.

### JS part

```text
  const svg = document.querySelector('.xy-chart');

  new chartXkcd.XY(svg, {
    title: 'Pokemon farms', //optional
    xLabel: 'Coodinate', //optional
    yLabel: 'Count', //optional
    data: {
      datasets: [{
        label: 'Pikachu',
        data: [{ x: 3, y: 10 }, { x: 4, y: 122 }, { x: 10, y: 100 }, { x: 1, y: 2 }, { x: 2, y: 4 }],
      }, {
        label: 'Squirtle',
        data: [{ x: 3, y: 122 }, { x: 4, y: 212 }, { x: -3, y: 100 }, { x: 1, y: 1 }, { x: 1.5, y: 12 }],
      }],
    },
    options: { //optional
      xTickCount: 5,
      yTickCount: 5,
      legendPosition: chartXkcd.config.positionType.upRight,
      showLine: false,
      timeFormat: undefined,
      dotSize: 1,
    },
  });
```

### Customize XY chart by defining options

* `xTickCount`: customize tick numbers you want to see on the x axis \(default `3`\)
* `yTickCount`: customize tick numbers you want to see on the y axis \(default `3`\)
* `legendPosition`: specify where you want to place the legend \(default `chartXkcd.config.positionType.upLeft`\) Possible values:
  * up left: `chart.Xkcd.positionType.upLeft`
  * up right: `chart.Xkcd.positionType.upLeft`
* `showLine`: connect the points with lines \(default: `false`\)
* `timeFormat`: specify the time format if the x values are time \(default `undefined`\) chart.xkcd use [dayjs](https://github.com/iamkun/dayjs) to format time, you can find the all the available formats [here](https://github.com/iamkun/dayjs/blob/dev/docs/en/API-reference.md#list-of-all-available-formats)
* `dotSize`: you can change size of the dots if you want \(default `1`\)

**Another example of XY chart: XY line chart with `timeFormat`**

## Bar chart

A bar chart provides a way of showing data values represented as vertical bars

### JS part

```text
const barChart = new chartXkcd.Bar(svg, {
  title: 'github stars VS patron number', // optional
  // xLabel: '', // optional
  // yLabel: '', // optional
  data: {
    labels: ['github stars', 'patrons'],
    datasets: [{
      data: [100, 2],
    }],
  },
  options: { // optional
    yTickCount: 2,
  },
});
```

### Customize chart by defining options

* `yTickCount`: customize tick numbers you want to see on the y axis

## Pie/Doughnut chart

### JS part

```text
const pieChart = new chartXkcd.Pie(svg, {
  title: 'What Tim made of', // optional
  data: {
    labels: ['a', 'b', 'e', 'f', 'g'],
    datasets: [{
      data: [500, 200, 80, 90, 100],
    }],
  },
  options: { // optional
    innerRadius: 0.5,
    legendPosition: chartXkcd.config.positionType.upRight,
  },
});
```

### Customize chart by defining options

* `innerRadius`: specify empty pie chart radius \(default: `0.5`\)
  * Want a pie chart? set `innerRadius` to `0`
* `legendPosition`: specify where you want to place the legend. \(default `chartXkcd.config.positionType.upLeft`\) Possible values:
  * up left: `chart.Xkcd.positionType.upLeft`
  * up right: \`chart.Xkcd.positionType.upLeft

