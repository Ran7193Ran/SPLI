<script>
    import Header from '../../../components/Header.svelte';
    import Footer from '../../../components/Footer.svelte';

    let y = $state(0);
    let innerHeight = $state(0);
    let innerWidth = $state(0);

    // @ts-ignore
    let selectedSector = $state([]);
    // @ts-ignore
    let selectedRole = $state([]);
    // @ts-ignore
    let selectedState = $state([]);
	let currentSector = $state('');
    let currentRole = $state('');
    let currentState = $state('');

	const sectors = [
		'Information Technology & Software',
		'Cybersecurity',
		'Networking',
		'Data Science',
		'UI/UX Design'
	];

	function addSector() {
		if (currentSector && !selectedSector.includes(currentSector)) {
			selectedSector.push(currentSector);
		}

		currentSector = '';
	}

	// @ts-ignore
	function removeSector(sector) {
		selectedSector = selectedSector.filter((item) => item !== sector);
	}

    const roles = [
        'Software Engineer',
        'Cybersecurity Analyst',
        'Data Scientist',
        'Data Analyst',
        'Network Engineer'
    ]

    function addRole(){
        if (currentRole && !selectedRole.includes(currentRole)) {
			selectedRole.push(currentRole);
		}
    }

    // @ts-ignore
    function removeRole(role) {
		selectedRole = selectedRole.filter((item) => item !== role);
	}

    const states = [
        'Perlis',
        'Kedah',
        'Pineng',
        'Perak',
        'Pahang',
        'Kelantan',
        'Terengganu',
        'Melaka',
        'Selangor',
        'Johor',
        'Sabah',
        'Sarawak'
    ]

    function addStates(){
        if (currentState && !selectedState.includes(currentState)) {
			selectedState.push(currentState);
		}
    }
    
    // @ts-ignore
    function removeState(state) {
		selectedState = selectedState.filter((item) => item !== state);
	}
</script>

<svelte:window
    bind:scrollY={y}
    bind:innerHeight={innerHeight}
    bind:innerWidth={innerWidth}
/>

<Header {y} />

<main class="flex justify-center px-4 -py-10">
    <div class=" w-full max-w-4xl p-8">
        <div class="mb-8">
            <h1 class="text-3xl font-bold">
                Preference
            </h1>
            <p class="text-gray-500 mt-2">
                Please pick any information that you are interested to applly your internships.
            </p>
        </div>

        <div class="grid gap-6">
            <div>
                <label for="" class="font-md block mb-2">Pleace choose your interested sectors.</label>
                <select name="" id="" bind:value={currentSector} onchange={addSector} class="w-md border rounded-lg p-3">
                    <option value="">Select your sector</option>
                    {#each sectors as sector}
                        <option value={sector}>{sector}</option>
                    {/each}
                </select>
            </div>
            <div class="flex flex-wrap gap-2">
                {#each selectedSector as sector}
                <div class="flex items-center gap-2 border rounded-lg px-4 py-2">
                    <span>{sector}</span>
                    <button onclick={() => removeSector(sector)} class="text-gray-500 hover:text-red-500">x</button>
                </div>
                {/each}
            </div>
        </div>
        
        <div class="grid gap-6">
            <div>
                <label for="" class="font-md block mb-2">Pleace choose 3 of your interested roles.</label>
                <select name="" id="" bind:value={currentRole} onchange={addRole} class="w-md border rounded-lg p-3">
                    <option value="">Select your roles</option>
                    {#each roles as role}
                        <option value={role}>{role}</option>
                    {/each}
                </select>
            </div>
            <div class="flex flex-wrap gap-2">
                {#each selectedRole as role}
                <div class="flex items-center gap-2 border rounded-lg px-4 py-2">
                    <span>{role}</span>
                    <button onclick={() => removeRole(role)} class="text-gray-500 hover:text-red-500">x</button>
                </div>
                {/each}
            </div>
        </div>
        
        <div class="grid gap-6">
            <div>
                <label for="" class="font-md block mb-2">Pleace choose 3 of your prefered states.</label>
                <select name="" id="" bind:value={currentState} onchange={addStates} class="w-md border rounded-lg p-3">
                    <option value="">Select your sector</option>
                    {#each states as state}
                        <option value={state}>{state}</option>
                    {/each}
                </select>
            </div>
            <div class="flex flex-wrap gap-2">
                {#each selectedState as state}
                <div class="flex items-center gap-2 border rounded-lg px-4 py-2">
                    <span>{state}</span>
                    <button onclick={() => removeState(state)} class="text-gray-500 hover:text-red-500">x</button>
                </div>
                {/each}
            </div>
        </div>
        <!-- Buttons -->
            <div class="flex justify-end gap-4 pt-4">

                <a href="/signUp/statusDetails"
                    class="px-6 py-3 rounded-lg border hover:bg-gray-100 duration-200"
                >
                    Back
                </a>

                <a href="" class="px-8 py-3 rounded-lg bg-lime-400 hover:bg-lime-500 font-semibold duration-200">Save</a>
                
            </div>
    </div>
</main>

<Footer />