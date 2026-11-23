<script setup>
import { reactive } from 'vue';

const form = reactive({
    guestName: '',
    roomNumber: '',
    guests: 1,
    checkIn: '',
    checkOut: ''
});

const submitBooking = () => {
    alert(`Foglalás rögzítve: ${form.guestName} (${form.roomNumber}. szoba)`);
};
</script>

<template>
    <section id="uj-foglalas" class="bg-cream py-5 my-5">
        <div class="container py-3">
            <div class="row g-5 align-items-center">
                <div class="col-lg-5">
                    <span class="section-tag d-block mb-2">FOGLALÁSKEZELÉS</span>
                    <h2 class="serif-font fw-bold text-harmonia display-6 mb-3">
                        Érkezéstől a távozásig, egyszerűen.
                    </h2>
                    <p class="text-muted mb-4">
                        A rendszer automatikusan ellenőrzi a dátumokat, a szoba kapacitását és az esetleges átfedéseket.
                    </p>

                    <ul class="list-unstyled d-flex flex-column gap-2 small fw-medium">
                        <li><i class="bi bi-check-circle-fill text-harmonia me-2"></i>Azonnali elérhetőség-ellenőrzés
                        </li>
                        <li><i class="bi bi-check-circle-fill text-harmonia me-2"></i>Biztonságos módosítás</li>
                        <li><i class="bi bi-check-circle-fill text-harmonia me-2"></i>Egyértelmű visszajelzések</li>
                    </ul>
                </div>

                <div class="col-lg-7">
                    <div class="card border-0 shadow-sm rounded-4 p-4 p-md-5">
                        <span class="section-tag">GYORS ÜGYINTÉZÉS</span>
                        <h3 class="serif-font fw-bold text-harmonia mt-1">Új foglalás</h3>
                        <p class="small text-muted mb-4">Minden mező kitöltése kötelező.</p>

                        <form @submit.prevent="submitBooking">
                            <div class="mb-3">
                                <label class="form-label small fw-semibold">Vendég neve</label>
                                <input type="text" class="form-control" v-model="form.guestName"
                                    placeholder="pl. Kiss Júlia" required />
                            </div>

                            <div class="row g-3 mb-3">
                                <div class="col-md-6">
                                    <label class="form-label small fw-semibold">Szoba</label>
                                    <select class="form-select" v-model="form.roomNumber" required>
                                        <option value="" disabled>Válasszon szobát</option>
                                        <option value="101">101. szoba (Egyágyas)</option>
                                        <option value="102">102. szoba (Egyágyas)</option>
                                        <option value="103">103. szoba (Kétágyas)</option>
                                        <option value="104">104. szoba (Kétágyas)</option>
                                        <option value="201">201. szoba (Kétágyas)</option>
                                        <option value="202">202. szoba (Lakosztály)</option>
                                        <option value="203">203. szoba (Lakosztály)</option>
                                        <option value="301">301. szoba (Lakosztály)</option>
                                    </select>
                                </div>

                                <div class="col-md-6">
                                    <label class="form-label small fw-semibold">Vendégek</label>
                                    <input type="number" class="form-control" v-model="form.guests" min="1" max="4"
                                        required />
                                </div>
                            </div>

                            <div class="row g-3 mb-4">
                                <div class="col-md-6">
                                    <label class="form-label small fw-semibold">Érkezés</label>
                                    <input type="date" class="form-control" v-model="form.checkIn" required />
                                </div>

                                <div class="col-md-6">
                                    <label class="form-label small fw-semibold">Távozás</label>
                                    <input type="date" class="form-control" v-model="form.checkOut" required />
                                </div>
                            </div>

                            <button type="submit" class="btn btn-harmonia w-100 py-2 rounded-3">
                                <i class="bi bi-check-lg me-1"></i> Foglalás rögzítése
                            </button>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>


<style scoped></style>