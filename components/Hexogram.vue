<template>
    <div class="statebinContainer">

    <div :id="'state-grid-map-' + race"></div>

    <div :id="'map-template-' + race" style="display: none;">
        <div class="key-wrap">
            <div class="title"><b>{{race == 'governors' ? 'Governor and lt. governor candidates' : 'State legislative candidates'}}</b><div style="font-size: 13px; line-height: 14px;top:5px;position: relative;">{{race == 'governors' ? '9.8%' : '11.4%'}} nationally</div></div>
            <ul class="key"></ul>
        </div>

            <svg viewBox="0 0 436 251" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:sketch="http://www.bohemiancoding.com/sketch/ns">
                <g stroke="none" stroke-width="1" fill="none" fill-rule="evenodd" sketch:type="MSPage">
                    <g class="map" sketch:type="MSLayerGroup" transform="translate(1.000000, 2.000000)" stroke-width="2" stroke="#FFFFFF" fill="#DDDDDD">
                        <g class="states" sketch:type="MSShapeGroup">
                            <path d="M35.5255888,0 L52.8460969,10 L52.8460969,30 L35.5255888,40 L18.2050808,30 L18.2050808,10 L35.5255888,0 Z" class="state-alaska"></path>
                            <path d="M416.576766,0 L433.897275,10 L433.897275,30 L416.576766,40 L399.256258,30 L399.256258,10 L416.576766,0 Z" class="state-maine"></path>
                            <path d="M364.615242,30 L381.93575,40 L381.93575,60 L364.615242,70 L347.294734,60 L347.294734,40 L364.615242,30 Z" class="state-vermont"></path>
                            <path d="M399.256258,30 L416.576766,40 L416.576766,60 L399.256258,70 L381.93575,60 L381.93575,40 L399.256258,30 Z" class="state-new-hampshire"></path>
                            <path d="M70.166605,60 L87.4871131,70 L87.4871131,90 L70.166605,100 L52.8460969,90 L52.8460969,70 L70.166605,60 Z" class="state-washington"></path>
                            <path d="M104.807621,60 L122.128129,70 L122.128129,90 L104.807621,100 L87.4871131,90 L87.4871131,70 L104.807621,60 Z" class="state-montana"></path>
                            <path d="M139.448637,60 L156.769145,70 L156.769145,90 L139.448637,100 L122.128129,90 L122.128129,70 L139.448637,60 Z" class="state-north-dakota"></path>
                            <path d="M174.089653,60 L191.410162,70 L191.410162,90 L174.089653,100 L156.769145,90 L156.769145,70 L174.089653,60 Z" class="state-minnesota"></path>
                            <path d="M208.73067,60 L226.051178,70 L226.051178,90 L208.73067,100 L191.410162,90 L191.410162,70 L208.73067,60 Z" class="state-wisconsin"></path>
                            <path d="M278.012702,60 L295.33321,70 L295.33321,90 L278.012702,100 L260.692194,90 L260.692194,70 L278.012702,60 Z" class="state-michigan"></path>
                            <path d="M347.294734,60 L364.615242,70 L364.615242,90 L347.294734,100 L329.974226,90 L329.974226,70 L347.294734,60 Z" class="state-new-york"></path>
                            <path d="M381.93575,60 L399.256258,70 L399.256258,90 L381.93575,100 L364.615242,90 L364.615242,70 L381.93575,60 Z" class="state-massachusetts"></path>
                            <path d="M416.576766,60 L433.897275,70 L433.897275,90 L416.576766,100 L399.256258,90 L399.256258,70 L416.576766,60 Z" class="state-rhode-island"></path>
                            <path d="M87.4871131,90 L104.807621,100 L104.807621,120 L87.4871131,130 L70.166605,120 L70.166605,100 L87.4871131,90 Z" class="state-idaho"></path>
                            <path d="M122.128129,90 L139.448637,100 L139.448637,120 L122.128129,130 L104.807621,120 L104.807621,100 L122.128129,90 Z" class="state-wyoming"></path>
                            <path d="M156.769145,90 L174.089653,100 L174.089653,120 L156.769145,130 L139.448637,120 L139.448637,100 L156.769145,90 Z" class="state-south-dakota"></path>
                            <path d="M191.410162,90 L208.73067,100 L208.73067,120 L191.410162,130 L174.089653,120 L174.089653,100 L191.410162,90 Z" class="state-iowa"></path>
                            <path d="M226.051178,90 L243.371686,100 L243.371686,120 L226.051178,130 L208.73067,120 L208.73067,100 L226.051178,90 Z" class="state-illinois"></path>
                            <path d="M260.692194,90 L278.012702,100 L278.012702,120 L260.692194,130 L243.371686,120 L243.371686,100 L260.692194,90 Z" class="state-indiana"></path>
                            <path d="M295.33321,90 L312.653718,100 L312.653718,120 L295.33321,130 L278.012702,120 L278.012702,100 L295.33321,90 Z" class="state-ohio"></path>
                            <path d="M329.974226,90 L347.294734,100 L347.294734,120 L329.974226,130 L312.653718,120 L312.653718,100 L329.974226,90 Z" class="state-pennsylvania"></path>
                            <path d="M364.615242,90 L381.93575,100 L381.93575,120 L364.615242,130 L347.294734,120 L347.294734,100 L364.615242,90 Z" class="state-new-jersey"></path>
                            <path d="M399.256258,90 L416.576766,100 L416.576766,120 L399.256258,130 L381.93575,120 L381.93575,100 L399.256258,90 Z" class="state-connecticut"></path>
                            <path d="M70.166605,120 L87.4871131,130 L87.4871131,150 L70.166605,160 L52.8460969,150 L52.8460969,130 L70.166605,120 Z" class="state-oregon"></path>
                            <path d="M104.807621,120 L122.128129,130 L122.128129,150 L104.807621,160 L87.4871131,150 L87.4871131,130 L104.807621,120 Z" class="state-nevada"></path>
                            <path d="M139.448637,120 L156.769145,130 L156.769145,150 L139.448637,160 L122.128129,150 L122.128129,130 L139.448637,120 Z" class="state-colorado"></path>
                            <path d="M174.089653,120 L191.410162,130 L191.410162,150 L174.089653,160 L156.769145,150 L156.769145,130 L174.089653,120 Z" class="state-nebraska"></path>
                            <path d="M208.73067,120 L226.051178,130 L226.051178,150 L208.73067,160 L191.410162,150 L191.410162,130 L208.73067,120 Z" class="state-missouri"></path>
                            <path d="M243.371686,120 L260.692194,130 L260.692194,150 L243.371686,160 L226.051178,150 L226.051178,130 L243.371686,120 Z" class="state-kentucky"></path>
                            <path d="M278.012702,120 L295.33321,130 L295.33321,150 L278.012702,160 L260.692194,150 L260.692194,130 L278.012702,120 Z" class="state-west-virginia"></path>
                            <path d="M312.653718,120 L329.974226,130 L329.974226,150 L312.653718,160 L295.33321,150 L295.33321,130 L312.653718,120 Z" class="state-virginia"></path>
                            <path d="M347.294734,120 L364.615242,130 L364.615242,150 L347.294734,160 L329.974226,150 L329.974226,130 L347.294734,120 Z" class="state-maryland"></path>
                            <path d="M381.93575,120 L399.256258,130 L399.256258,150 L381.93575,160 L364.615242,150 L364.615242,130 L381.93575,120 Z" class="state-delaware"></path>
                            <path d="M87.4871131,150 L104.807621,160 L104.807621,180 L87.4871131,190 L70.166605,180 L70.166605,160 L87.4871131,150 Z" class="state-california"></path>
                            <path d="M122.128129,150 L139.448637,160 L139.448637,180 L122.128129,190 L104.807621,180 L104.807621,160 L122.128129,150 Z" class="state-utah"></path>
                            <path d="M156.769145,150 L174.089653,160 L174.089653,180 L156.769145,190 L139.448637,180 L139.448637,160 L156.769145,150 Z" class="state-new-mexico"></path>
                            <path d="M191.410162,150 L208.73067,160 L208.73067,180 L191.410162,190 L174.089653,180 L174.089653,160 L191.410162,150 Z" class="state-kansas"></path>
                            <path d="M226.051178,150 L243.371686,160 L243.371686,180 L226.051178,190 L208.73067,180 L208.73067,160 L226.051178,150 Z" class="state-arkansas"></path>
                            <path d="M260.692194,150 L278.012702,160 L278.012702,180 L260.692194,190 L243.371686,180 L243.371686,160 L260.692194,150 Z" class="state-tennessee"></path>
                            <path d="M295.33321,150 L312.653718,160 L312.653718,180 L295.33321,190 L278.012702,180 L278.012702,160 L295.33321,150 Z" class="state-north-carolina"></path>
                            <path d="M329.974226,150 L347.294734,160 L347.294734,180 L329.974226,190 L312.653718,180 L312.653718,160 L329.974226,150 Z" class="state-south-carolina"></path>
                            <path d="M139.448637,180 L156.769145,190 L156.769145,210 L139.448637,220 L122.128129,210 L122.128129,190 L139.448637,180 Z" class="state-arizona"></path>
                            <path d="M174.089653,180 L191.410162,190 L191.410162,210 L174.089653,220 L156.769145,210 L156.769145,190 L174.089653,180 Z" class="state-oklahoma"></path>
                            <path d="M208.73067,180 L226.051178,190 L226.051178,210 L208.73067,220 L191.410162,210 L191.410162,190 L208.73067,180 Z" class="state-louisiana"></path>
                            <path d="M243.371686,180 L260.692194,190 L260.692194,210 L243.371686,220 L226.051178,210 L226.051178,190 L243.371686,180 Z" class="state-mississippi"></path>
                            <path d="M278.012702,180 L295.33321,190 L295.33321,210 L278.012702,220 L260.692194,210 L260.692194,190 L278.012702,180 Z" class="state-alabama"></path>
                            <path d="M312.653718,180 L329.974226,190 L329.974226,210 L312.653718,220 L295.33321,210 L295.33321,190 L312.653718,180 Z" class="state-georgia"></path>
                            <path d="M18.2050808,210 L35.5255888,220 L35.5255888,240 L18.2050808,250 L0.884572681,240 L0.884572681,220 L18.2050808,210 Z" class="state-hawaii"></path>
                            <path d="M191.410162,210 L208.73067,220 L208.73067,240 L191.410162,250 L174.089653,240 L174.089653,220 L191.410162,210 Z" class="state-texas"></path>
                            <path d="M295.33321,210 L312.653718,220 L312.653718,240 L295.33321,250 L278.012702,240 L278.012702,220 L295.33321,210 Z" class="state-florida"></path>
                        </g>
                    </g>
                </g>
            </svg>
        </div>

    </div>
