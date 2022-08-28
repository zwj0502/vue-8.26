<template>
  <div class="my_div">
    <img
      :src="imgUl"
      alt=""
    />
    <p>{{userName}}</p>
  </div>
</template>

<script>
export default {
    props:['imgUl','userName']
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