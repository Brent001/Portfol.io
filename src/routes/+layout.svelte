<script>
    import "../app.css";
    import { onMount } from 'svelte';

    onMount(() => {
        // Apply the 'dark' class to the <html> element
        document.documentElement.classList.add('dark');
    });
</script>

<style>
    :global(html), :global(body) {
        height: 100%; /* Ensure the body takes up the full height of the viewport */
        margin: 0; /* Remove default margin */
        background-color: #1e2939; /* Tailwind's bg-gray-900 for a dark background */
        color: #f7fafc; /* Tailwind's gray-100 for light text */
    }

    :global(body) {
        display: flex;
        flex-direction: column; /* Arrange content in a column */
    }

    :global(main) {
        flex: 1; /* Push the footer to the bottom */
    }
</style>

<slot />