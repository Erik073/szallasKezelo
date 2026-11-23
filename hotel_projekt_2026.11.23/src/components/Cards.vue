<script setup>
const rooms = [
  { number: 101, type: 'EGYÁGYAS', capacity: 1, price: 18500 },
  { number: 102, type: 'EGYÁGYAS', capacity: 1, price: 18500 },
  { number: 103, type: 'KÉTÁGYAS', capacity: 2, price: 29900 },
  { number: 104, type: 'KÉTÁGYAS', capacity: 2, price: 29900 },
  { number: 201, type: 'KÉTÁGYAS', capacity: 2, price: 33900 },
  { number: 202, type: 'LAKOSZTÁLY', capacity: 4, price: 62900 },
  { number: 203, type: 'LAKOSZTÁLY', capacity: 4, price: 59900 },
  { number: 301, type: 'LAKOSZTÁLY', capacity: 4, price: 74900 }
];
</script>

<template>
  <div class="row g-4">
    <div v-for="room in rooms" :key="room.number" class="col-12 col-sm-6 col-lg-3">
      <div class="card h-100 border shadow-sm rounded-4 p-3">
        <div class="d-flex justify-content-between align-items-center mb-3">
          <span class="bg-light rounded-3 p-2 lh-1 text-harmonia">
            <i class="bi bi-door-closed fs-5"></i>
          </span>
          <span class="badge rounded-pill bg-success-subtle text-success border border-success-subtle px-2 py-1">
            ● Szabad
          </span>
        </div>

        <span class="section-tag mb-1">{{ room.type }}</span>
        <h5 class="fw-bold text-harmonia mb-3">{{ room.number }}. szoba</h5>

        <div class="d-flex justify-content-between align-items-center small text-muted mb-3">
          <span><i class="bi bi-person me-1"></i>{{ room.capacity }} fő</span>
          <span class="fw-bold text-dark">{{ room.price.toLocaleString('hu-HU') }} Ft / éj</span>
        </div>

        <button class="btn btn-harmonia w-100 mt-auto py-2 rounded-3">
          Szoba foglalása
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped>
</style>