<template>
  <div id="app">
    <editor :options="editorOptions" mode="wysiwyg"/>
    <line-chart :data="chartData" :options="chartOptions"/>
  </div>
</template>

<script>
import "tui-chart/dist/tui-chart.css";
import { lineChart } from "@toast-ui/vue-chart";

import "tui-editor/dist/tui-editor.css";
import "tui-editor/dist/tui-editor-contents.css";
import "codemirror/lib/codemirror.css";
import { Editor } from "@toast-ui/vue-editor";

export default {
  name: "App",
  data() {
    return {
      editorOptions: {
        minHeight: "200px",
        useCommandShortcut: true,
        useDefaultHTMLSanitizer: true,
        hideModeSwitch: true,
        toolbarItems: [
          "heading",
          "bold",
          "italic",
          "strike",
          "divider",
          "hr",
          "quote",
          "divider",
          "ul",
          "ol",
          "task",
          "indent",
          "outdent",
          "divider",
          "table",
          "image",
          "link",
          "divider"
        ]
      },
      chartData: {
        categories: [
          "01/01/2016",
          "02/01/2016",
          "03/01/2016",
          "04/01/2016",
          "05/01/2016",
          "06/01/2016",
          "07/01/2016",
          "08/01/2016",
          "09/01/2016",
          "10/01/2016",
          "11/01/2016",
          "12/01/2016"
        ],
        series: [
          {
            name: "Seoul",
            data: [
              -3.5,
              -1.1,
              4.0,
              11.3,
              17.5,
              21.5,
              24.9,
              25.2,
              20.4,
              13.9,
              6.6,
              -0.6
            ]
          },
          {
            name: "Seattle",
            data: [
              3.8,
              5.6,
              7.0,
              9.1,
              12.4,
              15.3,
              17.5,
              17.8,
              15.0,
              10.6,
              6.4,
              3.7
            ]
          }
        ]
      },
      chartOptions: {
        chart: {
          width: 800,
          height: 540,
          title: "24-hr Average Temperature"
        },
        yAxis: [
          {
            title: "Temperature (Celsius)",
            pointOnColumn: true
          },
          {
            title: "Percent (%)",
            pointOnColumn: true,
            min: 0,
            max: 100,
            suffix: "%"
          }
        ],
        xAxis: {
          title: "Month",
          type: "datetime",
          dateFormat: "MM/dd"
        },
        series: {
          showDot: false,
          zoomable: false
        }
      }
    };
  },
  mounted() {},
  components: {
    editor: Editor,
    "line-chart": lineChart
  },
  methods: {}
};
</script>

