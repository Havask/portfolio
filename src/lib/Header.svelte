<script lang="ts">
  export let title: string;
</script>

<header class="bg-blue-600 text-white p-6 shadow-md">
  <div class="max-w-7xl mx-auto flex flex-col sm:flex-row items-center justify-between">
    <!-- Title -->
    <h1 class="text-4xl font-bold text-center sm:text-left">{title}</h1>

    <!-- Navigation -->
    <nav class="mt-4 sm:mt-0">
      <ul class="flex space-x-6 justify-center sm:justify-end">
        <li><a href="/" class="hover:underline">Home</a></li>
        <li><a href="/cv" class="hover:underline">CV</a></li>
        <li><a href="/projects" class="hover:underline">Projects</a></li>
        <li><a href="/socials" class="hover:underline">Socials</a></li>
      </ul>
    </nav>
  </div>
</header>
