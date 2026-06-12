<script>
	import Header from '../../components/Header.svelte';
	import Footer from '../../components/Footer.svelte';

	let y = $state(0);
	let innerHeight = $state(0);
	let innerWidth = $state(0);

	const internships = [
		{
			logo: 'https://placehold.co/120x120?text=LOGO',
			title: 'Support Executive Intern (MySIP)',
			company: 'Clazzy Sdn Bhd',
			location: 'Subang Jaya, Selangor',
			type: 'General Internship',
			salary: '900 MYR - 900 MYR',
			deadline: '31 August 2026'
		},
		{
			logo: 'https://placehold.co/120x120?text=LOGO',
			title: 'AI Engineering Intern',
			company: 'SYNOTECA DIGITAL',
			location: 'Kuala Lumpur, Wilayah Persekutuan',
			type: 'MySIP Advertised',
			salary: '600 MYR - 1500 MYR',
			deadline: '06 December 2026'
		},
		{
			logo: 'https://placehold.co/120x120?text=LOGO',
			title: 'Service Operations & Data Analytics Intern',
			company: 'ABBOTT LABORATORIES (MALAYSIA) SDN. BHD.',
			location: 'Petaling Jaya, Selangor',
			type: 'MySIP Advertised',
			salary: '1500 MYR - 1500 MYR',
			deadline: '01 December 2026'
		}
	];
</script>

<svelte:window
	bind:scrollY={y}
	bind:innerHeight={innerHeight}
	bind:innerWidth={innerWidth}
/>

<Header {y} />

<main class="max-w-7xl mx-auto px-6 py-10">

	<!-- Heading -->
	<div class="flex flex-col md:flex-row md:items-center md:justify-between mb-8 gap-4">
		<div>
			<h1 class="text-4xl font-bold">
				Internships Recommended (39/39)
			</h1>

			<p class="italic text-gray-500 mt-1">
				based on Scope of Study (Computer Science)
			</p>
		</div>

		<a
			href="#"
			class="text-pink-500 font-semibold hover:underline"
		>
			View all
		</a>
	</div>

	<!-- Internship Cards -->
	<div class="space-y-8">

		{#each internships as internship}
			<div
				class="bg-white rounded-3xl p-6 shadow-sm hover:shadow-md transition"
			>
				<div class="flex flex-col lg:flex-row gap-6">

					<!-- Logo -->
					<div class="flex justify-center lg:justify-start">
						<img
							src={internship.logo}
							alt={internship.company}
							class="w-24 h-24 object-contain shrink-0"
						/>
					</div>

					<!-- Content -->
					<div class="flex-1">

						<!-- Top Section -->
						<div class="flex justify-between items-start gap-4">

							<div>
								<h2 class="text-2xl font-semibold">
									{internship.title}
								</h2>

								<p class="text-pink-500 font-bold mt-2">
									{internship.company}
								</p>

								<p class="text-gray-600 mt-2 font-medium">
									{internship.location}
								</p>
							</div>

                            <div class="grid grid-cols-2 gap-2 text-lime-400">
                                <button
                                    class="text-3xl cursor-pointer"
                                >
                                    Apply Now
                                </button>
                                <button
                                    class="text-3xl cursor-pointer"
                                >
                                    ☆
                                </button>
                            </div>
                            

						</div>

						<hr class="my-5">

						<!-- Bottom Section -->
						<div
							class="flex flex-col xl:flex-row xl:items-center xl:justify-between gap-6"
						>

							<!-- Left -->
							<div class="flex flex-wrap gap-8 text-gray-700">

								<div class="flex items-center gap-2">
									
									<span class="font-medium">
										{internship.type}
									</span>
								</div>

								<div class="flex items-center gap-2">
									
									<span class="font-medium">
										{internship.salary}
									</span>
								</div>

							</div>

							<!-- Right -->
							<div
								class="flex flex-col sm:flex-row sm:items-center gap-4"
							>

								<p
									class="italic text-indigo-700 font-semibold"
								>
									Last date to apply :
									{internship.deadline}
								</p>

								<button
									class="
										px-10 py-3 rounded-full
										text-white font-semibold
										bg-gradient-to-r
										from-pink-500 to-purple-600
										hover:scale-105
										transition
									"
								>
									Apply Now
								</button>

							</div>

						</div>

					</div>

				</div>
			</div>
		{/each}

	</div>

</main>

<Footer />