<template>
  <section class="relative overflow-hidden">
    <!-- Background Elements -->
    <div class="absolute inset-0 bg-gradient-to-b from-primary-50 to-white z-0"></div>
    <div class="absolute top-0 right-0 w-1/3 h-1/3 bg-gradient-radial from-primary-200/50 to-transparent opacity-70"></div>
    <div class="absolute bottom-0 left-0 w-1/4 h-1/4 bg-gradient-radial from-primary-200/50 to-transparent opacity-70"></div>
    
    <div class="container relative z-10 pt-16 pb-24 md:pt-24 md:pb-32">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
        <!-- Content -->
        <div data-aos="fade-right">
          <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold mb-6 leading-tight">
            Unlock Your <span class="gradient-text">Learning Potential</span> With Expert-Led Courses
          </h1>
          <p class="text-lg md:text-xl text-secondary-600 mb-8 max-w-2xl">
            Discover a world of knowledge with our comprehensive learning platform. 
            Expert instructors, interactive content, and personalized learning paths to help you achieve your goals.
          </p>
          
          <div class="flex flex-col sm:flex-row gap-4 mb-12">
            <a href="#courses" class="btn btn-primary">
              Explore Courses
              <i class="bi bi-arrow-right ml-2"></i>
            </a>
            <a href="#course-finder" class="btn btn-secondary">
              <i class="bi bi-search mr-2"></i>
              Find Your Path
            </a>
          </div>
          
          <div class="flex items-center">
            <div class="flex -space-x-2 mr-4">
              <img src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="User" class="w-10 h-10 rounded-full border-2 border-white" crossorigin="anonymous">
              <img src="https://images.unsplash.com/photo-1535713875002-d1d0cf377fde?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="User" class="w-10 h-10 rounded-full border-2 border-white" crossorigin="anonymous">
              <img src="https://images.unsplash.com/photo-1580489944761-15a19d654956?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="User" class="w-10 h-10 rounded-full border-2 border-white" crossorigin="anonymous">
            </div>
            <div>
              <div class="flex items-center mb-1">
                <div class="flex">
                  <i class="bi bi-star-fill text-yellow-400"></i>
                  <i class="bi bi-star-fill text-yellow-400"></i>
                  <i class="bi bi-star-fill text-yellow-400"></i>
                  <i class="bi bi-star-fill text-yellow-400"></i>
                  <i class="bi bi-star-half text-yellow-400"></i>
                </div>
                <span class="ml-2 text-secondary-700 font-medium">4.8/5</span>
              </div>
              <p class="text-sm text-secondary-500">Trusted by over <span class="font-semibold">50,000+</span> students</p>
            </div>
          </div>
        </div>
        
        <!-- Hero Image -->
        <div class="relative" data-aos="fade-left">
          <div class="absolute -inset-4 bg-gradient-to-r from-primary-200/30 to-primary-400/30 rounded-full blur-3xl opacity-70"></div>
          <div class="relative">
            <img 
              src="https://images.unsplash.com/photo-1523240795612-9a054b0db644?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1740&q=80" 
              alt="Students learning online" 
              class="rounded-xl shadow-custom w-full object-cover"
              crossorigin="anonymous"
            >
            
            <!-- Floating Elements -->
            <div class="absolute -top-6 -left-6 bg-white rounded-lg shadow-lg p-4 flex items-center animate-bounce-slow">
              <div class="bg-primary-100 rounded-full p-2 mr-3">
                <i class="bi bi-lightning-charge-fill text-primary-600 text-xl"></i>
              </div>
              <div>
                <p class="font-semibold text-secondary-900">Live Classes</p>
                <p class="text-sm text-secondary-500">Interactive Learning</p>
              </div>
            </div>
            
            <div class="absolute -bottom-6 -right-6 bg-white rounded-lg shadow-lg p-4 flex items-center animate-pulse-slow">
              <div class="bg-primary-100 rounded-full p-2 mr-3">
                <i class="bi bi-trophy-fill text-primary-600 text-xl"></i>
              </div>
              <div>
                <p class="font-semibold text-secondary-900">Certification</p>
                <p class="text-sm text-secondary-500">Industry Recognized</p>
              </div>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Trusted By -->
      <div class="mt-20" data-aos="fade-up">
        <p class="text-center text-secondary-500 mb-8">Trusted by leading companies and institutions</p>
        <div class="flex flex-wrap justify-center items-center gap-8 md:gap-16">
          <div class="text-secondary-400 hover:text-secondary-600 transition-colors">
            <i class="bi bi-microsoft text-3xl"></i>
          </div>
          <div class="text-secondary-400 hover:text-secondary-600 transition-colors">
            <i class="bi bi-google text-3xl"></i>
          </div>
          <div class="text-secondary-400 hover:text-secondary-600 transition-colors">
            <i class="bi bi-apple text-3xl"></i>
          </div>
          <div class="text-secondary-400 hover:text-secondary-600 transition-colors">
            <i class="bi bi-amazon text-3xl"></i>
          </div>
          <div class="text-secondary-400 hover:text-secondary-600 transition-colors">
            <i class="bi bi-meta text-3xl"></i>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'HeroSection'
}
</script>

<style scoped>
.animate-bounce-slow {
  animation: bounce 5s infinite;
}

.animate-pulse-slow {
  animation: pulse 5s infinite;
}

@keyframes bounce {
  0%, 100% {
    transform: translateY(-5%);
    animation-timing-function: cubic-bezier(0.8, 0, 1, 1);
  }
  50% {
    transform: translateY(0);
    animation-timing-function: cubic-bezier(0, 0, 0.2, 1);
  }
}

@keyframes pulse {
  0%, 100% {
    opacity: 1;
  }
  50% {
    opacity: 0.8;
  }
}
</style>
