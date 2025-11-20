<script setup lang="ts">
import AppLayout from '@/layouts/AppLayout.vue';
import { dashboard } from '@/routes';
import { type BreadcrumbItem } from '@/types';
import { Head } from '@inertiajs/vue3';
import { ref } from 'vue';

// Breadcrumbs
const breadcrumbs: BreadcrumbItem[] = [
  {
    title: 'Dashboard',
    href: dashboard().url,
  },
];

// Contador reactivo con TypeScript
const contador = ref<number>(0);

const incrementar = () => contador.value++;
const decrementar = () => contador.value--;
const reset = () => contador.value = 0;
</script>

<template>
  <Head title="Dashboard" />

  <AppLayout :breadcrumbs="breadcrumbs">
    <div class="min-h-screen flex flex-col items-center justify-center bg-gradient-to-br from-purple-50 to-indigo-100 px-4">
      
      <!-- Título -->
      <h1 class="text-5xl md:text-6xl font-extrabold text-purple-700 mb-12 tracking-tight">
        Contador
      </h1>

      <!-- Número gigante -->
      <div class="text-8xl md:text-9xl font-black text-purple-600 tabular-nums select-none">
        {{ contador }}
      </div>

      <!-- Botones morados pro -->
      <div class="mt-16 flex flex-wrap gap-6 justify-center">
        <button
          @click="decrementar"
          class="px-10 py-6 bg-purple-600 text-white text-3xl font-bold rounded-2xl hover:bg-purple-700 active:scale-95 transition-all shadow-2xl">
          -1
        </button>

        <button
          @click="reset"
          class="px-8 py-6 bg-gray-600 text-white text-2xl font-bold rounded-2xl hover:bg-gray-700 active:scale-95 transition-all shadow-2xl">
          Reset
        </button>

        <button
          @click="incrementar"
          class="px-10 py-6 bg-purple-600 text-white text-3xl font-bold rounded-2xl hover:bg-purple-700 active:scale-95 transition-all shadow-2xl">
          +1
        </button>
      </div>

      <!-- Tu firma morada -->
      <footer class="mt-20 text-purple-600 font-semibold text-lg">
        Hecho por Roy Jhojan Mamani Alca
      </footer>
    </div>
  </AppLayout>
</template>