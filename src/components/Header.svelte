<script>
    let { y = 0 } = $props();

    let tabs = [
        { name: 'Features', link: '#features' },
        { name: 'About', link: '#about' },
        { name: 'Contact', link: '#contact' },
        { name: 'Intern', link: '/intern'}
    ];
</script>

<header
    class={`sticky top-0 z-50 duration-300 border-b
    ${
        y > 0
            ? 'py-4 bg-slate-950 border-violet-950 text-white'
            : 'py-6 bg-transparent border-transparent'
    }`}
>
    <div class="max-w-7xl mx-auto px-6 flex items-center justify-between">

        <a href="/">
            <h1 class="text-xl font-medium">
                <span class="font-bold poppins text-lime-400">UMS</span>pli
            </h1>
        </a>

        <!-- Navigation -->
        <nav class="hidden sm:flex items-center gap-8 ml-auto mr-6">
            {#each tabs as tab}
                <a
                    href={tab.link}
                    class="duration-200 hover:text-lime-400"
                >
                    {tab.name}
                </a>
            {/each}
        </nav>

        <!-- CTA Button -->
        <a
            href="signIn"
            class="blueShadow relative overflow-hidden px-5 py-2 rounded-full bg-white text-slate-950 font-medium group"
        >
            <div
                class="absolute inset-0 bg-lime-400 opacity-20 translate-x-[-100%] group-hover:translate-x-0 duration-300"
            ></div>

            <span class="relative z-10">
                Sign In
            </span>
        </a>

    </div>
</header>