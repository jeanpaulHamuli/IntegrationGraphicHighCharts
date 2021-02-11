<template>
    <div>
        <p>Jean-Paul</p>
        <div id="chartDiv" style="width: 100%; height: 400px;"></div>
    </div>
</template>
 
<script>
    import * as JSC from "jscharting";
 
    JSC.defaults({ baseUrl: './js/jsc/' });
 
export default {
    mounted(){
        this.graphic();
    },
     methods: {
        graphic: function(){
            const chart = new JSC.Chart("chartDiv", {
                debug: false, 
                type: "gauge" , 
                legend_visible: false, 
                yAxis: { 
                  line_visible: false, 
                  defaultTick_label_text: '%value%', 
                  scale_range: [0, 100] 
                }, 
                defaultSeries: { 
                  type: 'column roundCaps', 
                  angle: { sweep: 360, start: -90 }, 
                  shape: { 
                    innerSize: '70%', 
                    padding: 0.1, 
                    label: { 
                      text: 
                        'Notice exceeding activity<br/>goals at a glance', 
                      verticalAlign: 'middle'
                    } 
                  } 
                }, 
                defaultTooltip_enabled: false, 
                series: [ 
                  { 
                    palette: [ 
                      '#E10715', 
                      '#3FDC00', 
                      '#3EBAE1'
                    ], 
                    defaultPoint: { label_text: '%yValue%' }, 
                    points: [['value', 5]] 
                  } 
                ], 
                toolbar: { 
                  defaultItem: { position: 'top' }, 
                } 
            });
        },
        
     }
}
</script> 
 
