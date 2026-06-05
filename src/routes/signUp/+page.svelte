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
                Sign Up
            </h2>

            <p class="text-slate-500 mt-2">
                Pick your role
            </p>
            <div class="grid grid-cols-2 gap-2">
                <button class="border-1 rounded-md p-2 bg-slate-200 hover:bg-slate-200 duration-200">Student</button>
                <button class="border-1 rounded-md p-2 hover:bg-slate-200 duration-200">Company</button>
            </div>
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

        <!-- Confirm Password -->
        <div class="mb-2">
            <input
                type="password"
                placeholder="Confirm Password"
                class="w-full border border-slate-300 rounded-md px-4 py-3
                focus:outline-none focus:ring-2 focus:ring-lime-400
                focus:border-transparent"
            />
        </div>

        <!-- Sign In Button -->
        <a class="justify-center bg-lime-400 hover:bg-lime-500 shadow-lg font-semibold rounded-full p-3 flex" href="/signUp/personalInfo">Continue</a>

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

    </div>

</main>

<Footer/>