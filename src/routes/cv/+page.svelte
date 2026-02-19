<script lang="ts">
  import Header from '$lib/Header.svelte';
  import Footer from '$lib/Footer.svelte';

  // Education
  const education = [
    { date: "08.2024 – 05.2026", title: "Computer Science - Master", place: "UiT Norges arktiske universitet" },
    { date: "08.2022 – 08.2023", title: "Computer Science - Bachelor", place: "Vrije Universiteit Amsterdam VU" },
    { date: "08.2020 – 01.2024", title: "Computer Science - Bachelor", place: "UiT Norges arktiske universitet" },
    { date: "08.2019 – 06.2020", title: "Forkurs for ingeniør- og sivilingeniørutdanning", place: "UiT Norges arktiske universitet" }
  ];

// Work experience
const experience = [
  { date: "01.05 – d.d.", title: "Systemutvikler", place: "Ishavskraft AS", description: "" }, // ← NEW ENTRY
  { date: "12.2025 – d.d.", title: "Vitenskapelig Assistent", place: "UiT - Norges arktiske Universitet", description: "INF-3701 Advanced database systems" },
  { date: "08.2025 – d.d.", title: "Masteroppgave", place: "DIPS AS", description: "Tester og evaluerer språkmodeller for medisinsk bruk" },
  { date: "06.2025 – d.d.", title: "Systemutvikler", place: "AVJU SOLUTIONS AS", description: "Prosessering, analyse og visualisering av sensordata." },
  { date: "06.2024 – 08.2024", title: "Systemutvikler", place: "Datakvalitet AS", description: "Full-stack webutvikling i .NET" },
  { date: "06.2023 – 08.2023", title: "Tømrer", place: "Byggebistand AS", description: "" },
  { date: "01.2022 – 06.2022", title: "StartUp", place: "Norinnova AS", description: "Utviklet en mobil app MVP i samarbeid med Norinnova AS" },
  { date: "08.2021 – 12.2021", title: "Vitenskapelig assistent", place: "Universitetet i Tromsø - Norges arktiske Universitet", description: "" },
  { date: "03.2021 – 04.2021", title: "Narvik", place: "Nordisk film", description: "" },
  { date: "01.2020 – 09.2021", title: "Salgsmedarbeider", place: "Coop Obs Bygg", description: "" },
  { date: "05.2019 – 01.2020", title: "Installatør", place: "ISAS reklame", description: "Installerte stilt, bilfolie, banners etc." },
  { date: "05.2017 – 08.2018", title: "Tømrer / Taktekker", place: "Svein M Jentoft AS", description: "Taktekking og tømring" },
  { date: "05.2016 – 08.2017", title: "Salgsmedarbeider", place: "Eide Bygg", description: "" },
  { date: "09.2015 – 02.2016", title: "Salgsmedarbeider", place: "Brødrene Johannessen AS", description: "" },
  { date: "05.2014 – 08.2014", title: "Vedlikehold", place: "EWOS AS", description: "" }
];


  const roles = [
    { date: "08.2025 – d.d.", title: "Vararepresentant", place: "Studentparlamentet" },
    { date: "08.2021 – 12.2021", title: "Representant", place: "Studentutvalget NT-fak" },
    { date: "08.2021 – 12.2021", title: "Nestleder NT-SU", place: "Politisk student organ for NT fakultet (UiT)" },
    { date: "08.2021 – 12.2021", title: "Tillitsvalgt informatikk", place: "" }
  ];
</script>

<div class="flex flex-col min-h-screen">
  <Header title="CV" />

  <main class="flex-grow px-6 md:px-12 lg:px-24 py-8 space-y-12">

    <!-- Education -->
    <div class="bg-white rounded-xl shadow-md p-6 md:p-10">
      <h2 class="text-3xl font-bold mb-6">Education</h2>
      <ul class="space-y-4">
        {#each education as edu}
          <li class="flex flex-col sm:flex-row sm:justify-between border-b pb-2">
            <span class="text-gray-500 sm:w-48">{edu.date}</span>
            <div class="sm:flex-1">
              <h3 class="font-semibold">{edu.title}</h3>
              <p class="text-gray-600">{edu.place}</p>
            </div>
          </li>
        {/each}
      </ul>
    </div>

    <!-- Work Experience -->
    <div class="bg-white rounded-xl shadow-md p-6 md:p-10">
      <h2 class="text-3xl font-bold mb-6">Work Experience</h2>
      <ul class="space-y-4">
        {#each experience as job}
          <li class="flex flex-col sm:flex-row sm:justify-between border-b pb-2">
            <span class="text-gray-500 sm:w-48">{job.date}</span>
            <div class="sm:flex-1">
              <h3 class="font-semibold">{job.title}</h3>
              <p class="text-gray-600">{job.place}</p>
              {#if job.description}<p class="text-gray-500 text-sm">{job.description}</p>{/if}
            </div>
          </li>
        {/each}
      </ul>
    </div>

    <div class="bg-white rounded-xl shadow-md p-6 md:p-10">
      <h2 class="text-3xl font-bold mb-6">Roles</h2>
      <ul class="space-y-4">
        {#each roles as role}
          <li class="flex flex-col sm:flex-row sm:justify-between border-b pb-2">
            <span class="text-gray-500 sm:w-48">{role.date}</span>
            <div class="sm:flex-1">
              <h3 class="font-semibold">{role.title}</h3>
              {#if role.place}<p class="text-gray-600">{role.place}</p>{/if}
            </div>
          </li>
        {/each}
      </ul>
    </div>

  </main>

  <Footer />
</div>
