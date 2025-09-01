<template>
  <fieldset class="card">
    <legend>Ordenar</legend>
    <label>
      Campo:
      <select v-model="key" @change="apply">
        <option value="name">Nombre</option>
        <option value="value">Valor</option>
      </select>
    </label>
    <label>
      Dirección:
      <select v-model="dir" @change="apply">
        <option value="asc">Asc</option>
        <option value="desc">Desc</option>
      </select>
    </label>
  </fieldset>
</template>

<script>
import { mapState, mapMutations } from 'vuex';
export default {
  computed:{
    ...mapState(['sort']),
    key:{ get(){ return this.sort.key }, set(v){ this.$data._key=v } },
    dir:{ get(){ return this.sort.dir }, set(v){ this.$data._dir=v } },
  },
  data:()=>({_key:'name',_dir:'asc'}),
  mounted(){ this._key=this.sort.key; this._dir=this.sort.dir; },
  methods:{
    ...mapMutations(['SET_SORT']),
    apply(){ this.SET_SORT({ key: this._key, dir: this._dir }); }
  }
}
</script>

