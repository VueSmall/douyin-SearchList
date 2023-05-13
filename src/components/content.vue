<!--author:steam-404-->
<script>
import axios from "axios";

export default {
    data() {
        return {
            url: 'https://apis.tianapi.com/douyinhot/index?key=7c7f78805e649863b93ea32473f62fa3',
            data_list: '',
            status_code: '',
        }
    },
    methods: {
        get_douyin_hot_list() {
            axios.post(this.url, {}).then(response => {
                this.data_list = response.data.result.list
            }).catch(error => {
                console.log(error)
            })
        }
    },
    mounted() {
        this.get_douyin_hot_list()
    }
}
</script>

<template>
    <div id="content">
        <ul>
            <li v-for="value in this.data_list">
<!--                {{ value.hotindex }}-->
                <span v-show="value.label===1" style="color: #ff3767">新榜</span>
                <span v-show="value.label===2" style="color: #5352ff">荐榜</span>
                <span v-show="value.label===3" style="color: #fb20ff">热榜</span>
                {{ value.word }}
            </li>
        </ul>
    </div>
</template>

<style>
* {

}
#content{
    text-align: right;
}
li {
    list-style: none;
    margin: 1vh;
}
span{
    font-family: Arial,serif;
}
</style>