<script lang="ts">
  export let title: string;
  export let description: string;
  export let link: string;
</script>

<a href={link} class="block p-6 bg-white rounded-xl shadow hover:shadow-lg transition">
  <h3 class="font-bold text-xl mb-2">{title}</h3>
  <p class="text-gray-600">{description}</p>
</a>
