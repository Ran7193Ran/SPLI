<script>
    import Header from '../../components/Header.svelte';
	import Footer from '../../components/Footer.svelte';

	let y = $state(0);
	let innerHeight = $state(0);
	let innerWidth = $state(0);
</script>

<svelte:window
	bind:scrollY={y}
	bind:innerHeight={innerHeight}
	bind:innerWidth={innerWidth}
/>

<Header {y} />
<main class="min-h-screen flex items-center justify-center px-4">

    <div class="w-full max-w-md bg-white rounded-md shadow-2xl p-8">

        <!-- Form Header -->
        <div class="mb-6">
            <h2 class="text-4xl font-bold text-slate-800">
                Sign In
            </h2>

            <p class="text-slate-500 mt-2">
                Stay updated on your professional world
            </p>
        </div>

        <!-- Email -->
        <div class="mb-4">
            <input
                type="email"
                placeholder="Email or Phone"
                class="w-full border border-slate-300 rounded-md px-4 py-3
                focus:outline-none focus:ring-2 focus:ring-lime-400
                focus:border-transparent"
            />
        </div>

        <!-- Password -->
        <div class="mb-2">
            <input
                type="password"
                placeholder="Password"
                class="w-full border border-slate-300 rounded-md px-4 py-3
                focus:outline-none focus:ring-2 focus:ring-lime-400
                focus:border-transparent"
            />
        </div>

        <!-- Forgot Password -->
        <div class="text-right mb-6">
            <a
                href="#"
                class="text-sky-600 hover:text-sky-800 text-sm"
            >
                Forgot Password?
            </a>
        </div>

        <!-- Sign In Button -->
        <button
            class="w-full bg-lime-400 hover:bg-lime-500
            duration-200 text-slate-900 font-semibold
            rounded-full py-3 shadow-lg"
        >
            Sign In
        </button>

        <!-- Divider -->
        <div class="flex items-center my-6">
            <div class="flex-1 border-t"></div>
            <span class="px-4 text-sm text-slate-400">OR</span>
            <div class="flex-1 border-t"></div>
        </div>

        <!-- Google Button -->
        <button
            class="w-full border border-slate-300 rounded-full py-3
            hover:bg-slate-50 duration-200"
        >
            Continue with Google
        </button>

        <!-- Register -->
        <p class="text-center mt-6 text-slate-600">
            New to UMSpli?

            <a
                href="/signUp"
                class="text-lime-500 hover:text-lime-700 font-medium"
            >
                Join Now
            </a>
        </p>

    </div>

</main>

<Footer/>