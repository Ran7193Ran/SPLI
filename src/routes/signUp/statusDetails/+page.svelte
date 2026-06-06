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
                Complete Your Study Status
            </h1>
            <p class="text-gray-500 mt-2">
                Please provide your academic details before continuing.
            </p>
        </div>

        <div class="grid gap-10">

            <!-- Academic qualification -->
            <div>
                <label for="" class="block mb-2 font-medium">
                    What is your current academic qualification?
                </label>
                <select name="" id="" class="w-full border rounded-lg p-3 focus:none focus:ring-2 focus:ring-lime-400">
                    <option value="">Select your academic </option>
                    <option value="">SPM</option>
                    <option value="">Diploman</option>
                    <option value="">Bachelor Degree</option>
                </select>
            </div>

            <!-- Institue type -->
            <div>
                <label for="" class="block mb-2 font-medium">
                    What is your institution type?
                </label>
                <div class="flex gap-6 mt-2">
                        <label class="flex items-center gap-2">
                            <input type="radio" name="gender" />
                            I'm studying in Malaysia or on exchange programme
                        </label>

                        <label class="flex items-center gap-2">
                            <input type="radio" name="gender" />
                            I'm studying abroad
                        </label>
                    </div>
            </div>

            <!-- Institute & Campus -->
            <div class="grid md:grid-cols-2 gap-6">

                <div>
                    <label for="" class="block mb-2 font-medium">
                        What is the name of your institution?
                    </label>

                    <select name="" id="" class="w-full border rounded-lg p-3 focus:none focus:ring-2 focus:ring-lime-400">
                        <option value="">Select your Institute </option>
                        <option value="">University Malaysia Sabah (UMS)</option>
                        <option value="">University Sultan Zainal Abidin (UniSZA)</option>
                        <option value="">University Teknologi MARA (UiTM)</option>
                    </select>
                </div>

                <div>
                    <label for="" class="block mb-2 font-medium">
                        Which campus are you going?
                    </label>
                    <select name="" id="" class="w-full border rounded-lg p-3 focus:none focus:ring-2 focus:ring-lime-400">
                        <option value="">Select your Campus </option>
                        <option value="">Kota Kinabalu</option>
                        <option value="">Labuan</option>
                        <option value="">Sandakan</option>
                    </select>
                </div>

            </div>

            <!-- Faculty & Programme -->
            <div class="grid md:grid-cols-2 gap-6">

                <div>
                    <label for="" class="block mb-2 font-medium">
                        What is your faculty?
                    </label>
                    <select name="" id="" class="w-full border rounded-lg p-3 focus:none focus:ring-2 focus:ring-lime-400">
                        <option value="">Select your Faculty </option>
                        <option value="">Faculty of  Computer & Informatics</option>
                        <option value="">Faculty of Science Technology</option>
                        <option value="">Faculty of Engineering</option>
                    </select>
                </div>

                <div>
                    <label for="" class="block mb-2 font-medium">
                        Which programme are you studying?
                    </label>
                    <select name="" id="" class="w-full border rounded-lg p-3 focus:none focus:ring-2 focus:ring-lime-400">
                        <option value="">Select your Programme </option>
                        <option value="">Software Engineering</option>
                        <option value="">Network Engineering</option>
                        <option value="">Data Science</option>
                    </select>
                </div>

            </div>

            <div>
                <label for="" class="block mb-2 font-medium">
                    What is your scope of study?
                </label>
                <select name="" id="" class="w-full border rounded-lg p-3 focus:none focus:ring-2 focus:ring-lime-400">
                    <option value="">Select your scope </option>
                    <option value="">Computer Science</option>
                </select>
            </div>

            <div class="grid md:grid-cols-2 gap-6">

                <div>
                    <label for="" class="block mb-2 font-medium">
                        When is your university enrolment date?
                    </label>
                    <input type="date" name="" id="" class="w-full border rounded-lg p-3 ">
                </div>

                <div>
                    <label for="" class="block mb-2 font-medium">
                        When is your expected graduation date?
                    </label>
                    <input type="date" name="" id="" class="w-full border rounded-lg p-3 ">
                </div>
            </div>

            <div>
                <label for="" class="block mb-2 font-medium">
                    What's the current year of your study?
                </label>
                <select name="" id="" class="w-full border rounded-lg p-3 focus:none focus:ring-2 focus:ring-lime-400">
                    <option value="">Select your year </option>
                    <option value="">Year 1</option>
                    <option value="">Year 2</option>
                    <option value="">Year 3</option>
                    <option value="">Year 4</option>
                </select>
            </div>

            <div>
                <label for="" class="block mb-2 font-medium">
                    What is your current grade?
                </label>
                <div class="flex gap-4 mt-2 w-full">
                    <label class="flex-1 flex justify-center items-center">
                        <input type="radio" name="englishTest" />
                        CGPA
                    </label>
                    <label class="flex-1 flex justify-center items-center">
                        <input type="radio" name="englishTest" />
                        grade
                    </label>
                    <label class="flex-1 flex justify-center items-center">
                        <input type="radio" name="englishTest" />
                        Others
                    </label>
                    <label class="flex-1 flex justify-center items-center">
                        <input type="radio" name="englishTest" />
                        No Current Grade
                    </label>
                </div>
                <input type="text" class="w-md border rounded-lg p-3 focus:none focus:ring-2 focus:ring-lime-400" placeholder="Insert your grade">
            </div>

            <div>
                <label for="" class="block mb-2 font-medium">
                    What is the english equivalency test you have taken?
                </label>
                <div class="flex gap-4 mt-2 w-full">
                    <label class="flex-1 flex justify-center items-center">
                        <input type="radio" name="englishTest" />
                        MUET
                    </label>
                    <label class="flex-1 flex justify-center items-center">
                        <input type="radio" name="englishTest" />
                        CEFR
                    </label>
                    <label class="flex-1 flex justify-center items-center">
                        <input type="radio" name="englishTest" />
                        TOEFL
                    </label>
                    <label class="flex-1 flex justify-center items-center">
                        <input type="radio" name="englishTest" />
                        IELTS
                    </label>
                </div>
                <select name="" id="" class="w-md border rounded-lg p-3 focus:none focus:ring-2 focus:ring-lime-400">
                    <option value="">Select</option>
                    <option value="">Band 1</option>
                    <option value="">Band 2</option>
                    <option value="">Band 3</option>
                    <option value="">Band 4</option>
                    <option value="">Band 5</option>
                </select>
            </div>

            <!-- Buttons -->
            <div class="flex justify-end gap-4 pt-4">

                <a href="/signUp/personalInfo" class="px-6 py-3 rounded-lg border hover:bg-gray-100 duration-200">Back</a>

                <a href="/signUp/preference" class="px-8 py-3 rounded-lg bg-lime-400 hover:bg-lime-500 font-semibold duration-200">
                    Continue →
                </a>

            </div>

        </div>

    </div>
</main>

<Footer />