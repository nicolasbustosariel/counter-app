<template>
  <fieldset class="filtros">
    <legend>Filtrar</legend>
    <label>
      Tipo:
      <select v-model="type" @change="apply">
        <option :value="null">Ninguno</option>
        <option value="gt">Mayores a</option>
        <option value="lt">Menores a</option>
      </select>
    </label>
    <label>
      x:
      <input type="number" v-model.number="x" min="0" max="20" @input="apply"/>
    </label>
    <button class="btn" @click="CLEAR_FILTERS">Borrar filtros</button>
  </fieldset>
</template>

<script>
import { mapState, mapMutations } from 'vuex';
export default {
  computed:{
    ...mapState(['filter']),
    type:{ get(){ return this.filter.type }, set(v){ this.$data._type=v } },
    x:{ get(){ return this.filter.x }, set(v){ this.$data._x=v } },
  },
  data:()=>({_type:null,_x:null}),
  mounted(){ this._type=this.filter.type; this._x=this.filter.x; },
  methods:{
    ...mapMutations(['SET_FILTER','CLEAR_FILTERS']),
    apply(){ this.SET_FILTER({ type: this._type, x: (this._x ?? null) }); }
  }
}
</script>

