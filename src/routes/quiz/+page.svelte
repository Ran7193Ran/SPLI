<script>
	import Header from '../../components/Header.svelte';
	import Footer from '../../components/Footer.svelte';

	let y = $state(0);
	let innerHeight = $state(0);
	let innerWidth = $state(0);

	const assessments = [
		{
			title: 'Work Interests',
			description: 'Discover your key areas of interest and the preferences that will make the best job match for you.',
			progress: 0,
			link: '/quiz/workInterest'
		},
		{
			title: 'Work Values',
			description: 'Explore the work values that are important for you in your future career.',
			progress: 0,
			link: '/quiz/workValues'
		},
		{
			title: 'Employability',
			description: 'Discover the work competencies that will make you highly employable.',
			progress: 0,
			link: '/quiz/employability'
		},
		{
			title: 'Future of Work',
			description: 'Discover the key competencies that you should develop for work in the future.',
			progress: 0,
			link: '/quiz/future-of-work'
		},
		{
			title: 'Cognitive Ability Assessment',
			description: 'Evaluate your problem solving, reasoning, and analytical skills to understand your cognitive strengths.',
			progress: 0,
			link: '/quiz/cognitive-ability'
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

	<!-- Page Header -->
	<section class="mb-10">
		<h1 class="text-4xl font-bold">
			Career Assessments
		</h1>

		<p class="text-slate-500 mt-2">
			Complete all assessments to receive personalised internship recommendations.
		</p>
	</section>

	<!-- Progress Card -->
	<section class="mb-10">
		<div class="bg-lime-50 border border-lime-200 rounded-2xl p-6">

			<div class="flex justify-between items-center mb-4">
				<h2 class="text-xl font-semibold">
					Overall Progress
				</h2>

				<span class="text-lime-600 font-medium">
					0%
				</span>
			</div>

			<div class="w-full bg-lime-100 rounded-full h-3">
				<div
					class="bg-lime-500 h-3 rounded-full"
					style="width: 0%;"
				></div>
			</div>

			<p class="mt-3 text-slate-600">
				0 of {assessments.length} assessments completed
			</p>

		</div>
	</section>

	<!-- Assessment Cards -->
	<section class="grid md:grid-cols-2 gap-6">

		{#each assessments as assessment}

			<div
				class="bg-white shadow-lg rounded-2xl p-6 flex flex-col gap-5 border border-slate-100 hover:shadow-xl duration-200"
			>

				<div>
					<h2 class="text-2xl font-semibold">
						{assessment.title}
					</h2>

					<p class="text-slate-600 mt-3">
						{assessment.description}
					</p>
				</div>

				<div>

					<div class="flex justify-between mb-2">
						<span class="text-sm text-slate-500">
							Progress
						</span>

						<span class="text-sm text-red-500">
							{assessment.progress}%
						</span>
					</div>

					<div class="w-full bg-slate-200 rounded-full h-2">
						<div
							class="bg-lime-400 h-2 rounded-full"
							style={`width:${assessment.progress}%`}
						></div>
					</div>

				</div>

				<a
					href={assessment.link}
					class="mt-auto bg-lime-400 hover:bg-lime-500 duration-200 rounded-full px-5 py-3 text-center font-medium"
				>
					Start Assessment →
				</a>

			</div>

		{/each}

	</section>

</main>

<Footer />