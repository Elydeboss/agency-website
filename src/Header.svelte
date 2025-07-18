<script>
  import { onMount } from 'svelte';
  import { fade, fly } from 'svelte/transition';
  import Image from '../src/img/business-team_.jpg';
  import Global from '../src/img/photo-rebrand.webp';
  import Digital from '../src/img/digital-tranform.webp'
  import Product from '../src/img/product-launch-.webp';
  import Social from '../src/img/strategy.jpg';
  import Team from '../src/img/team-african.webp';

  // data for the services, projects, testimonials, and team members
  const services = [
    { 
      title: 'Brand Strategy', 
      description: 'We develop comprehensive brand strategies that position your business for success in competitive markets.',
      icon: 'M9.813 15.904L9 18.75l-.813-2.846a4.5 4.5 0 00-3.09-3.09L2.25 12l2.846-.813a4.5 4.5 0 003.09-3.09L9 5.25l.813 2.846a4.5 4.5 0 003.09 3.09L15.75 12l-2.846.813a4.5 4.5 0 00-3.09 3.09zM18.259 8.715L18 9.75l-.259-1.035a3.375 3.375 0 00-2.455-2.456L14.25 6l1.036-.259a3.375 3.375 0 002.455-2.456L18 2.25l.259 1.035a3.375 3.375 0 002.456 2.456L21.75 6l-1.035.259a3.375 3.375 0 00-2.456 2.456zM16.894 20.567L16.5 21.75l-.394-1.183a2.25 2.25 0 00-1.423-1.423L13.5 18.75l1.183-.394a2.25 2.25 0 001.423-1.423l.394-1.183.394 1.183a2.25 2.25 0 001.423 1.423l1.183.394-1.183.394a2.25 2.25 0 00-1.423 1.423z'
    },
    { 
      title: 'Creative Design', 
      description: 'Our award-winning design team creates visually stunning assets that capture attention and communicate your message.',
      icon: 'M9.53 16.122a3 3 0 00-5.78 1.128 2.25 2.25 0 01-2.4 2.245 4.5 4.5 0 008.4-2.245c0-.399-.078-.78-.22-1.128zm0 0a15.998 15.998 0 003.388-1.62m-5.043-.025a15.994 15.994 0 011.622-3.395m3.42 3.42a15.995 15.995 0 004.764-4.648l3.876-5.814a1.151 1.151 0 00-1.597-1.597L14.146 6.32a15.996 15.996 0 00-4.649 4.763m3.42 3.42a6.776 6.776 0 00-3.42-3.42'
    },
    { 
      title: 'Digital Marketing', 
      description: 'We leverage the latest digital channels and technologies to reach your target audience and drive measurable results.',
      icon: 'M3.75 3v11.25A2.25 2.25 0 006 16.5h2.25M3.75 3h-1.5m1.5 0h16.5m0 0h1.5m-1.5 0v11.25A2.25 2.25 0 0118 16.5h-2.25m-7.5 0h7.5m-7.5 0l-1 3m8.5-3l1 3m0 0l.5 1.5m-.5-1.5h-9.5m0 0l-.5 1.5m.75-9l3-3 2.148 2.148A12.061 12.061 0 0116.5 7.605'
    },
    { 
      title: 'Media Planning', 
      description: 'Our strategic media planning ensures your message reaches the right audience at the right time across all channels.',
      icon: 'M3.75 3.75v4.5m0-4.5h4.5m-4.5 0L9 9M3.75 20.25v-4.5m0 4.5h4.5m-4.5 0L9 15M20.25 3.75h-4.5m4.5 0v4.5m0-4.5L15 9m5.25 11.25h-4.5m4.5 0v-4.5m0 4.5L15 15'
    }
  ];
  
  const projects = [
    { 
      title: 'Global Rebrand', 
      client: 'TechCorp', 
      image: Global,
      category: 'Branding'
    },
    { 
      title: 'Product Launch Campaign', 
      client: 'Innovate Inc', 
      image: Product,
      category: 'Marketing'
    },
    { 
      title: 'Digital Transformation', 
      client: 'Legacy Enterprises', 
      image:  Digital,
      category: 'Digital'
    },
    { 
      title: 'Social Media Strategy', 
      client: 'Fashion Forward', 
      image: Social,
      category: 'Social'
    }
  ];
  
  const testimonials = [
    {
      quote: "Working with Spark Solutions transformed our brand. Their strategic approach and creative execution exceeded our expectations.",
      author: "Sarah Johnson",
      position: "CMO, TechCorp",
      image: "/placeholder.svg?height=100&width=100"
    },
    {
      quote: "The team's attention to detail and innovative thinking helped us stand out in a crowded market. Highly recommended!",
      author: "Michael Chen",
      position: "CEO, Innovate Inc",
      image: "/placeholder.svg?height=100&width=100"
    },
    {
      quote: "Our digital presence has never been stronger. The ROI on our campaigns has been exceptional.",
      author: "Jessica Williams",
      position: "Marketing Director, Legacy Enterprises",
      image: "/placeholder.svg?height=100&width=100"
    }
  ];
  
  let currentTestimonial = 0;
  let isMenuOpen = false;
  
  function nextTestimonial() {
    currentTestimonial = (currentTestimonial + 1) % testimonials.length;
  }
  
  function prevTestimonial() {
    currentTestimonial = (currentTestimonial - 1 + testimonials.length) % testimonials.length;
  }
  
  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }
  
  // Animation for the hero section
  let isVisible = false;
  
  onMount(() => {
    isVisible = true;
  });
