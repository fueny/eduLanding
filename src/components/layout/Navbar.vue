<template>
  <header class="sticky top-0 z-50 bg-white/95 backdrop-blur-sm shadow-sm">
    <nav class="container py-4">
      <div class="flex items-center justify-between">
        <!-- Logo -->
        <div class="flex items-center">
          <a href="/" class="flex items-center">
            <i class="bi bi-book-half text-primary-600 text-3xl mr-2"></i>
            <span class="text-xl font-bold gradient-text">EduVista</span>
          </a>
        </div>

        <!-- Desktop Navigation -->
        <div class="hidden md:flex items-center space-x-8">
          <a href="#courses" class="text-secondary-700 hover:text-primary-600 font-medium transition-colors">Courses</a>
          <a href="#features" class="text-secondary-700 hover:text-primary-600 font-medium transition-colors">Features</a>
          <a href="#testimonials" class="text-secondary-700 hover:text-primary-600 font-medium transition-colors">Testimonials</a>
          <a href="#pricing" class="text-secondary-700 hover:text-primary-600 font-medium transition-colors">Pricing</a>
          <a href="#contact" class="text-secondary-700 hover:text-primary-600 font-medium transition-colors">Contact</a>
        </div>

        <!-- CTA Buttons -->
        <div class="hidden md:flex items-center space-x-4">
          <a href="#" class="text-primary-600 hover:text-primary-700 font-medium">Log in</a>
          <a href="#" class="btn btn-primary">Get Started</a>
        </div>

        <!-- Mobile menu button -->
        <div class="md:hidden flex items-center">
          <button @click="isMenuOpen = !isMenuOpen" class="text-secondary-500 hover:text-primary-600 focus:outline-none">
            <i class="bi" :class="isMenuOpen ? 'bi-x-lg' : 'bi-list'"></i>
          </button>
        </div>
      </div>

      <!-- Mobile Navigation -->
      <div v-if="isMenuOpen" class="md:hidden mt-4 pb-4">
        <div class="flex flex-col space-y-4">
          <a href="#courses" @click="isMenuOpen = false" class="text-secondary-700 hover:text-primary-600 font-medium transition-colors">Courses</a>
          <a href="#features" @click="isMenuOpen = false" class="text-secondary-700 hover:text-primary-600 font-medium transition-colors">Features</a>
          <a href="#testimonials" @click="isMenuOpen = false" class="text-secondary-700 hover:text-primary-600 font-medium transition-colors">Testimonials</a>
          <a href="#pricing" @click="isMenuOpen = false" class="text-secondary-700 hover:text-primary-600 font-medium transition-colors">Pricing</a>
          <a href="#contact" @click="isMenuOpen = false" class="text-secondary-700 hover:text-primary-600 font-medium transition-colors">Contact</a>
          <div class="pt-4 flex flex-col space-y-4">
            <a href="#" class="text-primary-600 hover:text-primary-700 font-medium">Log in</a>
            <a href="#" class="btn btn-primary">Get Started</a>
          </div>
        </div>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'Navbar',
  data() {
    return {
      isMenuOpen: false
    }
  }
}
</script>
