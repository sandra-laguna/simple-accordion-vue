<template>
  <section id="faq" class="relative w-full max-w-screen-md mx-auto py-12 px-4 sm:py-24">
    <h1 class="mb-6 text-center text-3xl font-extrabold text-gray-900 sm:text-4xl"> Frequently asked questions </h1>

    <div id="accordion" class="accordions">
      <dl class="border-t-2 border-black-900 py-6" v-for="(row, id) in rows" :key="id">
        <dt class="py-1 w-full text-black font-black flex justify-between" v-on:click="row.open = !row.open">
          {{ row.term }}
          <button @click="toggle" class="px-2">
            <icon-arrowdown :class="[row.open ? 'hidden' : 'block', 'h-4 w-4']" />
            <icon-arrowup :class="[row.open ? 'block' : 'hidden', 'h-4 w-4']" />
          </button>
        </dt>
        <dd class="mb-2 text-gray-500" v-if="row.open">{{ row.details }}</dd>
      </dl>
    </div>
  </section>
</template>

<script>
export default {
  data: () => ({
    isOpen: false,
    rows: {
      faq1: {
        term: "Lorem ipsum dolor sit amet.",
        details: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Impedit, nemo!",
        open: false
      },
      faq2: {
        term: "Lorem ipsum dolor sit amet.",
        details: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Impedit, nemo!",
        open: false
      },
      faq3: {
        term: "Lorem ipsum dolor sit amet.",
        details: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Impedit, nemo!",
        open: false
      }
    }
  }),
  methods: {
    toggle() {
      this.isOpen = !this.isOpen;
    }
  }
};
</script>
