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
        {   title: 'Intelectual Stimulation',
            question: ['To have opportunities for problem solving', 'To be intellectually stimulated', 'To have opportunities to learn new things']
        },
        {   title: 'Recognintion',
            question: ['To gain recognition in my work', 'To know that others consider my work important', 'That others look up to me for my contribution']
        },
        {
            title: 'Achievement',
            question: ['To experience the satisfaction of accomplishing tasks', 'To know by the results that I have done a good job', 'To see the result of my efforts']
        },
        {
            title:'Independence',
            question: ['To be free to manage my own workload', 'To have choice about the way that I approach tasks', 'To set up my own business']
        },
        {
            title: 'Variety',
            question: ['To be involved in work with a high level of change', 'To have a role that requires a range of skills', 'To have variety in my work']
        }
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
			Self Value Survey
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
                {#each questions as section}
            <h3 class="col-span-6 text-xl font-bold mt-8 mb-2">
                {section.title}
            </h3>
                {#each section.question as item}
                    <div class="col-span-6 grid grid-cols-[1fr_repeat(5,40px)] gap-3 items-center py-3 border-b border-slate-200">
                        <p>{item}</p>
                        {#each infos as info}
                            <button
                                class={`w-10 h-10 rounded-full border-2 ${info.color} cursor-pointer`}
                                aria-label={info.title}
                            ></button>
                        {/each}
                    </div>
                {/each}
            {/each}
		    </div>
	    </div>
        <a href="/quiz" class=" rounded-full px-8 py-3 bg-lime-400">Submit</a>
	</div>

</main>

<Footer />