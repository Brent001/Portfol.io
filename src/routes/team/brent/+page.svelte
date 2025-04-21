<script>
    import Footer from '$lib/components/Footer.svelte';
    import NavBar from '$lib/components/NavBar.svelte';
    import { fade, scale } from 'svelte/transition';

    const member = {
        name: "Brent Kenneth O. Abrazaldo",
        role: "Junior Developer",
        image: "/img/img3.jpg",
        description: `Hello, I am Brent Kenneth O. Abrazaldo, a 20-year-old Junior Developer from Pogo, Mangaldan, Pangasinan. 
        I specialize in front-end development and have some experience in back-end technologies. 
        I am passionate about creating responsive and visually appealing web applications that provide seamless user experiences. 
        My dedication to learning and improving my skills allows me to contribute effectively to team projects.`,
        skills: ["Front-End Development", "Responsive Design", "Basic Back-End Knowledge"],
        portfolio: "Brent has contributed to various team projects by developing user interfaces and assisting with back-end integration.",
        workExperience: "None", // Added work experience
        education: {
            elementary: "Pogo-Palua Elementary School",
            highschool: "Mangaldan Integrated School SPED Center",
            seniorHighschool: "Mangaldan National Highschool", // Added senior high school
            college: "Metro Dagupan Colleges"
        },
        educationLogos: {
            elementary: "/img/logos/pogo-palua-elementary.png",
            highschool: "/img/logos/mangaldan-integrated-school.png",
            seniorHighschool: "/img/logos/mangaldan-national-highschool.png", // Added senior high school logo
            college: "/img/logos/metro-dagupan-colleges.png"
        },
        personalInfo: {
            age: 20,
            address: "Pogo, Mangaldan, Pangasinan"
        }
    };
</script>

<svelte:head>
    <title>About Brent Kenneth O. Abrazaldo</title>
    <meta name="description" content="Learn more about Brent Kenneth O. Abrazaldo, a Junior Developer with a passion for front-end development and responsive design." />
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
                    <img src={member.educationLogos.seniorHighschool} alt="Senior High School Logo" class="h-6 w-6 sm:h-8 sm:w-8 object-contain" />
                    <span><strong>Senior High School:</strong> {member.education.seniorHighschool}</span>
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
                    href="https://www.facebook.com/brentkenneth504"
                    target="_blank"
                    rel="noopener noreferrer"
                    class="inline-flex items-center transition duration-300"
                    aria-label="Visit Brent's Facebook profile"
                >
                    <img
                        src="https://cdn-icons-png.flaticon.com/512/733/733547.png"
                        alt="Facebook Logo"
                        class="w-6 h-6"
                    />
                </a>

                <!-- GitHub -->
                <a
                    href="https://github.com/Brent001"
                    target="_blank"
                    rel="noopener noreferrer"
                    class="inline-flex items-center transition duration-300"
                    aria-label="Visit Brent's GitHub profile"
                >
                    <img
                        src="https://cdn-icons-png.flaticon.com/512/733/733553.png"
                        alt="GitHub Logo"
                        class="w-6 h-6"
                    />
                </a>

                <!-- Instagram -->
                <a
                    href="https://www.instagram.com/brentph504/"
                    target="_blank"
                    rel="noopener noreferrer"
                    class="inline-flex items-center transition duration-300"
                    aria-label="Visit Brent's Instagram profile"
                >
                    <img
                        src="https://cdn-icons-png.flaticon.com/512/733/733558.png"
                        alt="Instagram Logo"
                        class="w-6 h-6"
                    />
                </a>

                <!-- SoundCloud -->
                <a
                    href="https://soundcloud.com/brent-kenneth-abrazaldo"
                    target="_blank"
                    rel="noopener noreferrer"
                    class="inline-flex items-center transition duration-300"
                    aria-label="Visit Brent's SoundCloud profile"
                >
                    <img
                        src="https://cdn-icons-png.flaticon.com/512/145/145809.png"
                        alt="SoundCloud Logo"
                        class="w-6 h-6"
                    />
                </a>

                <!-- YouTube -->
                <a
                    href="https://www.youtube.com/@brentkennethabrazaldo1387"
                    target="_blank"
                    rel="noopener noreferrer"
                    class="inline-flex items-center transition duration-300"
                    aria-label="Visit Brent's YouTube channel"
                >
                    <img
                        src="https://cdn-icons-png.flaticon.com/512/1384/1384060.png"
                        alt="YouTube Logo"
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