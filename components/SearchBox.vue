<template>
  <label class="card">
    Buscar:
    <input type="text" v-model.trim="q" maxlength="20" @input="SET_SEARCH(q)" placeholder="por nombre..." />
  </label>
</template>

<script>
import { mapMutations } from 'vuex';
export default {
  data:()=>({ q:'' }),
  methods:{ ...mapMutations(['SET_SEARCH']) }
}
</script>

