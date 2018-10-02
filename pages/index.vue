<template>
    <div class="statebinContainer">
        <svg style="width:100%;height:60px">
            <g class="legendLinear" transform="translate(20,20)">
            </g>
        </svg>

        <div class="statebins">
            <div :style="'top:' + bin.y + 'px;left:' + bin.x + 'px;background-color:' + bin.color" class="statebin" v-for="bin in bins" v-tooltip="{ content: '<b>' + bin.name + '</b><br>' + Math.round(bin.percent*100) + ' percent<br>' + bin.number + ' workers' }">
                {{bin.abbrev}}
            </div>
        </div>

        <!-- <p class="source">Source: AARP analysis of U.S. Census Bureau data</p> -->
    </div>
</template>

<script>
import stats from '~/assets/governors_map.csv';
import { intword, intcomma, postal } from 'journalize';
import * as d3 from 'd3';
import { legendColor } from 'd3-svg-legend';

export default {
    data() {
        return {
            stats: stats.map(row => {
                console.log(row);
                return {
                    state: row.state,
                    percent: +row['pct_governor/lieutenant_governor_out_of_state'],
                    number: +row['contributions_18_governor/lieutenant_governor_out_of_state']
                };
            }),
            grid: [
                '                                  ME',
                '                   WI          VT NH',
                '    WA ID MT ND MN IL MI    NY MA',
                '    OR NV WY SD IA IN OH PA NJ CT RI',
                '    CA UT CO NE MO KY WV VA MD DE',
                '       AZ NM KS AR TN NC SC',
                '             OK LA MS AL GA',
                '    HI AK    TX             FL'
            ]
        };
    },
    mounted() {
        this.$nextTick(() => {
            let legendLinear = legendColor()
                .shapeWidth(30)
                .cells([0.1, 0.2, 0.3, 0.4, 0.5])
                .orient('horizontal')
                .labelFormat('.0%')
                .scale(this.scale());

            d3.select('.legendLinear').call(legendLinear);
        });
    },
    methods: {
        scale() {
            return d3
                .scaleSequential(d3.interpolateYlOrBr)
                .domain([0, 0.5]);
        }
    },
    computed: {
        bins() {
            let scale = this.scale();

            let binsRef = {};
            let bins = [];

            let boxSize = 26;

            let re = /\w+/g;

            this.grid.forEach(function(line, i) {
                let m;
                while ((m = re.exec(line))) { // eslint-disable-line no-cond-assign
                    let state = {
                        abbrev: m[0],
                        x: m.index / 3 * boxSize - (boxSize + 2),
                        y: i * boxSize,
                        color: null,
                        name: null,
                        percent: null,
                        number: null
                    };

                    bins.push(state);

                    binsRef[state.abbrev] = state;
                }
            });

            this.stats.forEach(function(d) {
                let abbrev = d.state; // postal(d.state);
                if (abbrev in binsRef) {
                    binsRef[abbrev].color = scale(d.percent);
                    binsRef[abbrev].name = d.state;
                    binsRef[abbrev].percent = d.percent;
                    binsRef[abbrev].number =
                        d.number >= 1000000
                            ? intword(d.number)
                            : intcomma(d.number);
                }
            });

            return bins;
        }
    }
};
</script>

<style>
.statebins {
    position: relative;
    width: 300px;
    height: 220px;
    margin-top: -19px;
    text-shadow: 1px 1px black;
}

.statebin {
    position: absolute;
    width: 24px;
    height: 24px;
    background-color: #eee;
    color: white;
    text-align: center;
    font-size: 12px;
    line-height: 20px;
    padding-top: 1px;
}

.tooltip {
    display: block !important;
    z-index: 10000;
}

.tooltip .tooltip-inner {
    background: white;
    color: black;
    border-radius: 2px;
    padding: 5px 10px 4px;
    font-family: tablet-gothic-n2,tablet-gothic,Helvetica Neue,Helvetica,Arial,sans-serif;
    font-size: 16px;
    line-height: 19px;
}

.tooltip .tooltip-arrow {
    width: 0;
    height: 0;
    border-style: solid;
    position: absolute;
    margin: 5px;
    border-color: white;
    z-index: 1;
}

.tooltip[x-placement^="top"] {
    margin-bottom: 5px;
}

.tooltip[x-placement^="top"] .tooltip-arrow {
    border-width: 5px 5px 0 5px;
    border-left-color: transparent !important;
    border-right-color: transparent !important;
    border-bottom-color: transparent !important;
    bottom: -5px;
    left: calc(50% - 5px);
    margin-top: 0;
    margin-bottom: 0;
}

.tooltip[x-placement^="bottom"] {
    margin-top: 5px;
}

.tooltip[x-placement^="bottom"] .tooltip-arrow {
    border-width: 0 5px 5px 5px;
    border-left-color: transparent !important;
    border-right-color: transparent !important;
    border-top-color: transparent !important;
    top: -5px;
    left: calc(50% - 5px);
    margin-top: 0;
    margin-bottom: 0;
}

.tooltip[x-placement^="right"] {
    margin-left: 5px;
}

.tooltip[x-placement^="right"] .tooltip-arrow {
    border-width: 5px 5px 5px 0;
    border-left-color: transparent !important;
    border-top-color: transparent !important;
    border-bottom-color: transparent !important;
    left: -5px;
    top: calc(50% - 5px);
    margin-left: 0;
    margin-right: 0;
}

.tooltip[x-placement^="left"] {
    margin-right: 5px;
}

.tooltip[x-placement^="left"] .tooltip-arrow {
    border-width: 5px 0 5px 5px;
    border-top-color: transparent !important;
    border-right-color: transparent !important;
    border-bottom-color: transparent !important;
    right: -5px;
    top: calc(50% - 5px);
    margin-left: 0;
    margin-right: 0;
}

.tooltip.popover .popover-inner {
    background: #f9f9f9;
    color: black;
    padding: 24px;
    border-radius: 2px;
    box-shadow: 0 5px 30px rgba(black, .1);
}

.tooltip.popover .popover-arrow {
    border-color: #f9f9f9;
}

.tooltip[aria-hidden='true'] {
    visibility: hidden;
    opacity: 0;
    transition: opacity .15s, visibility .15s;
}

.tooltip[aria-hidden='false'] {
    visibility: visible;
    opacity: 1;
    transition: opacity .15s;
}
.source {
    font-size: 14px;
    line-height: 16px;
    color: #666;
    margin-bottom: 15px;
}

.legendLinear .label {
    font-family: tablet-gothic-n2,tablet-gothic,Helvetica Neue,Helvetica,Arial,sans-serif;
    font-size: 13px;
    line-height: 16px;
    fill: rgb(100,100,100);
}
</style>