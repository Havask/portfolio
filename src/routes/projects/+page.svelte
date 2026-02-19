<script lang="ts">
  import Header from '$lib/Header.svelte';
  import Footer from '$lib/Footer.svelte';
  import { ExternalLink } from 'lucide-svelte';

  // Degrees summary
  const degrees = [
    { level: "Master", field: "Computer Science", place: "UiT Norges arktiske universitet", date: "08.2024 – 05.2026" },
    { level: "Bachelor", field: "Computer Science", place: "UiT Norges arktiske universitet", date: "08.2022 – 08.2023" },
  ];

  // Courses data
const courses = [
    { code: "INF-1100", title: "Innføring i programmering og datamaskiners virkemåte", semester: "2020 høst", points: 10 },
    { code: "MAT-0001", title: "Brukerkurs i matematikk", semester: "2020 høst", points: 10 },
    { code: "MAT-1005", title: "Diskret matematikk", semester: "2020 høst", points: 10 },
    { code: "INF-1101", title: "Datastrukturer og algoritmer", semester: "2021 vår", points: 10 },
    { code: "BED-2012", title: "Prosjektledelse", semester: "2021 høst", points: 10 },
    { code: "FIL-0700", title: "Examen philosophicum, Tromsøvarianten", semester: "2021 høst", points: 10 },
    { code: "INF-1400", title: "Objektorientert programmering", semester: "2021 høst", points: 10 },
    { code: "INF-2200", title: "Datamaskinarkitektur og -organisering", semester: "2021 høst", points: 10 },
    { code: "BED-1009", title: "Innovasjon", semester: "2023 høst", points: 10 },
    { code: "INF-2300", title: "Computer Communication", semester: "2023 høst", points: 10 },
    { code: "INF-2700", title: "Database Systems", semester: "2023 høst", points: 10 },
    { code: "BED-2043NETT", title: "Ledelse av prosjekt", semester: "2024 vår", points: 10 },
    { code: "INF-2201", title: "Operating system fundamentals", semester: "2024 vår", points: 20 },
    { code: "INF-2310", title: "Computer Security", semester: "2024 vår", points: 10 },
    { code: "REL-1001", title: "Kristendom I: Kristendommens opphav og historie", semester: "2024 vår", points: 10 },
    { code: "STA-0001", title: "Brukerkurs i statistikk 1", semester: "2024 vår", points: 10 },
    { code: "BED-1004", title: "Markedsføring", semester: "2024 høst", points: 10 },
    { code: "BED-2029", title: "Organisasjonsteori og ledelse", semester: "2024 høst", points: 10 },
    { code: "INF-3200", title: "Distributed Systems Fundamentals", semester: "2024 høst", points: 10 },
    { code: "INF-3201", title: "Parallel Programming", semester: "2024 høst", points: 10 },
    { code: "BED-2052", title: "Merkevarebygging", semester: "2025 vår", points: 10 },
    { code: "INF-3203", title: "Advanced Distributed Systems", semester: "2025 vår", points: 10 },
    { code: "INF-3701", title: "Advanced database systems", semester: "2025 vår", points: 10 },
    { code: "INF-3701-MASTER", title: "Masteroppgave – DIPS AS", semester: "2025 vår", points: 60 },

    // New VU courses
    { code: "XB_0014", title: "Data Wrangling", semester: "2023 vår", points: 6 },
    { code: "X_400488", title: "Web Technology", semester: "2023 vår", points: 3 },
    { code: "XB_0089", title: "Software Engineering Processes", semester: "2023 sommer", points: 6 },
];


  // Sort courses by field code
  courses.sort((a, b) => {
    const fieldA = a.code.split('-')[0];
    const fieldB = b.code.split('-')[0];
    if (fieldA < fieldB) return -1;
    if (fieldA > fieldB) return 1;
    return 0;
  });

  // Total points
  const totalPoints = courses.reduce((sum, course) => sum + course.points, 0);

  // Projects list
  const projects = [
    {
      name: "Masteroppgave – DIPS AS",
      description: "Tester og evaluerer språkmodeller for medisinsk bruk.",
      link: "",
      date: "08.2025 – d.d.",
    },
    {
      name: "Portfolio Website",
      description: "A clean, responsive portfolio built with SvelteKit and TailwindCSS.",
      link: "",
      date: "2026",
    },
    {
      name: "Next.JS website",
      description: "",
      link: "https://byggebistand-as.no/",
      date: "2024",
    },
  ];
</script>

<div class="flex flex-col min-h-screen bg-gray-50">
  <Header title="Courses & Projects" />

  <main class="flex-grow px-6 md:px-12 lg:px-24 py-12 space-y-16">
    <!-- Projects -->
    <section>
      <h2 class="text-3xl font-bold mb-4">My Projects</h2>
      <ul class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        {#each projects as project}
          <li class="bg-white rounded-xl shadow-md p-6 hover:shadow-lg transition">
            <div class="flex justify-between items-start">
              <h3 class="font-semibold text-xl">{project.name}</h3>
              <span class="text-gray-500">{project.date}</span>
            </div>
            <p class="text-gray-600 mt-2">{project.description}</p>
            {#if project.link}
              <a href={project.link} target="_blank" class="flex items-center text-blue-600 mt-2 hover:underline">
                View project
                <ExternalLink class="w-4 h-4 ml-1" />
              </a>
            {/if}
          </li>
        {/each}
      </ul>
    </section>
    <!-- Degrees summary -->
    <section>
      <h2 class="text-3xl font-bold mb-4">Degrees</h2>
      <ul class="space-y-2">
        {#each degrees as deg}
          <li class="bg-white rounded-lg shadow-sm p-4 md:p-6">
            <span class="font-semibold">{deg.level} in {deg.field}</span> – {deg.place} <br />
            <span class="text-gray-500 text-sm">{deg.date}</span>
          </li>
        {/each}
      </ul>
    </section>

    <!-- Courses -->
    <section>
      <h2 class="text-3xl font-bold mb-4">Courses Taken</h2>
      <p class="text-gray-700 mb-6 font-medium">Total points: {totalPoints} ECTS</p>

      <ul class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
        {#each courses as course}
          <li class="bg-white rounded-lg p-4 shadow-sm hover:shadow-md transition">
            <span class="font-semibold">{course.code}</span> – {course.title} <br />
            <span class="text-gray-500 text-sm">{course.semester} ({course.points} sp)</span>
          </li>
        {/each}
      </ul>
    </section>



  </main>

  <Footer />
</div>
