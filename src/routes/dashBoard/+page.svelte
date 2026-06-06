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

<Header {y}  />

<main class="max-w-7xl mx-auto px-6 py-10">

    <!-- Welcome -->
    <section class="mb-8">
        <h1 class="text-4xl font-bold">
            Hello, User 👋
        </h1>
        <p class="text-slate-500 mt-2">
            Welcome back to UMSpli.
        </p>
    </section>

    <!-- Main Grid -->
    <section class="grid lg:grid-cols-3 gap-8">

        <!-- Assessment Card -->
        <div class="lg:col-span-2 bg-white shadow-xl rounded-2xl p-8">

            <div class="mb-6">
                <h2 class="text-2xl font-bold text-lime-500">
                    Start your internship journey
                </h2>

                <p class="text-slate-600 mt-3">
                    Complete the assessment and let UMSpli match you with
                    companies that fit your skills, interests and career goals.
                </p>
            </div>

            <div class="flex gap-4">
                <a
                    href="/quiz"
                    class="bg-lime-400 hover:bg-lime-500 px-6 py-3 rounded-full font-medium duration-200"
                >
                    Start Questionnaire →
                </a>

                <button
                    class="border border-slate-300 px-6 py-3 rounded-full hover:bg-slate-100 duration-200"
                >
                    Learn More
                </button>
            </div>

        </div>

        <!-- Profile Card -->
        <div class="bg-white shadow-xl rounded-2xl p-8">

            <div class="flex items-center justify-between mb-6">

                <div class="flex items-center gap-4">

                    <div class="grid w-16 h-16 rounded-full bg-slate-200 flex items-center justify-center">
                        <div class="bg-slate-400 w-5 h-5 rounded-full flex items-center justify-center mx-auto"></div>
                        <div class="bg-slate-400 w-7 h-5"></div>
                    </div>

                    <div>
                        <h3 class="font-bold text-lg">
                            Username
                        </h3>

                        <p class="text-sm text-slate-500">
                            Student
                        </p>
                    </div>

                </div>

                <button
                    class="text-lime-500 hover:text-lime-600"
                >
                    Edit
                </button>

            </div>

            <div class="space-y-5">

                <div>
                    <p class="text-sm text-slate-500">
                        Email
                    </p>

                    <p class="font-medium">
                        email@gmail.com
                    </p>
                </div>

                <div>
                    <p class="text-sm text-slate-500">
                        Phone Number
                    </p>

                    <p class="font-medium">
                        012-000-0060
                    </p>
                </div>

                <div>
                    <p class="text-sm text-slate-500">
                        Role
                    </p>

                    <div class="flex items-center gap-3">
                        <p class="font-medium">
                            Student
                        </p>

                        <button class="text-lime-500 text-sm">
                            Change Role
                        </button>
                    </div>
                </div>

            </div>

        </div>

    </section>

</main>
<Footer />