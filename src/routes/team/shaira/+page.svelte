<script>
    import Footer from '$lib/components/Footer.svelte';
    import NavBar from '$lib/components/NavBar.svelte';
    import { fade, scale } from 'svelte/transition';

    // Updated data for Shaira Embornal
    const member = {
        name: "Shaira Embornal",
        role: "BS-Tourism",
        image: "/img/img2.jpg",
        description: `Hello! My name is Shaira Embornal, and I’m a 20-year-old BS-Tourism student from Longos Proper, San Fabian, Pangasinan. 
        I’m passionate about creating meaningful connections and ensuring seamless experiences for clients. 
        I pride myself on my excellent communication skills, teamwork, and problem-solving abilities, which have helped me grow both personally and professionally.`,
        skills: ["Basic UX Design", "Basic UI Design", "Communication"], // Updated skills
        portfolio: "Shaira has played a key role in maintaining strong client relationships and ensuring project success.",
        workExperience: "None", // Added work experience
        education: {
            elementary: "Longos Proper Elementary School",
            highschool: "Mangaldan National High School",
            college: "Metro Dagupan Colleges"
        },
        educationLogos: {
            elementary: "/img/logos/san-fabian-elementary.png",
            highschool: "/img/logos/mangaldan-national-highschool.png",
            college: "/img/logos/metro-dagupan-colleges.png"
        },
        personalInfo: {
            age: 20,
            address: "Longos Proper, San Fabian, Pangasinan"
        },
        hobby: "Artistic activities, community service, photography, and gaming."
    };
</script>

<svelte:head>
    <title>About Shaira Embornal</title>
    <meta name="description" content="Learn more about Shaira Embornal, a BS-Tourism student with a passion for customer relations and hospitality." />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
</svelte:head>

<NavBar />

<main class="flex-grow py-8 px-4 sm:px-8 bg-gray-900 text-gray-100">
    <section class="max-w-screen-lg mx-auto grid grid-cols-1 sm:grid-cols-3 gap-8">
        <!-- Left Column: Profile Picture -->
        <div class="text-center sm:col-span-1">
            <div class="relative mx-auto w-32 h-32 sm:w-52 sm:h-52" in:scale={{ duration: 500 }}>
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

        <!-- Right Column: About, Skills, Portfolio, Work Experience, and Education -->
        <div class="sm:col-span-2 text-gray-300">
            <h2 class="text-xl sm:text-2xl font-bold text-white">About</h2>
            <p class="mt-2 sm:mt-4 text-sm sm:text-base">{member.description}</p>
            <p class="mt-2 sm:mt-4 text-sm sm:text-base">
                <strong>Age:</strong> {member.personalInfo.age} <br />
                <strong>Address:</strong> {member.personalInfo.address}
            </p>

            <h2 class="text-xl sm:text-2xl font-bold text-white mt-6 sm:mt-8">Skills</h2>
            <ul class="list-disc list-inside mt-2 sm:mt-4 text-sm sm:text-base">
                {#each member.skills as skill}
                    <li>{skill}</li>
                {/each}
            </ul>

            <h2 class="text-xl sm:text-2xl font-bold text-white mt-6 sm:mt-8">Hobbies</h2>
            <p class="mt-2 sm:mt-4 text-sm sm:text-base">{member.hobby}</p>

            <h2 class="text-xl sm:text-2xl font-bold text-white mt-6 sm:mt-8">Portfolio</h2>
            <p class="mt-2 sm:mt-4 text-sm sm:text-base">{member.portfolio}</p>

            <h2 class="text-xl sm:text-2xl font-bold text-white mt-6 sm:mt-8">Work Experience</h2>
            <p class="mt-2 sm:mt-4 text-sm sm:text-base">{member.workExperience}</p>

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
                    <img src={member.educationLogos.college} alt="College Logo" class="h-6 w-6 sm:h-8 sm:w-8 object-contain" />
                    <span><strong>College:</strong> {member.education.college}</span>
                </li>
            </ul>

            <!-- Socials Section -->
            <h2 class="text-xl sm:text-2xl font-bold text-white mt-6 sm:mt-8">Socials</h2>
            <div class="flex items-center space-x-4 mt-4">
                <!-- Facebook -->
                <a
                    href="https://www.facebook.com/yoimiahs"
                    target="_blank"
                    rel="noopener noreferrer"
                    class="inline-flex items-center transition duration-300"
                    aria-label="Visit Shaira's Facebook profile"
                >
                    <img
                        src="https://cdn-icons-png.flaticon.com/512/733/733547.png"
                        alt="Facebook Logo"
                        class="w-6 h-6"
                    />
                </a>

                <!-- Instagram -->
                <a
                    href="https://instagram.com"
                    target="_blank"
                    rel="noopener noreferrer"
                    class="inline-flex items-center transition duration-300"
                    aria-label="Visit Shaira's Instagram profile"
                >
                    <img
                        src="https://cdn-icons-png.flaticon.com/512/733/733558.png"
                        alt="Instagram Logo"
                        class="w-6 h-6"
                    />
                </a>

            </div>

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
                        viewBox="0 0 24 24"
                        stroke="currentColor"
                        stroke-width="2"
                    >
                        <path
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            d="M11 17l-5-5m0 0l5-5m-5 5h12"
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