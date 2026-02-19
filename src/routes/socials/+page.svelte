<script lang="ts">
  import Header from '$lib/Header.svelte';
  import Footer from '$lib/Footer.svelte';
  import { Github, Linkedin, Twitter } from 'lucide-svelte';

  const socials = [
    { name: "GitHub", url: "https://github.com/havask", description: "My GitHub repositories and projects.", icon: Github, color: "bg-gray-900 text-white" },
    { name: "LinkedIn", url: "https://shorturl.at/oRwPr", description: "My professional LinkedIn profile.", icon: Linkedin, color: "bg-blue-700 text-white" },
  ];
</script>

<div class="flex flex-col min-h-screen bg-gray-50">
  <Header title="Socials" />

  <main class="flex-grow px-6 md:px-12 lg:px-24 py-12 flex flex-col items-center space-y-6">
    <h2 class="text-3xl font-bold mb-6 text-center">Connect with Me</h2>

    <div class="flex flex-col w-full max-w-md space-y-6">
      {#each socials as social}
        <a 
          href={social.url} 
          target="_blank" 
          class="flex items-center p-6 bg-white rounded-xl shadow hover:shadow-2xl transition-transform transform hover:-translate-y-1 hover:scale-105 space-x-6"
        >
          <div class={`flex items-center justify-center w-16 h-16 rounded-full ${social.color} text-2xl`}>
            <svelte:component this={social.icon} class="w-8 h-8" />
          </div>
          <div>
            <h3 class="font-semibold text-xl">{social.name}</h3>
            <p class="text-gray-600">{social.description}</p>
          </div>
        </a>
      {/each}
    </div>
  </main>

  <Footer />
</div>
