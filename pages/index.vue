<template>
    <div>
        <center>
            <h3 style="padding-bottom: 10px">Campaign cash raised from out-of-state donors</h3>
        </center>

        <div class="group">
            <div class="left">
                <hexogram race="governors" />
            </div>
            <div class="left">
                <hexogram race="legislators" />
            </div>
        </div>

        <center>
            <div class="key-wrap">
                <ul class="key">
                    <li class="key-item"><b style="background: rgb(221, 221, 221)"></b>
                        <label style="bottom:2px; position: relative; font-size:13px">insufficient data</label>
                    </li>
                </ul>
            </div>
        </center>

        <p class="source">Source: Center for Public Integrity analysis of National Institute on Money in Politics data</p>
    </div> 
</template>

<script>
import Statebin from '~/components/Statebin.vue';
import Hexogram from '~/components/Hexogram.vue';

export default {
    components: {
        Statebin,
        Hexogram
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
.left {
    float: left;
    width: 49%;
}
.group:after {
  content: "";
  display: table;
  clear: both;
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
    .left {
        float: none;
        width: 100%;
    }
}
</style>