</script>

<div class="font-sans text-gray-900">
  <!-- Navigation -->
  <nav class="bg-white shadow-md fixed top-0 left-0 right-0 py-4 mb-8 w-full z-10">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between h-16">
        <div class="flex items-center">
          <div class="flex-shrink-0 flex items-center">
            <span class="text-2xl font-bold text-primary">TECH</span>
            <span class="ml-1 text-sm text-gray-500">CAVE</span>
          </div>
        </div>
        
        <!-- Desktop menu -->
        <div class="hidden md:flex items-center space-x-8 text-bold">
          <a href="#home" class="text-gray-600 hover:text-primary transition-colors">Home</a>
          <a href="#services" class="text-gray-600 hover:text-primary transition-colors">Services</a>
          <a href="#work" class="text-gray-600 hover:text-primary transition-colors">Work</a>
          <a href="#about" class="text-gray-600 hover:text-primary transition-colors">About</a>
          <a href="#testimonials" class="text-gray-600 hover:text-primary transition-colors">Testimonials</a>
          <a href="#contact" class="bg-primary text-white px-4 py-2 rounded-md hover:bg-primary-dark transition-colors">Contact Us</a>
        </div>
        
        <!-- Mobile menu button -->
        <div class="md:hidden flex items-center">
          <button on:click={toggleMenu} class="text-gray-600 hover:text-primary focus:outline-none">
            <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              {#if isMenuOpen}
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
              {:else}
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
              {/if}
            </svg>
          </button>
        </div>
      </div>
    </div>
    
    <!-- Mobile menu -->
    {#if isMenuOpen}
      <div class="md:hidden bg-white shadow-lg text-bold">
        <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
          <a href="#services" class="block px-3 py-2 text-gray-600 hover:text-primary">Services</a>
          <a href="#work" class="block px-3 py-2 text-gray-600 hover:text-primary">Work</a>
          <a href="#about" class="block px-3 py-2 text-gray-600 hover:text-primary">About</a>
          <a href="#testimonials" class="block px-3 py-2 text-gray-600 hover:text-primary">Testimonials</a>
          <a href="#contact" class="block px-3 py-2 bg-primary text-white rounded-md">Contact Us</a>
        </div>
      </div>
    {/if}
  </nav>
</div>

  <!-- Hero Section -->
  <section class="pt-24 pb-16 md:pt-32 md:pb-24 bg-gradient-to-r from-gray-50 to-gray-100 mt-12" id="home">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-center">
        <div class="transition-all duration-1000 transform {isVisible ? 'translate-x-0 opacity-100' : '-translate-x-10 opacity-0'}">
          <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold leading-tight text-gray-900 mb-4">
            We craft <span class="text-primary">powerful</span> brand experiences
          </h1>
          <p class="text-xl text-gray-600 mb-8">
            Strategic thinking. Creative solutions. Measurable results.
          </p>
          <div class="flex flex-col sm:flex-row gap-4">
            <a href="#contact" class="bg-primary text-white px-6 py-3 rounded-md text-lg font-medium hover:bg-primary-dark transition-colors inline-block text-center">
              Get Started
            </a>
            <a href="#work" class="border border-gray-300 text-gray-700 px-6 py-3 rounded-md text-lg font-medium hover:bg-gray-50 transition-colors inline-block text-center">
              View Our Work
            </a>
          </div>
        </div>
        <div class="transition-all duration-1000 delay-300 transform mt-12 {isVisible ? 'translate-x-0 opacity-100' : 'translate-x-10 opacity-0'}">
          <img src={Image} alt="Creative advertising concept" class="rounded-lg shadow-xl">
        </div>
      </div>
    </div>
  </section>

  <!-- Services Section -->
  <section id="services" class="py-16 md:py-24 bg-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-4">Our Services</h2>
        <p class="text-xl text-gray-600 max-w-3xl mx-auto">
          We offer comprehensive advertising and marketing solutions tailored to your unique business needs.
        </p>
      </div>
      
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
        {#each services as service, i}
          <div class="bg-gray-50 rounded-lg p-8 shadow-sm hover:shadow-md transition-shadow">
            <div class="w-12 h-12 bg-primary/10 rounded-lg flex items-center justify-center mb-6">
              <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 text-primary">
                <path stroke-linecap="round" stroke-linejoin="round" d={service.icon} />
              </svg>
            </div>
            <h3 class="text-xl font-bold text-gray-900 mb-3">{service.title}</h3>
            <p class="text-gray-600">{service.description}</p>
          </div>
        {/each}
      </div>
    </div>
  </section>

  <!-- Work Section -->
  <section id="work" class="py-16 md:py-24 bg-gray-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-4">Our Work</h2>
        <p class="text-xl text-gray-600 max-w-3xl mx-auto">
          Explore our portfolio of successful campaigns and creative solutions.
        </p>
      </div>
      
      <div class="grid grid-cols-3 md:grid-cols-2 gap-8">
        {#each projects as project, i}
          <div class="group relative overflow-hidden rounded-lg shadow-md hover:shadow-xl transition-shadow">
            <img src={project.image || "/placeholder.svg"} alt={project.title} class="w-full h-80 object-cover transition-transform duration-500 group-hover:scale-105">
            <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent opacity-90 transition-opacity group-hover:opacity-100"></div>
            <div class="absolute bottom-0 left-0 right-0 p-6 text-white">
              <span class="text-sm font-medium text-primary-light bg-black/30 px-3 py-1 rounded-full">{project.category}</span>
              <h3 class="text-2xl font-bold mt-2">{project.title}</h3>
              <p class="text-gray-200">{project.client}</p>
            </div>
          </div>
        {/each}
      </div>
      
      
    </div>
  </section>

  <!-- About Section -->
  <section id="about" class="py-16 md:py-24 bg-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
        <div>
          <img src={Team} alt="Our team at work" class="rounded-lg shadow-lg">
        </div>
        <div>
          <h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-6">About Sophnex Solutions</h2>
          <p class="text-lg text-gray-600 mb-6">
            Founded in 2010, Sophnex Solutions has grown from a small creative shop to a full-service advertising Solutions with a global reach. Our mission is to create meaningful connections between brands and their audiences through strategic thinking and creative excellence.
          </p>
          <p class="text-lg text-gray-600 mb-8">
            With a team of over 50 specialists across strategy, creative, digital, and media, we bring diverse perspectives and expertise to every project. Our collaborative approach ensures that we deliver integrated solutions that drive real business results.
          </p>
          
          <div class="grid grid-cols-2 gap-6 mb-8">
            <div>
              <div class="text-4xl font-bold text-primary mb-2">150+</div>
              <div class="text-gray-600">Clients Worldwide</div>
            </div>
            <div>
              <div class="text-4xl font-bold text-primary mb-2">200+</div>
              <div class="text-gray-600">Projects Completed</div>
            </div>
            <div>
              <div class="text-4xl font-bold text-primary mb-2">30+</div>
              <div class="text-gray-600">Industry Awards</div>
            </div>
            <div>
              <div class="text-4xl font-bold text-primary mb-2">12+</div>
              <div class="text-gray-600">Years of Excellence</div>
            </div>
          </div>
          
          <a href="#contact" class="inline-block bg-primary text-white px-6 py-3 rounded-md text-lg font-medium hover:bg-primary-dark transition-colors">
            Join Our Team
          </a>
        </div>
      </div>
    </div>
  </section>

<!--ads marketing section-->
<section class="py-8 bg-white-700 text-center text-white">
  <div class="container mx-auto px-6">
    <h4 class="text-2xl font-semibold mb-4 text-black" in:fly={{ x: -20, duration: 500 }}>
      Learn the Cost of your <span class="font-bold text-black">Marketing Campaign</span> Right Now!
    </h4>
    <a href="/" class="px-6 py-3 bg-white text-blue-600 font-semibold rounded-lg shadow-md hover:bg-gray-200 transition duration-300" in:fly={{ x: 20, duration: 500 }}>
      View all pricing
    </a>
  </div>
</section>

<section id="our-team" class="py-16 text-center">
  <div class="container mx-auto px-6">
    <h3 class="text-3xl font-semibold text-gray-800 mb-8" in:fade={{ duration: 500 }}>
      Who We Are
    </h3>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-12">
      {#each [
        { name: 'Alex', position: 'Lead Of Creative, SophNex', img: '' },
        { name: 'kelvin', position: 'Head Of Operations, SophNex', img: '' },
        { name: 'John pierce', position: 'CEO, Founder, SophNex', img: '' }
      ] as member, i}
        <div class="text-center" in:fly={{ x: -20 * (i + 1), duration: 500, delay: 100 * i }}>
          <img src={member.img} alt={member.name} class="rounded-lg shadow-md w-full h-72 object-cover mb-4" />
          <h4 class="text-xl font-semibold text-gray-800">{member.name}</h4>
          <p class="text-gray-600">{member.position}</p>
        </div>
      {/each}
    </div>
    <div class="mt-8">
      <a href="/" class="px-6 py-3 bg-blue-600 text-white font-semibold rounded-lg shadow-md hover:bg-blue-700 transition duration-300" in:fly={{ y: 20, duration: 500 }}>
        View all Team
      </a>
    </div>
  </div>
</section>




  <!-- Testimonials Section -->
  <section id="testimonials" class="py-16 md:py-24 bg-gray-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-4">What Our Clients Say</h2>
        <p class="text-xl text-gray-600 max-w-3xl mx-auto">
          Don't just take our word for it. Here's what our clients have to say about working with us.
        </p>
      </div>
      
      <div class="relative bg-white rounded-xl shadow-lg p-8 md:p-12 max-w-4xl mx-auto">
        <div class="absolute top-0 left-0 transform -translate-x-4 -translate-y-4">
          <svg width="40" height="40" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M12.5 20H7.5C6.83696 20 6.20107 19.7366 5.73223 19.2678C5.26339 18.7989 5 18.163 5 17.5V12.5C5 11.837 5.26339 11.2011 5.73223 10.7322C6.20107 10.2634 6.83696 10 7.5 10H12.5C13.163 10 13.7989 10.2634 14.2678 10.7322C14.7366 11.2011 15 11.837 15 12.5V27.5" stroke="#6366F1" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            <path d="M32.5 20H27.5C26.837 20 26.2011 19.7366 25.7322 19.2678C25.2634 18.7989 25 18.163 25 17.5V12.5C25 11.837 25.2634 11.2011 25.7322 10.7322C26.2011 10.2634 26.837 10 27.5 10H32.5C33.163 10 33.7989 10.2634 34.2678 10.7322C34.7366 11.2011 35 11.837 35 12.5V27.5" stroke="#6366F1" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </div>
        
        <div class="pt-6">
          <p class="text-xl md:text-2xl text-gray-700 italic mb-8">
            {testimonials[currentTestimonial].quote}
          </p>
          
          <div class="flex items-center">
            <img src={testimonials[currentTestimonial].image || "/placeholder.svg"} alt={testimonials[currentTestimonial].author} class="w-14 h-14 rounded-full object-cover mr-4">
            <div>
              <div class="font-bold text-gray-900">{testimonials[currentTestimonial].author}</div>
              <div class="text-gray-600">{testimonials[currentTestimonial].position}</div>
            </div>
          </div>
        </div>
        
        <div class="absolute bottom-6 right-6 flex space-x-2">
          <button on:click={prevTestimonial} class="p-2 rounded-full bg-gray-100 hover:bg-gray-200 transition-colors">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-gray-600" viewBox="0 0 20 20" fill="currentColor">
              <path fill-rule="evenodd" d="M12.707 5.293a1 1 0 010 1.414L9.414 10l3.293 3.293a1 1 0 01-1.414 1.414l-4-4a1 1 0 010-1.414l4-4a1 1 0 011.414 0z" clip-rule="evenodd" />
            </svg>
          </button>
          <button on:click={nextTestimonial} class="p-2 rounded-full bg-gray-100 hover:bg-gray-200 transition-colors">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-gray-600" viewBox="0 0 20 20" fill="currentColor">
              <path fill-rule="evenodd" d="M7.293 14.707a1 1 0 010-1.414L10.586 10 7.293 6.707a1 1 0 011.414-1.414l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414 0z" clip-rule="evenodd" />
            </svg>
          </button>
        </div>
      </div>
    </div>
  </section>