</template>

<script>

// Code from https://github.com/nprapps/dailygraphics licensed MIT

/* eslint-disable */

import governors from '~/assets/governors_map.csv';
import legislators from '~/assets/legislators_map.csv';
import { intcomma, postal, apstate } from 'journalize';
import * as d3 from 'd3';
import * as _ from 'lodash';
import { legendColor } from 'd3-svg-legend';

export default {
    props: ['race'],
    mounted() {
        let vm = this;

        var COLORS = {
                    nullGray: '#b2b0b0',

                    red1: '#6C2315',
                    red2: '#A23520',
                    red3: '#D8472B',
                    red4: '#E27560',
                    red5: '#ECA395',
                    red6: '#F5D1CA',

                    orange1: '#714616',
                    orange2: '#AA6A21',
                    orange3: '#E38D2C',
                    orange4: '#EAAA61',
                    orange5: '#F1C696',
                    orange6: '#F8E2CA',

                    yellow1: '#77631B',
                    yellow2: '#B39429',
                    yellow3: '#EFC637',
                    yellow4: '#F3D469',
                    yellow5: '#F7E39B',
                    yellow6: '#FBF1CD',

                    teal1: '#0B403F',
                    teal2: '#11605E',
                    teal3: '#17807E',
                    teal4: '#51A09E',
                    teal5: '#8BC0BF',
                    teal6: '#C5DFDF',

                    blue1: '#28556F',
                    blue2: '#3D7FA6',
                    blue3: '#51AADE',
                    blue4: '#7DBFE6',
                    blue5: '#A8D5EF',
                    blue6: '#D3EAF7'};

        var scale = d3.scaleThreshold()
            .domain([0, 0.1, 0.2, 0.3, 0.4])
            .range(['white', COLORS['blue6'], COLORS['blue5'], COLORS['blue4'], COLORS['blue3'], COLORS['blue2'], COLORS['blue1']]);
        
        var MAP_TEMPLATE_ID = '#map-template-' + vm.race;
        var LABELS = {legend_labels: scale.domain(), max_label: 0.5};
        var DEFAULT_WIDTH = 300;
        var MOBILE_THRESHOLD = 500;
        var isMobile = false;

        this.$nextTick(() => {

            var classify = function(str) {
                return postal(str,true).toLowerCase()
                    .replace(/\s+/g, '-')           // Replace spaces with -
                    .replace(/[^\w\-]+/g, '')       // Remove all non-word chars
                    .replace(/\-\-+/g, '-')         // Replace multiple - with single -
                    .replace(/^-+/, '')             // Trim - from start of text
                    .replace(/-+$/, '');            // Trim - from end of text
            }

            var render = function(containerWidth) {
                if (!containerWidth) {
                    containerWidth = DEFAULT_WIDTH;
                }

                if (containerWidth <= MOBILE_THRESHOLD) {
                    isMobile = true;
                } else {
                    isMobile = false;
                }
                var isNumeric = true;

                renderStateGridMap({
                    container: '#state-grid-map-' + vm.race,
                    width: containerWidth,
                    data: (vm.race === 'governors' ? governors : legislators).map(row => {
                        return {
                            state_name: row.state,
                            percent: row[(vm.race === 'governors' ?
                                'pct_governor/lieutenant_governor_out_of_state' :
                                'pct_state_house/assembly/senate_out_of_state')]
                        };
                    }),
                    isNumeric: isNumeric,
                    valueColumn: 'percent'
                });         
            }

            /*
             * Render a state grid map.
             */
            var renderStateGridMap = function(config) {
                var valueColumn = config.valueColumn;

                // Clear existing graphic (for redraw)
                var containerElement = d3.select(config['container']);
                containerElement.html('');

                config.width = containerElement.offsetWidth;

                // Copy map template
                var template = d3.select(MAP_TEMPLATE_ID);
                containerElement.html(template.html());

                // Extract categories from data
                var categories = [];

                // Default: Return sorted array of categories
                 _.each(config['data'], function(state) {
                    if (state[valueColumn] != null) {
                        categories.push(state[valueColumn]);
                    }
                });

                categories = d3.set(categories).values().sort();

                // Create legend
                var legendWrapper = containerElement.select('.key-wrap');
                var legendElement = containerElement.select('.key');

                legendWrapper.classed('linear-scale', true);

                // Append legend widths for all vars            
                var tempKey = 0;

                _.each(scale.domain(), function(key, i) {

                    var keyItem = legendElement.append('li')
                        .classed('key-item', true)

                    keyItem.append('b')
                        .style('background', scale(key))

                    tempKey = key;

                    if (key === 0) {
                        keyItem.append('label')
                            .text('' + key + '%') 
                    } else {
                    keyItem.append('label')
                        .text(key * 100 + '%')
                        // .text('$' + intcomma(key/1000) + 'k')
                    }

                    // Add the upper bound label on numeric scale
                    if (config['isNumeric'] && i == scale.domain().length - 1) {
                        if (LABELS['max_label'] && LABELS['max_label'] !== '') {
                            keyItem.append('label')
                                .attr('class', 'end-label')
                                .text(intcomma(LABELS['max_label']*100) + '%');
                        }
                    }
                });

                // Select SVG element
                var chartElement = containerElement.select('svg');

                // resize map (needs to be explicitly set for IE11)
                chartElement.attr('width', config['width'])
                    .attr('height', function() {
                        var s = d3.select(this);
                        var viewBox = s.attr('viewBox').split(' ');
                        return Math.floor(config['width'] * parseInt(viewBox[3]) / parseInt(viewBox[2]));
                    });

                // Set state colors
                _.each(config['data'], function(state) {
                    if (state[valueColumn] !== null) {
                        var stateClass = 'state-' + classify(state['state_name']);
                        var categoryClass = 'category-' + classify(state[valueColumn]);

                        chartElement.select('.' + stateClass)
                            .attr('class', stateClass + ' state-active ' + categoryClass);
                        if (state['state_name'] === 'DC') {
                             chartElement.select('.' + stateClass)
                                .attr('fill', '#9b9b9b');
                        } else if (state[valueColumn] > 100000) {
                            chartElement.select('.' + stateClass)
                                .attr('fill', COLORS['blue1']);
                        } else {
                            chartElement.select('.' + stateClass)
                                .attr('fill', scale(state[valueColumn]));
                        }
                    }
                });

                // Draw state labels
                chartElement.append('g')
                    .selectAll('text')
                        .data(config['data'])

                    .enter().append('text')
                        .attr('text-anchor', 'middle')
                        .text(function(d) {
                            if (isMobile) {
                                return d['state_name'];
                            } else {
                                return apstate(postal(d['state_name'],true));
                            }
                            
                        })
                        .attr('class', function(d) {
                            return d[valueColumn] !== null ? 'category-' + classify(d[valueColumn]) + ' label label-active' : 'label';
                        })
                        .attr('x', function(d) {
                            var className = '.state-' + classify(d['state_name']);
                            var tileBox = chartElement.select(className).node().getBBox();


                            return tileBox['x'] + tileBox['width'] * 0.52;
                        })
                        .attr('y', function(d) {
                            var className = '.state-' + classify(d['state_name']);
                            var tileBox = chartElement.select(className).node().getBBox();
                            var textBox = d3.select(this).node().getBBox();
                            var textOffset = textBox['height'] / 2.5;
                            
                            if (isMobile) {
                                textOffset -= 1;
                            }
                            
                            return (tileBox['y'] + tileBox['height'] * 0.5) + textOffset;
                        });
            }

            render(window.innerWidth);
            window.addEventListener('resize', function() {
                render(window.innerWidth);
            });

        });
    }
};
</script>

