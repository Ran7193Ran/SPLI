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
        'Using technology and digital devices','Being well-organised', 'Logical processes and procedures', 'Selling Goods', 'Creating movie visual/special effects', 'Outdoor tasks such as gardening', 'Administritive tasks', 'Helping others', 'Graphix design', 'Putting DIY furniture together', 'Financial planning and budgeting', 'Keeping financial accounts', 'Finding our how things work', 'Researching ways to improve the envirnment', 'Repairing appliances', 'Working with details in a task', 'Working with other people in a team', 'Coaching children or adults', 'Performing arts', 'Researching economic solutions to global problems', 'Investing climate change solutions', 'Experimenting or inovating', 'Taking part in creative productions such a plays, performance, art shows', 'Leading a team', 'Leading other people', 'Influencing how others think', 'Doing creative work that gives me personal satisfaction', 'Vehicle maintenance', 'Representing peoples rights', 'Working with numbers', 'Expressing myself creatively e.g writing content for social media', 'Working with children or young people', 'Building or construction', 'Finding innovative solutions to problems', 'innovative solutions to problems', 'engaging in art e.g. music, dance, dramatic performance', 'media production such as photography, design, writing', 'researching a topic I am working on', 'organising data e.g. working with spreadsheets', 'writing poetry, short stories, or drama scripts', 'Designing new products', 'composing or arranging music', 'learning new things', 'connecting with other people around me', 'improving others emotional wellbeing', 'researching new medicines or medical products', 'Teaching others', 'Organising my surroundings', 'a regular daily routine', 'Cooking or crafting products', 'Performing chemical experiments', 'Working with tools', 'improving others physical wellbeing', 'operating or repairing machinery', 'Communicating new ideas', 'promoting new products or services', 'Giving advices and guidance', 'tasks with clear instructions and known outcomes', 'starting up my own business', 'software coding (or artifical intelligence)', 'Having time to work something out for myself'
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
			Career Interest Survey
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
			<h2 class="font-semibold text-lg mb-6">
				I would like work that involves.
			</h2>

			<div class="grid grid-cols-5 gap-4">
                {#each questions as question}
                    <p class="col-span-5">{question}</p>
                    {#each infos as info}
					<button
						class={`border-3 w-10 h-10 mx-auto rounded-full transition ac ${info.color} focus:bg-lime-400`}
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