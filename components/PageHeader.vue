<script lang="ts">
</script>

<template>
  <header>
    <div class="container">
      <h1 class="text-4xl font-semibold text-slate-200 sm:text-5xl">
        Jelson Matheus
      </h1>
      <h2 class="py-2 text-lg font-semibold text-slate-200 sm:text-xl">Develop Backend</h2>
      <p class="pt-1">
        Eu construo lógica de servidor eficiente e robusta para garantir desempenho 
        consistente nos bastidores.
      </p>
      <div class="hidden lg:block mt-16">
        <MenuList/>
      </div>
    </div>
    <ul class="mt-4 flex items-center gap-x-6 social">
      <li>
        <a href="https://github.com/JelsonMatheus" target="_blank" title="GitHub">
          <i class="bi bi-github text-2xl"></i>
        </a>
      </li>
      <li>
        <a href="https://www.linkedin.com/in/jelson-m-91b7651b5/" target="_blank" title="Linkedin">
          <i class="bi bi-linkedin text-2xl"></i>
        </a>
      </li>
      <li>
        <a href="" target="_blank" title="Instagram">
          <i class="bi bi-instagram text-2xl"></i>
        </a>
      </li>
    </ul>
  </header>
</template>

<style scoped>
.social a:hover {
  color: white;
}
</style>