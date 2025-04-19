<script>
    import Footer from '$lib/components/Footer.svelte';
    import NavBar from '$lib/components/NavBar.svelte';
    import { fade, scale } from 'svelte/transition';

    const member = {
        name: "Brent Kenneth O. Abrazaldo",
        role: "BS-Computer Science",
        image: "/img/img3.jpg",
        description: "Brent is a software developer with expertise in full-stack development and innovative problem-solving.",
        skills: ["Full-Stack Development", "Database Management", "Problem Solving"],
        portfolio: "Brent has developed key features for the team's projects, ensuring high performance and user satisfaction.",
        education: {
            elementary: "Pogo-Palua Elementary School",
            highschool: "Mangaldan Integrated School SPED Center",
            seniorHighschool: "Mangaldan National Highschool",
            college: "Metro Dagupan Colleges"
        },
        educationLogos: {
            elementary: "/img/logos/pogo-palua-elementary.png",
            highschool: "/img/logos/mangaldan-integrated-school.png",
            seniorHighschool: "/img/logos/mangaldan-national-highschool.png",
            college: "/img/logos/metro-dagupan-colleges.png"
        }
    };
</script>

<svelte:head>
    <title>About Brent Kenneth O. Abrazaldo</title>
    <meta name="description" content="Learn more about Brent Kenneth O. Abrazaldo, a BS-Computer Science student with a passion for software development." />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
</svelte:head>

<NavBar />

<main class="flex-grow py-8 px-4 sm:px-8 bg-gray-900 text-gray-100">
    <section class="max-w-screen-lg mx-auto grid grid-cols-1 sm:grid-cols-3 gap-8">
        <!-- Left Column: Profile Picture -->
        <div class="text-center sm:col-span-1">
            <div class="relative mx-auto w-36 h-36 sm:w-52 sm:h-52" in:scale={{ duration: 500 }}>
                <!-- Animated Border -->
                <div class="relative w-full h-full rounded-xl border-animation">
                    <!-- Profile Picture -->
                    <img
                        src={member.image}
                        alt={member.name}
                        class="relative rounded-xl w-full h-full object-cover shadow-lg"
                    />
                </div>
            </div>
            <h1 class="text-xl sm:text-3xl font-bold text-white mt-4 sm:mt-6" in:fade={{ duration: 500 }}>
                {member.name}
            </h1>
            <p class="text-base sm:text-lg text-gray-400 mt-2" in:fade={{ duration: 500 }}>
                {member.role}
            </p>
        </div>

        <!-- Right Column: About, Skills, Portfolio, and Education -->
        <div class="sm:col-span-2 text-gray-300">
            <h2 class="text-xl sm:text-2xl font-bold text-white">About</h2>
            <p class="mt-2 sm:mt-4 text-sm sm:text-base">{member.description}</p>

            <h2 class="text-xl sm:text-2xl font-bold text-white mt-6 sm:mt-8">Skills</h2>
            <ul class="list-disc list-inside mt-2 sm:mt-4 text-sm sm:text-base">
                {#each member.skills as skill}
                    <li>{skill}</li>
                {/each}
            </ul>

            <h2 class="text-xl sm:text-2xl font-bold text-white mt-6 sm:mt-8">Portfolio</h2>
            <p class="mt-2 sm:mt-4 text-sm sm:text-base">{member.portfolio}</p>

            <h2 class="text-xl sm:text-2xl font-bold text-white mt-6 sm:mt-8">Education</h2>
            <ul class="list-disc list-inside mt-2 sm:mt-4 text-sm sm:text-base">
                <li class="flex items-center space-x-2 sm:space-x-4">
                    <img src={member.educationLogos.elementary} alt="Elementary Logo" class="h-6 w-6 sm:h-8 sm:w-8 object-contain" />
                    <span><strong>Elementary:</strong> {member.education.elementary}</span>
                </li>
                <li class="flex items-center space-x-2 sm:space-x-4 mt-2 sm:mt-4">
                    <img src={member.educationLogos.highschool} alt="High School Logo" class="h-6 w-6 sm:h-8 sm:w-8 object-contain" />
                    <span><strong>High School:</strong> {member.education.highschool}</span>
                </li>
                <li class="flex items-center space-x-2 sm:space-x-4 mt-2 sm:mt-4">
                    <img src={member.educationLogos.seniorHighschool} alt="Senior High School Logo" class="h-6 w-6 sm:h-8 sm:w-8 object-contain" />
                    <span><strong>Senior High School:</strong> {member.education.seniorHighschool}</span>
                </li>
                <li class="flex items-center space-x-2 sm:space-x-4 mt-2 sm:mt-4">
                    <img src={member.educationLogos.college} alt="College Logo" class="h-6 w-6 sm:h-8 sm:w-8 object-contain" />
                    <span><strong>College:</strong> {member.education.college}</span>
                </li>
            </ul>

            <!-- Go Back Icon -->
            <div class="mt-8 text-left">
                <button
                    type="button"
                    class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm p-2.5 text-center inline-flex items-center me-2 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800 border- border-transparent hover:border-blue-500 focus:border-blue-500"
                    on:click={() => window.history.back()}
                >
                    <svg
                        class="w-5 h-5"
                        aria-hidden="true"
                        xmlns="http://www.w3.org/2000/svg"
                        fill="none"
                        viewBox="0 0 14 10"
                    >
                        <path
                            stroke="currentColor"
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            stroke-width="2"
                            d="M1 5h12m0 0L9 1m4 4L9 9"
                        />
                    </svg>
                    <span class="ml-2">Back</span>
                </button>
            </div>
        </div>
    </section>
</main>

<Footer />

<style>
    @layer utilities {
        @keyframes pulse-border {
            0% {
                background-size: 200% 200%;
                background-position: 50% 50%;
            }
            50% {
                background-size: 250% 250%;
                background-position: 75% 25%;
            }
            100% {
                background-size: 200% 200%;
                background-position: 50% 50%;
            }
        }

        .border-animation {
            position: relative;
            padding: 2px; /* Thinner border for better mobile appearance */
            background: radial-gradient(
                circle,
                #EB459E,
                #5865F2,
                #00C2FF
            );
            background-size: 200% 200%;
            animation: pulse-border 4s ease-in-out infinite;
            border-radius: 1rem;
        }

        .border-animation img {
            border-radius: inherit;
        }
    }
</style>