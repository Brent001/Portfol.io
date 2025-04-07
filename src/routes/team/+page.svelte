<script lang="ts">
    import Footer from '$lib/components/Footer.svelte';
    import NavBar from '../../lib/components/NavBar.svelte';

    let expandedMember: number | null = null;

    const teamMembers = [
        {
            id: 1,
            name: "Irish M. Villanueva",
            role: "BS-Tourism",
            image: "/img/img1.jpg",
            description: "Irish specializes in event planning and logistics, bringing creativity and organization to every project.",
            skills: ["Event Planning", "Logistics Management", "Creative Problem Solving"],
            portfolio: "Irish has successfully organized multiple events for the team, ensuring smooth execution and client satisfaction."
        },
        {
            id: 2,
            name: "Brent Kenneth O. Abrazaldo",
            role: "BS-Computer Science",
            image: "/img/img3.jpg",
            description: "Brent is a software developer with expertise in full-stack development and innovative problem-solving.",
            skills: ["Full-Stack Development", "Database Management", "Problem Solving"],
            portfolio: "Brent has developed key features for the team's projects, ensuring high performance and user satisfaction."
        },
        {
            id: 3,
            name: "Shaira Embornal",
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

<NavBar />

<main class="flex-grow py-16 px-4 sm:px-8 bg-gray-900 text-gray-100">
    <section id="team" class="max-w-screen-xl mx-auto">
        <h2 class="text-4xl font-extrabold mb-12 text-center text-white">Team Wiki</h2>
        <div class="space-y-6">
            {#each teamMembers as member}
                <div
                    class="bg-gray-800 p-6 rounded-lg shadow-lg transition-all duration-500 cursor-pointer"
                    on:click={() => toggleExpand(member.id)}
                >
                    <div class="flex items-center">
                        <img src={member.image} alt={member.name} class="rounded-xl w-24 h-24 sm:w-32 sm:h-32 object-cover mr-4 sm:mr-6 shadow-md">
                        <div>
                            <h3 class="text-xl sm:text-2xl font-semibold text-white">{member.name}</h3>
                            <p class="text-xs sm:text-sm text-gray-400">{member.role}</p>
                            <p class="mt-2 text-sm sm:text-base text-gray-300">{member.description}</p>
                        </div>
                    </div>
                    <div
                        class={`overflow-hidden transition-all duration-500 ease-in-out ${expandedMember === member.id ? 'max-h-screen mt-4' : 'max-h-0'}`}
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
                            </div>
                        {/if}
                    </div>
                </div>
            {/each}
        </div>
    </section>
</main>

<Footer />