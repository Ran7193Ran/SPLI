<script>
    import Header from '../../../components/Header.svelte';
    import Footer from '../../../components/Footer.svelte';

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

<main class="flex justify-center px-4 py-10">
    <div class="w-full max-w-4xl bg-white p-8">

        <div class="mb-8">
            <h1 class="text-3xl font-bold">
                Complete Your Profile
            </h1>
            <p class="text-gray-500 mt-2">
                Please provide your personal details before continuing.
            </p>
        </div>

        <div class="grid gap-6">

            <!-- IC Number -->
            <div>
                <label class="block mb-2 font-medium">
                    IC Number
                </label>
                <input
                    type="text"
                    placeholder="XXXXXX-XX-XXXX"
                    class="w-full border rounded-lg p-3 focus:outline-none focus:ring-2 focus:ring-lime-400"
                />
            </div>

            <!-- Full Name -->
            <div>
                <label class="block mb-2 font-medium">
                    Full Name
                </label>
                <input
                    type="text"
                    placeholder="Enter your full name"
                    class="w-full border rounded-lg p-3 focus:outline-none focus:ring-2 focus:ring-lime-400"
                />
            </div>

            <!-- Gender & DOB -->
            <div class="grid md:grid-cols-2 gap-6">

                <div>
                    <label class="block mb-2 font-medium">
                        Gender
                    </label>

                    <div class="flex gap-6 mt-2">
                        <label class="flex items-center gap-2">
                            <input type="radio" name="gender" />
                            Male
                        </label>

                        <label class="flex items-center gap-2">
                            <input type="radio" name="gender" />
                            Female
                        </label>
                    </div>
                </div>

                <div>
                    <label class="block mb-2 font-medium">
                        Date of Birth
                    </label>
                    <input
                        type="date"
                        class="w-full border rounded-lg p-3 focus:outline-none focus:ring-2 focus:ring-lime-400"
                    />
                </div>

            </div>

            <!-- Phone & Email -->
            <div class="grid md:grid-cols-2 gap-6">

                <div>
                    <label class="block mb-2 font-medium">
                        Phone Number
                    </label>
                    <input
                        type="tel"
                        placeholder="012-3456789"
                        class="w-full border rounded-lg p-3 focus:outline-none focus:ring-2 focus:ring-lime-400"
                    />
                </div>

                <div>
                    <label class="block mb-2 font-medium">
                        Email Address
                    </label>
                    <input
                        type="email"
                        placeholder="student@example.com"
                        class="w-full border rounded-lg p-3 focus:outline-none focus:ring-2 focus:ring-lime-400"
                    />
                </div>

            </div>

            <!-- Buttons -->
            <div class="flex justify-end gap-4 pt-4">

                <button
                    class="px-6 py-3 rounded-lg border hover:bg-gray-100 duration-200"
                >
                    Back
                </button>

                <button
                    class="px-8 py-3 rounded-lg bg-lime-400 hover:bg-lime-500 font-semibold duration-200"
                >
                    Continue →
                </button>

            </div>

        </div>

    </div>
</main>

<Footer />