<script setup>
</script>

<template>
  <div class="d-flex flex-column min-vh-100">
    <header class="bg-harmonia text-white pb-5">
      <div class="container">
        <nav class="navbar navbar-dark py-3 border-bottom border-white border-opacity-10">
          <a class="navbar-brand d-flex align-items-center gap-2" href="#">
            <span class="border border-white border-opacity-25 rounded-3 px-2 py-1 serif-font fw-bold">H</span>
            <div class="lh-1">
              <div class="fw-semibold fs-6">Harmónia</div>
              <small class="text-white-50" style="font-size: 0.6rem; letter-spacing: 0.1em;">HOTEL RECEPTION</small>
            </div>
          </a>

          <div class="d-flex align-items-center gap-4">
            <a href="#szobak" class="text-white-50 text-decoration-none small">Szobák</a>
            <a href="#foglalasok" class="text-white-50 text-decoration-none small">Foglalások</a>
            <a href="#uj-foglalas" class="btn btn-light btn-sm fw-semibold text-harmonia px-3">
              + Új foglalás
            </a>
          </div>
        </nav>

        <div class="row align-items-center py-5 g-4">
          <div class="col-lg-7">
            <span class="badge bg-white bg-opacity-10 text-info-emphasis border border-white border-opacity-10 mb-3">
              ● RECEPCIÓS MUNKAFELÜLET
            </span>
            <h1 class="serif-font display-4 fw-bold mb-3">
              Minden foglalás.<br />Egy helyen.
            </h1>
            <p class="text-white-50 lead fs-6 mb-0" style="max-width: 450px;">
              Tekintse át a szobák állapotát, kezelje a vendégek foglalásait gyorsan és magabiztosan.
            </p>
          </div>

          <div class="col-lg-5 d-flex justify-content-lg-end">
            <div
              class="bg-white bg-opacity-10 border border-white border-opacity-10 rounded-4 p-4 d-flex gap-4 text-center">
              <div>
                <div class="serif-font fs-2 fw-bold">8</div>
                <small class="text-white-50">szoba</small>
              </div>
              <div class="vr opacity-25"></div>
              <div>
                <div class="serif-font fs-2 fw-bold">5</div>
                <small class="text-white-50">foglalás</small>
              </div>
              <div class="vr opacity-25"></div>
              <div>
                <div class="serif-font fs-2 fw-bold">8</div>
                <small class="text-white-50">szabad most</small>
              </div>
            </div>
          </div>
        </div>
      </div>
    </header>

    <main class="flex-grow-1">
      <section id="szobak" class="container pt-5">
        <span class="section-tag d-block mb-1">ÁTTEKINTÉS</span>
        <h2 class="serif-font fw-bold text-harmonia mb-1">Szobák elérhetősége</h2>
        <p class="text-muted small mb-4">Válasszon időszakot a pontos foglaltság megtekintéséhez.</p>

        <Filter />
        <Cards />
      </section>

      <Form />
      <Active />
    </main>

    <!-- Lábléc -->
    <footer class="bg-harmonia text-white-50 py-3 small">
      <div class="container d-flex justify-content-between">
        <span>© 2026 Harmónia Hotel</span>
        <span>Recepciós foglaláskezelő</span>
      </div>
    </footer>
  </div>
</template>

<script setup>
import Filter from './components/Filter.vue';
import Cards from './components/Cards.vue';
import Form from './components/Form.vue';
import Active from './components/Active.vue';
</script>
