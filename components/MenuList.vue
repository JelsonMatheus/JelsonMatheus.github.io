<script lang="ts">
export default {
  data() {
    return {
      items: [
        {name: 'Sobre', path: '#about'},
        {name: 'Carreira', path: '#career'},
        {name: 'Projetos', path: '#projects'}
      ],
      activeRouteValue: null as string | null
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  computed: {
    activeItem() {
      const activeRoute = this.$route.hash;
      const activeIndex = this.items.findIndex(item => item.path === activeRoute);
      this.activeRouteValue = activeIndex === -1 ? this.activeRouteValue || this.items[0].path : this.items[activeIndex].path;
      return this.activeRouteValue;
    }
  },
  methods: {
    handleScroll() {
      const activeItem = this.items.find(item => {
        const section = document.getElementById(item.path.substring(1));
        const rect = section?.getBoundingClientRect();
        return rect && rect.top <= window.innerHeight && rect.bottom >= 0;
      });

      if (activeItem) {
        this.activeRouteValue = activeItem.path;
      }
    }
  }
}
</script>

<template>
  <nav class="nav">
    <ul class="w-max">
      <li v-for="item in items" :key="item.name">
        <a :class="[ 'group flex items-center py-3', { 'active': item.path === activeItem } ]"
          :href="item.path">
          <span class="nav-indicator mr-4 h-px w-8 bg-slate-600 transition-all 
            group-hover:w-16 group-hover:bg-slate-200 group-focus-visible:w-16 group-focus-visible:bg-slate-200 motion-reduce:transition-none"></span>
          <span class="nav-text uppercase tracking-widest text-xs font-bold
            group-hover:text-slate-200 group-focus-visible:text-slate-200">
            {{ item.name }}
          </span>
        </a>
      </li>
    </ul>
  </nav>
</template>

<style scoped>
  .nav .active .nav-indicator {
    width: 4rem;
    background-color: white;
  }
  .nav .active {
    color: white;
  }

</style>