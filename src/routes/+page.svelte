<script lang="ts">
  import Header from '$lib/Header.svelte';
  import Section from '$lib/Section.svelte';
  import Card from '$lib/Card.svelte';
  import Footer from '$lib/Footer.svelte';
  import { base } from '$app/paths';

  const projects = [
    { title: "CV", description: "View my professional CV.", link: `${base}/cv` },
    { title: "Courses & Projects", description: "See courses I've taken and my projects.", link: `${base}/projects` },
    { title: "Socials", description: "Links to GitHub, LinkedIn, etc.", link: `${base}/socials` },
  ];
</script>

<div class="flex flex-col min-h-screen bg-gray-50">
  <!-- Header -->
  <Header title="Håvard Skjærstein – Portfolio" />

  <!-- Main content grows to fill remaining space -->
  <main class="flex-grow px-6 md:px-12 lg:px-24 py-12 space-y-16">

    <!-- About Me -->
    <Section heading="About Me">
      <div class="flex flex-col md:flex-row items-center md:items-center gap-8 md:gap-12">
        <!-- Picture -->
        <img
          src="{base}/profile.jpeg"
          alt="Håvard Skjærstein"
          class="w-52 h-52 md:w-64 md:h-64 object-cover rounded-full shadow-xl border-4 border-blue-600"
        />

        <!-- Text -->
        <div class="md:flex-1">
          <p class="text-gray-800 leading-relaxed text-lg md:text-xl">
I'm Håvard, a Computer Science Master's student at UiT. I build web and mobile apps, explore AI in healthcare, and enjoy turning ideas into working software.          </p>
        </div>
      </div>
    </Section>

    <!-- My Work -->
    <Section heading="My Work">
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
        {#each projects as project}
          <Card 
            title={project.title} 
            description={project.description} 
            link={project.link} 
          />
        {/each}
      </div>
    </Section>
    
  </main>

  <!-- Footer -->
  <Footer />
</div>