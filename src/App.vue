<!--Author:VueSmall-->
<script>
import {defineComponent} from "vue";
import count from '@/components/count.vue'
import Count from "@/components/count.vue";
export default defineComponent({
    components: {Count},
    mounted() {
        count
    }
})
</script>
<template>
  <p>VueSmall</p>
  <count></count>
</template>
<style>
*{
    text-align: center;
}
</style>