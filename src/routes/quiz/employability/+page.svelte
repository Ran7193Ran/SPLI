<script>
	import Header from '../../../components/Header.svelte';
	import Footer from '../../../components/Footer.svelte';

	let y = $state(0);
	let innerHeight = $state(0);
	let innerWidth = $state(0);

	let infos = [
		{ title: 'Strongly Disagree', color: 'border-red-500', bgColor: 'bg-red-500' },
		{ title: 'Disagree', color: 'border-orange-400', bgColor: 'bg-orange-400' },
		{ title: 'Unsure', color: 'border-yellow-400', bgColor: 'bg-yellow-400' },
		{ title: 'Agree', color: 'border-sky-500', bgColor: 'bg-sky-500' },
		{ title: 'Strongly Agree', color: 'border-green-500', bgColor: 'bg-green-500' }
	];

    let questions = [
        'I am able to list down the different types of value that a single idea can have',  'I find ways to improve myself by reflecting on what I have learnt from projects at school or work', 'I am able to form teams and networks of talent according to the needs of the project I am working on', 'I believe in my ability to carry out plans in my school or workplace despite barriers and challenges that arise', 'I am able to develop financial plans for a project at school or work that will continue even if I leave', 'I can visualise the future I want to live in', 'I can find examples of valuable ideas that solve problems faced in school or work settings', 'I know I can do well and what I cannot do well', 'in the past, I have used my ideas to solve existing problems I face at school or work', 'I know why integrity and ethical behaviour is important at work or school'
        ];
</script>

<svelte:window
	bind:scrollY={y}
	bind:innerHeight={innerHeight}
	bind:innerWidth={innerWidth}
/>

<Header {y} />

<main class="max-w-5xl mx-auto px-6 py-10">

	<div class="bg-white rounded-3xl shadow-lg p-8">

		<h1 class="text-2xl font-bold mb-6">
			Find out if you are capable to be employ
		</h1>

		<!-- Legend -->
		<div class="flex flex-wrap gap-6 mb-10 justify-center rounded-2xl border p-3">
			{#each infos as info}
				<div class="flex items-center gap-2">
					<div class={`w-4 h-4 rounded-full ${info.bgColor}`}></div>
					<span class="text-sm text-gray-700">{info.title}</span>
				</div>
			{/each}
		</div>

		<!-- Question -->
		<div class="p-6">
			

			<div class="grid grid-cols-5 gap-4">
                {#each questions as question}
                    <p class="col-span-5">{question}</p>
                    {#each infos as info}
					<button
						class={`border-3 w-10 h-10 mx-auto rounded-full transition ac ${info.color} focus:bg-lime-400 cursor-pointer`}
						aria-label={info.title}
					></button>
                    
				{/each}
                    <div class="col-span-5 h-0.5 w-full bg-slate-100 rounded-full"></div>
                {/each}
				
			</div>

		</div>
        <a href="/quiz" class=" rounded-full px-8 py-3 bg-lime-400">Submit</a>
	</div>

</main>

<Footer />