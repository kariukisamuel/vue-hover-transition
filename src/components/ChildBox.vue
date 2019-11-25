<template>

    <div class="child-box" :style="boxStyle">
        <p >{{ item.text }}</p>
    </div>
</template>
<script>
export default {
    name: 'ChildBox',
    props: ['item', 'index'],
    computed:{
      boxStyle(){
          return{
           '--i': this.index,
           'backgroundColor': this.item.color
          }
      }
     
    }

}
</script>
<style scoped lang="scss">
.child-box {
    width: 350px;
    height: 50vh;
    align-items: center;
    justify-content: center;
    display:flex;
    p{
      color:#fff;
      font-size:20px;
    }
}
</style>