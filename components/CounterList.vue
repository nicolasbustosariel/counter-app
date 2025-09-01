<template>
  <div class="listado-contadores">
    <transition-group name="fade" tag="div" class="list-grid">
      <CounterItem
        v-for="c in counters"
        :key="c.id"
        :counter="c"
        @inc="INC(c.id)"
        @dec="DEC(c.id)"
        @remove="REMOVE_COUNTER(c.id)"
        @rename="(name) => RENAME({ id: c.id, name })"
      />
    </transition-group>

    <!-- Si no hay contadores visibles -->
    <p v-if="counters.length === 0" class="empty">
      No hay contadores que coincidan con el filtro.
    </p>
  </div>
</template>

<script>
import { mapGetters, mapMutations } from 'vuex'
import CounterItem from './CounterItem.vue'

export default {
  components: { CounterItem },
  computed: {
    ...mapGetters(['visible']),  
    counters() {
      return this.visible
    }
  },
  methods: {
    ...mapMutations(['INC', 'DEC', 'REMOVE_COUNTER', 'RENAME'])
  }
}
</script>


