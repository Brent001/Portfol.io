<script lang="ts">
    import { fade, slide } from 'svelte/transition'; // Import fade and slide transitions
    import Footer from '$lib/components/Footer.svelte';
    import NavBar from '../../lib/components/NavBar.svelte';

    let expandedMember: number | null = null;

    const teamMembers = [
        {
            id: 1,
            name: "Irish Villanueva",
            slug: "irish-m-villanueva",
            role: "UI Consultant", // Updated role
            image: "/img/img1.jpg",
            description: "Irish is a beginner UI Consultant with basic knowledge of creating visually appealing and user-friendly interfaces. She is eager to learn and improve her skills.",
            skills: ["Basic UI Design", "Creativity", "Attention to Detail"], // Updated skills
            portfolio: "Irish has participated in team projects, contributing her creativity and attention to detail."
        },
        {
            id: 2,
            name: "Brent Kenneth Abrazaldo",
            slug: "brent-kenneth-o-abrazaldo",
            role: "Junior Developer", // Updated role
            image: "/img/img3.jpg",
            description: "Brent is a motivated junior developer with a strong focus on front-end development and some experience in back-end technologies. He is passionate about creating responsive and visually appealing web applications.",
            skills: ["Front-End Development", "Responsive Design", "Basic Back-End Knowledge"], // Updated skills
            portfolio: "Brent has contributed to various team projects by developing user interfaces and assisting with back-end integration."
        },
        {
            id: 3,
            name: "Shaira Embornal",
            slug: "shaira-embornal",
            role: "UX and UI Consultant and Assistant", // Updated role
            image: "/img/img2.jpg",
            description: "Shaira is a beginner UX and UI Consultant and Assistant with basic knowledge of designing user experiences. She is enthusiastic about learning and improving her skills.",
            skills: ["Basic UX Design", "Basic UI Design", "Communication"], // Updated skills
            portfolio: "Shaira has assisted in team projects by providing basic design support and maintaining client relationships."
        }
    ];

    function toggleExpand(id: number) {
        expandedMember = expandedMember === id ? null : id;
    }
</script>

<svelte:head>
    <title>Team Members</title>
    <meta name="description" content="Meet our talented team members who are passionate about creating innovative solutions." />
</svelte:head>

<NavBar />

<main class="flex-grow py-8 px-4 sm:px-8 bg-gray-900 text-gray-100">
    <section id="team" class="max-w-screen-xl mx-auto">
        <h2 class="text-2xl sm:text-3xl font-extrabold mb-8 sm:mb-12 text-center text-white" in:fade={{ duration: 500 }}>
            Team Members
        </h2>
        <div class="space-y-4 sm:space-y-6">
            {#each teamMembers as member}
                <button
                    class="bg-gray-800 p-4 sm:p-6 rounded-lg shadow-lg transition-all duration-500 cursor-pointer text-left w-full"
                    on:click={() => toggleExpand(member.id)}
                    aria-expanded={expandedMember === member.id}
                    in:fade={{ duration: 300 }}
                >
                    <div class="flex flex-col sm:flex-row items-center sm:items-start">
                        <img
                            src={member.image}
                            alt={member.name}
                            class="rounded-xl w-20 h-20 sm:w-32 sm:h-32 object-cover mb-4 sm:mb-0 sm:mr-6 shadow-md"
                            in:fade={{ duration: 300 }}
                        >
                        <div class="flex-1">
                            <h3 class="text-lg sm:text-xl font-semibold text-white" in:fade={{ duration: 300 }}>
                                {member.name}
                            </h3>
                            <p class="text-xs sm:text-sm text-gray-400">{member.role}</p>
                            <p class="mt-2 text-sm sm:text-base text-gray-300">
                                {member.description}
                            </p>
                        </div>
                    </div>
                    <div
                        class={`overflow-hidden transition-all ${
                            expandedMember === member.id ? 'duration-500 ease-in-out max-h-screen mt-4' : 'duration-500 ease-in-out max-h-0'
                        }`}
                    >
                        {#if expandedMember === member.id}
                            <div class="mt-4 text-sm sm:text-base text-gray-300" in:slide={{ duration: 300 }}>
                                <h4 class="text-base sm:text-lg font-bold text-white">Skills:</h4>
                                <ul class="list-disc list-inside">
                                    {#each member.skills as skill}
                                        <li>{skill}</li>
                                    {/each}
                                </ul>
                                <h4 class="mt-4 text-base sm:text-lg font-bold text-white">Portfolio:</h4>
                                <p>{member.portfolio}</p>
                                <!-- Add "See More" link -->
                                <div class="mt-4">
                                    <a
                                        href={`/team/${member.name.split(' ')[0].toLowerCase()}`}
                                        class="text-blue-400 hover:underline text-sm sm:text-base flex items-center space-x-2"
                                    >
                                        <span>More Info About {member.name.split(' ')[0]}</span>
                                        <svg
                                            xmlns="http://www.w3.org/2000/svg"
                                            class="h-4 w-4 sm:h-5 sm:w-5"
                                            fill="none"
                                            viewBox="0 0 24 24"
                                            stroke="currentColor"
                                        >
                                            <path
                                                stroke-linecap="round"
                                                stroke-linejoin="round"
                                                stroke-width="2"
                                                d="M13 7l5 5m0 0l-5 5m5-5H6"
                                            />
                                        </svg>
                                    </a>
                                </div>
                            </div>
                        {/if}
                    </div>
                </button>
            {/each}
        </div>
    </section>
</main>

<Footer />