<template>
  <div>
      <h2>
          {{msg}}
      </h2><hr/>
      <h3>{{$store.state.count}}--{{count}}</h3>
      <p>
          <button @click="$store.commit('add',10)">+</button>
          <button @click="reduce">-</button>
      </p>
      <p>
          <button @click="addActions">+</button>
          <button @click="reduceActions">-</button>
      </p>
  </div>
</template>

<<script>
import store from '@/vuex/store';
import { mapState,mapMutations,mapGetters,mapActions } from 'vuex';
export default{
    data(){
        return{
            msg:'hello vuex'
        }
    },
    // computed:{
    //     count(){
    //         return this.$store.state.count;
    //     }
    // },


    // computed:mapState({
    //     count:state=>state.count
    // }),

    computed:{
        ...mapState(['count']),
        // count(){
        //     this.$store.getters.count;
        // }

        // ...mapGetters(['count'])
    },
    methods:{
        ...mapMutations(['add','reduce']),
        ...mapActions(['addActions','reduceActions'])
    },
    store
}
</script>

