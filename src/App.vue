<template>
  <div id="app" >
    <div class="">
      <section class="tab">
        <ul class="tab__label">
          <li v-for="(item) of items" :key="item.id">
            <a href="#"  @click.prevent="activate(item.id)"
            :class="{active:active === item.id}">{{item.title}}</a>
          </li>
        </ul>

        <div class="tab__content" v-show="active === 1">
          サイトの情報。サイトの情報。
        </div>
        <div class="tab__content" v-show="active === 2">
          商品情報。商品情報。
        </div>
        <div class="tab__content" v-show="active === 3">
          お問い合わせ。お問い合わせ。
        </div>
      </section>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
  },
  data(){
    return{
      active:1,
      items:[
        {id:1,title:'サイトの情報'},
        {id:2,title:'商品情報'},
        {id:3,title:'お問い合わせ'}
      ]
    }
  },
  methods:{
    activate(id){
      console.log(id)
      this.active = id
    }
  }
}
</script>

<style scoped lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.border{
  &_blue{
    border:1px blue solid 
  }
}
.background{
  &_primary{
    background-color:$color-primary ;
  }
}
</style>
