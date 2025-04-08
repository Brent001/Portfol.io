<script>
    import Footer from '$lib/components/Footer.svelte';
    import NavBar from '../../lib/components/NavBar.svelte';

    let name = '';
    let email = '';
    let message = '';

    // Access the API key from environment variables
    const WEB3FORMS_ACCESS_KEY = import.meta.env.VITE_WEB3FORMS_ACCESS_KEY;

    async function handleSubmit() {
        const formData = {
            access_key: WEB3FORMS_ACCESS_KEY,
            name,
            email,
            message,
        };

        try {
            const response = await fetch('https://api.web3forms.com/submit', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json',
                },
                body: JSON.stringify(formData),
            });

            if (response.ok) {
                alert('Thank you! Your message has been sent.');
                name = '';
                email = '';
                message = '';
            } else {
                alert('Oops! Something went wrong. Please try again.');
            }
        } catch (error) {
            console.error('Error submitting the form:', error);
            alert('An error occurred. Please try again later.');
        }
    }
</script>

<style>
    main {
        background: linear-gradient(135deg, #1e293b, #0f172a);
    }

    form {
        animation: fadeIn 0.8s ease-in-out;
    }

    @keyframes fadeIn {
        from {
            opacity: 0;
            transform: translateY(20px);
        }
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }
</style>

<NavBar />

<main class="flex flex-col items-center px-4 py-8 min-h-screen text-white">
    <h1 class="text-3xl font-bold mb-6 text-center sm:text-4xl">Contact Us</h1>
    <form 
        on:submit|preventDefault={handleSubmit} 
        class="w-full max-w-lg p-6 rounded-lg shadow-lg bg-gray-800 sm:p-8"
    >
        <div class="mb-4">
            <label for="name" class="block text-sm font-medium mb-1">Name:</label>
            <input 
                type="text" 
                id="name" 
                bind:value={name} 
                required 
                class="w-full px-3 py-2 border border-gray-600 rounded-md shadow-sm focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500 bg-gray-700 text-gray-100"
            />
        </div>
        <div class="mb-4">
            <label for="email" class="block text-sm font-medium mb-1">Email:</label>
            <input 
                type="email" 
                id="email" 
                bind:value={email} 
                required 
                class="w-full px-3 py-2 border border-gray-600 rounded-md shadow-sm focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500 bg-gray-700 text-gray-100"
            />
        </div>
        <div class="mb-4">
            <label for="message" class="block text-sm font-medium mb-1">Message:</label>
            <textarea 
                id="message" 
                bind:value={message} 
                required 
                class="w-full px-3 py-2 border border-gray-600 rounded-md shadow-sm focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500 bg-gray-700 text-gray-100"
            ></textarea>
        </div>
        <button 
            type="submit" 
            class="w-full bg-blue-500 text-white py-2 px-4 rounded-md hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-offset-2"
        >
            Send
        </button>
    </form>
</main>

<Footer />