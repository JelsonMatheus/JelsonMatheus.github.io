<script lang="ts">
import careerData from '~/assets/data/career.json';

export default {
  data() {
    return {
      careers: careerData
    }
  }
}
</script>

<template>
  <section id="career" class="lg:scroll-mt-24" >
    <div class="sticky top-0 z-20 -mx-6 mb-4 w-screen bg-slate-900/75 px-6 py-5 backdrop-blur md:-mx-12 md:px-12 lg:sr-only lg:relative lg:top-auto lg:mx-auto lg:w-full lg:px-0 lg:py-0 lg:opacity-0">
      <h2 class="text-sm font-bold uppercase tracking-widest text-slate-200 lg:sr-only">Carreira</h2>
    </div>

    <div class="group/list">
      <div v-for="(career, idx) in careers" :key="idx" class="mb-12 group">
        <div class="relative group grid sm:grid-cols-10 sm:gap-x-3 lg:hover:!opacity-100 lg:group-hover/list:opacity-50">
          <div class="absolute -inset-x-4 -inset-y-4 z-0 hidden rounded-md transition motion-reduce:transition-none lg:-inset-x-6 lg:block lg:group-hover:bg-slate-800/50 lg:group-hover:shadow-[inset_0_1px_0_0_rgba(148,163,184,0.1)] lg:group-hover:drop-shadow-lg"></div>
          <div class="z-10 mb-2 mt-1 col-span-3 font-medium uppercase text-xs tracking-wide text-slate-500">
            <p>{{ career.duration }}</p>
          </div>
          <div class="z-10 col-span-7 group">
            <h3 class="font-medium text-slate-200">
              <a :href="career.link" target="_blank" class="group-hover:text-teal-300">
                <span class="absolute -inset-x-4 -inset-y-2.5 hidden rounded md:-inset-x-6 md:-inset-y-4 lg:block"></span>
                <span>{{ career.office }}</span>
              </a>
            </h3>
            <p class="mt-2 text-sm leading-normal">
              {{ career.description }}
            </p>
            <ul class="mt-2 flex flex-wrap">
              <li v-for="tec in career.technologies" :key="tec" class="mr-1.5 mt-2">
                <div class="bg-teal-400/10 rounded-full text-xs font-medium leading-5 px-3 py-1 text-teal-300">
                  {{ tec }}
                </div>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>