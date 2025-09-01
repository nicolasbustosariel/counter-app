<template>
  <div class="backdrop" @click.self="$emit('close')">
    <div class="modal">
      <h3>Nuevo contador</h3>
      <input
        v-model.trim="name"
        :maxlength="20"
        placeholder="Nombre (máx. 20)"
        @keyup.enter="confirm"
      />
      <div class="row">
        <button class="btn" @click="$emit('close')">Cancelar</button>
        <button class="btn primary" :disabled="!valid" @click="confirm">Agregar</button>
      </div>
      <small v-if="name && !valid" class="err">El nombre debe tener 1–20 caracteres.</small>
    </div>
  </div>
</template>

<script>
export default {
  data:()=>({ name:'' }),
  computed:{ valid(){ return this.name.length > 0 && this.name.length <= 20; } },
  methods:{
    confirm(){ if(this.valid) this.$emit('confirm', this.name); }
  }
}
</script>

