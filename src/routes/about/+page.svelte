<script lang="ts">
  import Header from '$lib/Header.svelte';
  import Footer from '$lib/Footer.svelte';
</script>

<Header title="About This App" />

<main class="max-w-3xl mx-auto p-6">
  <h2 class="text-2xl font-semibold mb-4">Who we are</h2>
  <p class="mb-4">
    This is a demo SvelteKit project to show how pages and components work.
  </p>
  <p>
    You can reuse components from <code>lib/</code> and style with Tailwind.
  </p>
</main>

<Footer />