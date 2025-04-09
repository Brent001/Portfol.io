<script lang="ts">
    export let status: number;
    export let error: { message?: string };
    import { fade } from 'svelte/transition'; // Import fade transition
</script>

<section class="bg-gray-900 text-gray-100">
    <div class="container flex items-center min-h-screen px-4 py-12 mx-auto">
        <div class="text-center w-full" in:fade={{ duration: 500 }}>
            <!-- Error Code and Title -->
            <div class="mb-6">
                <h1 class="text-4xl font-extrabold text-blue-500 sm:text-5xl lg:text-6xl">
                    404 Error {status}
                </h1>
                <h2 class="mt-4 text-lg font-bold text-white sm:text-xl lg:text-2xl">
                    {error?.message || "Page not found"}
                </h2>
            </div>

            <!-- Error Description -->
            <p class="mt-4 text-gray-400 text-sm sm:text-base lg:text-lg">
                {status === 404
                    ? "The page you are looking for doesn't exist."
                    : "Sorry, the page you are looking for doesn't exist."}
            </p>

            <!-- Buttons -->
            <div class="flex flex-row justify-center items-center mt-6 gap-4">
                <button
                    class="flex items-center justify-center px-4 py-2 text-sm text-gray-900 bg-gray-100 border rounded-lg gap-x-2 hover:bg-gray-200 dark:bg-gray-800 dark:text-gray-200 dark:border-gray-700 dark:hover:bg-gray-700"
                    on:click={() => history.back()}
                >
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-5 h-5 rtl:rotate-180">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M6.75 15.75L3 12m0 0l3.75-3.75M3 12h18" />
                    </svg>
                    <span>Go back</span>
                </button>

                <a
                    href="/"
                    class="px-4 py-2 text-sm tracking-wide text-white bg-blue-500 rounded-lg hover:bg-blue-600"
                >
                    Take me home
                </a>
            </div>
        </div>
    </div>
</section>
