<script setup>
import { reactive } from 'vue';

const filters = reactive({
  checkIn: '2026-12-01',
  checkOut: '2026-12-02',
  roomType: 'all',
  onlyAvailable: true
});
</script>

<template>
  <div class="card border-0 shadow-sm rounded-4 p-3 p-md-4 mb-4">
    <div class="row g-3 align-items-end">
      <div class="col-md-3">
        <label class="form-label small fw-semibold text-muted">Érkezés</label>
        <input type="date" class="form-control" v-model="filters.checkIn" />
      </div>

      <div class="col-md-3">
        <label class="form-label small fw-semibold text-muted">Távozás</label>
        <input type="date" class="form-control" v-model="filters.checkOut" />
      </div>

      <div class="col-md-3">
        <label class="form-label small fw-semibold text-muted">Szobatípus</label>
        <select class="form-select" v-model="filters.roomType">
          <option value="all">Mindegyik</option>
          <option value="EGYÁGYAS">Egyágyas</option>
          <option value="KÉTÁGYAS">Kétágyas</option>
          <option value="LAKOSZTÁLY">Lakosztály</option>
        </select>
      </div>

      <div class="col-md-3 pb-md-2">
        <div class="form-check">
          <input
            class="form-check-input"
            type="checkbox"
            id="onlyAvailable"
            v-model="filters.onlyAvailable"
          />
          <label class="form-check-label small fw-medium" for="onlyAvailable">
            Csak szabad szobák
          </label>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
</style>