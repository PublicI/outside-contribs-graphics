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

<style>
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