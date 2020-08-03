<template>
    <button :class="{checked}" @click="toggle">
           <span>

           </span>

    </button>
</template>

<script lang='ts'>
    import {ref} from 'vue';

    export default {
        setup() {
            const checked = ref(false);
            const toggle =  () => {
                checked.value = !checked.value;
            };
            return {checked, toggle};
        }
    };
</script>

<style lang='scss' scoped>
    $h: 22px;
    $h2: $h - 4px;
    button {
        height: $h;
        width: $h*2;
        border: none;
        background: #cccccc;
        border-radius: $h/2;
        position: relative;

    }

    span {
        height: $h2;
        width: $h2;
        border-radius: $h2/2;
        background: white;
        position: absolute;
        top: 2px;
        left: 2px;
      transition: left 200ms ;
    }
    button.checked{
      background: #2D8CF0;
    }
    button.checked > span {
        left: calc(100% - #{$h2} - 2px);
    }
</style>
