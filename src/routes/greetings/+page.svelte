<script>
  // Importing reusable Navbar and Footer components
  import Footer from '$lib/shared/ui/components/footer/Footer.svelte';
  import Navbar from '$lib/shared/ui/components/navbar/Navbar.svelte';

  // Variables to hold username and the CA code
  let username = "Username";
  let caCode = '';

  // Function to trigger on clicking "Enter CA Code" button
  const enterCode = () => {
    alert(`Entered CA code: ${caCode}`);
  };

  // Function to trigger on clicking "Get CA Code" button
  const getCode = () => {
    alert('Generating CA code...');
  };
</script>

<!-- Full-page container with vertical layout and gradient background -->
<div class="relative min-h-screen w-screen flex flex-col text-white bg-[linear-gradient(190deg,#01d6f4_0%,#039ff1_1.5%,#0575ba_4%,#074f88_8%,#04528e_13%,#005698_14%,#001423_18%,#000910_19%,#000000_100%)] overflow-x-hidden">
  
  <!-- Background Image: only shown on small screens with partial transparency -->
  <div class="absolute inset-0 z-0 md:hidden opacity-40">
    <img src="src/lib/assets/images/hands.png" alt="Hands Background" class="w-full h-full object-cover" />
  </div>

  <!-- Navbar at the top -->
  <Navbar />

  <!-- Main content section -->
  <main class="relative z-10 flex-1 px-6 py-10 flex flex-col justify-center">
    
    <!-- Wrapper for left (text/buttons) and right (image) sections -->
    <div class="flex flex-col lg:flex-row justify-between items-center gap-10 mt-6 mb-6">
      
      <!-- Left Section: Heading, Description, and Buttons -->
      <div class="max-w-full lg:max-w-[50%] lg:ml-16 text-center md:text-left">
        
        <!-- Personalized greeting -->
        <h1 class="text-4xl md:text-6xl lg:text-7xl font-extrabold mb-6 font-[Playfair Display] mt-8 md:mt-0">
          Hi, <span class="text-[#3fdcff]">{username}</span>
        </h1>

        <!-- Description of the fest -->
        <p class="text-gray-300 text-base md:text-xl mb-8">
          Petrichor '26 isn't just a fest — it's a whole dang multiverse. Hack all night, dance all day, vibe like there's no Monday. Win stuff, lose sleep, make memories — or don't, who cares?!
        </p>

        <!-- Action Buttons -->
        <div class="flex flex-col gap-6 items-center md:items-start">
          
          <!-- Button to enter CA code -->
          <button
            on:click={enterCode}
            class="font-sans w-[220px] md:w-[180px] lg:w-[250px] text-lg md:text-xl lg:text-2xl px-6 md:px-6 lg:px-10 py-5 md:py-4 lg:py-6 rounded-full bg-gradient-to-r from-black to-[#01CFF7] hover:scale-105 active:scale-95 transition-all duration-300 shadow-[0_4px_14px_rgba(0,255,255,0.3)]"
            style="font-family: Arial, sans-serif;">
            Enter CA code
          </button>

          <!-- Button to get CA code -->
          <button
            on:click={getCode}
            class="font-sans w-[220px] md:w-[180px] lg:w-[250px] text-lg md:text-xl lg:text-2xl px-6 md:px-6 lg:px-10 py-5 md:py-4 lg:py-6 rounded-full bg-gradient-to-r from-black to-[#01CFF7] hover:scale-105 active:scale-95 transition-all duration-300 shadow-[0_4px_14px_rgba(0,255,255,0.3)]"
            style="font-family: Arial, sans-serif;">
            Get CA code
          </button>
        </div>
      </div>

      <!-- Right Section: Image (hidden on small screens) -->
      <div class="w-[80%] md:max-w-[40%] hidden md:block">
        <img src="src/lib/assets/images/hands.png" alt="HandsIMG" class="w-full" />
      </div>
    </div>
  </main>

  <!-- Footer at the bottom -->
  <Footer />
</div>
