<script lang="ts">
    import { fade } from 'svelte/transition'; // Import the fade transition
    import Footer from '$lib/components/Footer.svelte';
    import NavBar from '../../lib/components/NavBar.svelte';

    let expandedMember: number | null = null;

    const teamMembers = [
        {
            id: 1,
            name: "Irish Villanueva",
            slug: "irish-m-villanueva",
            role: "BS-Tourism",
            image: "/img/img1.jpg",
            description: "Irish specializes in event planning and logistics, bringing creativity and organization to every project.",
            skills: ["Event Planning", "Logistics Management", "Creative Problem Solving"],
            portfolio: "Irish has successfully organized multiple events for the team, ensuring smooth execution and client satisfaction."
        },
        {
            id: 2,
            name: "Brent Kenneth Abrazaldo",
            slug: "brent-kenneth-o-abrazaldo",
            role: "BS-Computer Science",
            image: "/img/img3.jpg",
            description: "Brent is a software developer with expertise in full-stack development and innovative problem-solving.",
            skills: ["Full-Stack Development", "Database Management", "Problem Solving"],
            portfolio: "Brent has developed key features for the team's projects, ensuring high performance and user satisfaction."
        },
        {
            id: 3,
            name: "Shaira Embornal",
            slug: "shaira-embornal",
            role: "BS-Tourism",
            image: "/img/img2.jpg",
            description: "Shaira excels in customer relations and hospitality, ensuring seamless experiences for clients.",
            skills: ["Customer Relations", "Hospitality Management", "Communication"],
            portfolio: "Shaira has played a key role in maintaining strong client relationships and ensuring project success."
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

<main
    class="flex-grow py-8 px-4 sm:px-8 bg-gray-900 text-gray-100"
    in:fade={{ duration: 300 }}
    out:fade={{ duration: 300 }}
>
    <section id="team" class="max-w-screen-xl mx-auto">
        <h2 class="text-2xl sm:text-3xl font-extrabold mb-8 sm:mb-12 text-center text-white">Team Members</h2>
        <div class="space-y-4 sm:space-y-6">
            {#each teamMembers as member}
                <button
                    class="bg-gray-800 p-4 sm:p-6 rounded-lg shadow-lg transition-all duration-500 cursor-pointer text-left w-full"
                    on:click={() => toggleExpand(member.id)}
                    aria-expanded={expandedMember === member.id}
                >
                    <div class="flex flex-col sm:flex-row items-center sm:items-start">
                        <img
                            src={member.image}
                            alt={member.name}
                            class="rounded-xl w-20 h-20 sm:w-32 sm:h-32 object-cover mb-4 sm:mb-0 sm:mr-6 shadow-md"
                        >
                        <div class="flex-1">
                            <h3 class="text-lg sm:text-xl font-semibold text-white">
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
                            <div class="mt-4 text-sm sm:text-base text-gray-300">
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