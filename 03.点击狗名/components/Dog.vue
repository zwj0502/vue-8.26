<template>
   <div>
    <div class="my_div">
        <img :src="imgUl" alt="" />
        <p :style="{ backgroundColor: colorStr }" @click="btn(userName)">{{userName}}</p>
    </div>
   
   
   </div>
</template>

<script>
    export default {
        props: ['imgUl', 'userName'],
        data() {
            return {
                colorStr: "",
                gouming:''
            };
        },
        methods: {
            btn(userName) {
                this.colorStr = `rgb(${Math.floor(Math.random() * 256)}, ${Math.floor(
                    Math.random() * 256
                )}, ${Math.floor(Math.random() * 256)})`;
                this.gouming = this.userName
            },
        },
    };
</script>

<style>
    .my_div {
        width: 200px;
        border: 1px solid black;
        text-align: center;
        float: left;
    }

    .my_div img {
        width: 100%;
        height: 200px;
    }
</style>