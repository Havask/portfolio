<script lang="ts">
  export let heading: string;
</script>

<section class="max-w-5xl mx-auto p-6 mb-10">
  <h2 class="text-3xl font-bold mb-6">{heading}</h2>
  <slot /> <!-- content goes here -->
</section>