<style lang="less">

.source {
    font-size: 70%;
    line-height: 120%;
    color: #666;
    margin-top: 15px;
    margin-left: 7px;
    text-align: center;
    word-wrap: break-word;
}

.title {
    font-size: 16px;
    margin-bottom: 5px;
    color: #666;
    text-align: center;
    word-wrap: break-word;
    line-height: 21px;
}

.key-wrap {
    .key {
        margin: 0 0 10px 0;
        padding: 0;
        list-style-type: none;

        .key-item {
            display: inline-block;
            margin: 0 18px 0 0;
            padding: 0;
            line-height: 15px;
        }
        .key-item b {
            display: inline-block;
            width: 15px;
            height: 15px;
            margin-right: 6px;
            float: left;
        }
        .key-item label {
            white-space: nowrap;
            font-size: 12px;
            font-weight: normal;
            -webkit-font-smoothing: antialiased;
        }
    }

    &.linear-scale {
        transform-origin: 50% 50%;
        text-align: center;
        font-size: 12px;

        h3 {
            margin-bottom: 10px;
        }

        .key {
            .key-item {
                margin: 0 1px 0 0;
                position: relative;

            }

            .key-item b {
                width: 40px;
                height: 10px;
                margin-right: 0;

            }

            .key-item label {
                position: absolute;
                bottom: -20px;
                right: 75%;

                &.end-label {
                    left: auto;
                    right: -25%;

                }
            }
        }
    }
}

.state {
    fill: #eee;
}

.label {
    fill: #979797;
    font-size: 13px;
}

.label-active {
    fill: #fff;
    font-size: 12px;
}

@media screen and (max-width: 500px){
    .label {
        font-size: 13px;
    }
}

@media screen and (min-width: 500px){
    .label {
        font-size: 11px;
    }
}

</style>
