<script>
    import Footer from '$lib/components/Footer.svelte';
    import NavBar from '$lib/components/NavBar.svelte';

    // Updated data for Irish M. Villanueva
    const member = {
        name: "Irish M. Villanueva",
        role: "BS-Tourism",
        image: "/img/img1.jpg",
        description: "Irish specializes in event planning and logistics, bringing creativity and organization to every project.",
        skills: ["Event Planning", "Logistics Management", "Creative Problem Solving"],
        portfolio: "Irish has successfully organized multiple events for the team, ensuring smooth execution and client satisfaction.",
        education: {
            elementary: "San Fabian Elementary School",
            highschool: "San Fabian National High School",
            seniorHighschool: "San Fabian Senior High School",
            college: "Metro Dagupan Colleges"
        },
        educationLogos: {
            elementary: "/img/logos/san-fabian-elementary.png",
            highschool: "/img/logos/san-fabian-highschool.png",
            seniorHighschool: "/img/logos/san-fabian-senior-highschool.png",
            college: "/img/logos/metro-dagupan-colleges.png"
        }
    };
</script>

<svelte:head>
    <title>About Irish M. Villanueva</title>
    <meta name="description" content="Learn more about Irish M. Villanueva, a BS-Tourism student with a passion for event planning and logistics." />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
</svelte:head>

<NavBar />

<main class="flex-grow py-8 px-4 sm:px-8 bg-gray-900 text-gray-100">
    <section class="max-w-screen-lg mx-auto grid grid-cols-1 sm:grid-cols-3 gap-8">
        <!-- Left Column: Profile Picture -->
        <div class="text-center sm:col-span-1">
            <div class="relative mx-auto w-32 h-32 sm:w-52 sm:h-52">
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
            <h1 class="text-xl sm:text-3xl font-bold text-white mt-4 sm:mt-6">{member.name}</h1>
            <p class="text-base sm:text-lg text-gray-400 mt-2">{member.role}</p>
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

            <!-- Go Back Button -->
            <div class="mt-8 text-left">
                <button
                    type="button"
                    class="bg-gradient-to-r from-blue-500 to-blue-700 hover:from-blue-600 hover:to-blue-800 text-white font-semibold text-xs sm:text-sm py-2 px-4 rounded-lg shadow-md inline-flex items-center transition duration-300"
                    on:click={() => window.history.back()}
                >
                    <svg
                        class="w-4 h-4 sm:w-5 sm:h-5 mr-2"
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
                    Back
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