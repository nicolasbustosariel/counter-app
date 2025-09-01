<template>
  <article class="contador">
    <input class="name" :value="counter.name" @change="onRename" :maxlength="20"/>
    <div class="valor">{{ counter.value }}</div>
    <div class="acciones">
      <button class="btn" @click="$emit('dec')">-</button>
      <button class="btn" @click="$emit('inc')">+</button>
<button class="btn danger" @click="$emit('remove')" title="Eliminar">
  <svg width="24" height="24" viewBox="0 0 24 24" fill="none" aria-hidden="true" style="display:block; margin:auto;">
    <path d="M3 6h18M8 6V4a2 2 0 0 1 2-2h4a2 2 0 0 1 2 2v2m2 0v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6h16z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    <path d="M10 11v6M14 11v6" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
  </svg>
</button>
    </div>
  </article>
</template>

<script>
export default {
  props:{ counter:{ type:Object, required:true } },
  methods:{
    onRename(e){ this.$emit('rename', e.target.value); }
  }
}
</script>


