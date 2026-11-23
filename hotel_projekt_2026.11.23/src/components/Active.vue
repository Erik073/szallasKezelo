<script setup>
import { ref, computed } from 'vue';

const searchQuery = ref('');

const bookings = ref([
    { id: '#1001', guest: 'Kovács Anna', room: '101', roomType: 'Egyágyas', period: '2026. dec. 2. → 2026. dec. 5.', guests: 1 },
    { id: '#1002', guest: 'Nagy Bence', room: '103', roomType: 'Kétágyas', period: '2026. dec. 4. → 2026. dec. 8.', guests: 2 },
    { id: '#1003', guest: 'Szabó család', room: '202', roomType: 'Lakosztály', period: '2026. dec. 10. → 2026. dec. 14.', guests: 4 },
    { id: '#1004', guest: 'Tóth Eszter', room: '104', roomType: 'Kétágyas', period: '2026. dec. 15. → 2026. dec. 19.', guests: 2 },
    { id: '#1005', guest: 'Varga Dániel', room: '203', roomType: 'Lakosztály', period: '2026. dec. 20. → 2026. dec. 27.', guests: 3 }
]);

const filteredBookings = computed(() => {
    return bookings.value.filter(b =>
        b.guest.toLowerCase().includes(searchQuery.value.toLowerCase())
    );
});
</script>

<template>
    <section id="foglalasok" class="container pb-5 mb-4">
        <div class="d-flex flex-wrap justify-content-between align-items-end gap-3 mb-4">
            <div>
                <span class="section-tag d-block mb-1">NYILVÁNTARTÁS</span>
                <h2 class="serif-font fw-bold text-harmonia mb-1">Aktív foglalások</h2>
                <p class="text-muted small mb-0">Érkezési dátum szerint rendezve.</p>
            </div>

            <div class="input-group" style="max-width: 280px;">
                <span class="input-group-text bg-white border-end-0 text-muted">
                    <i class="bi bi-search"></i>
                </span>
                <input type="text" class="form-control border-start-0 ps-0" v-model="searchQuery"
                    placeholder="Keresés vendégnév alapján..." />
            </div>
        </div>

        <div class="card border shadow-sm rounded-4 overflow-hidden">
            <div class="table-responsive">
                <table class="table table-hover align-middle mb-0">
                    <thead class="table-light">
                        <tr class="section-tag">
                            <th class="ps-4 py-3">AZONOSÍTÓ</th>
                            <th class="py-3">VENDÉG</th>
                            <th class="py-3">SZOBA</th>
                            <th class="py-3">IDŐSZAK</th>
                            <th class="py-3">FŐ</th>
                            <th class="text-end pe-4 py-3">MŰVELETEK</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="item in filteredBookings" :key="item.id">
                            <td class="ps-4 text-muted small">{{ item.id }}</td>
                            <td class="fw-semibold">{{ item.guest }}</td>
                            <td>
                                <div class="fw-bold">{{ item.room }}</div>
                                <div class="text-muted small">{{ item.roomType }}</div>
                            </td>
                            <td class="small">{{ item.period }}</td>
                            <td class="small">{{ item.guests }}</td>
                            <td class="text-end pe-4">
                                <button class="btn btn-sm btn-outline-secondary me-1" title="Szerkesztés">
                                    <i class="bi bi-pencil"></i>
                                </button>
                                <button class="btn btn-sm btn-outline-danger" title="Törlés">
                                    <i class="bi bi-trash"></i>
                                </button>
                            </td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </section>
</template>


<style scoped></style>