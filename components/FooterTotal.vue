<template>
  <footer>
    Suma total de contadores: <strong>{{ total }}</strong>
  </footer>
</template>

<script>
import { mapGetters } from 'vuex';
export default {
  computed:{ ...mapGetters(['totalSum']), total(){ return this.totalSum } }
}
</script>