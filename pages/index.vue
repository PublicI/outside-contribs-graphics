<template>
    <div>
        <div style="float: left">
            <statebin race="governors" />
        </div>
        <div style="float: left">
            <statebin race="legislators" />
        </div>
    </div>
</template>

<script>
import Statebin from '~/components/Statebin.vue';

export default {
    components: {
        Statebin
    }
};
</script>

<style>

</style>