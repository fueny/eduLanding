<template>
  <footer class="bg-secondary-900 text-white">
    <div class="container py-12 md:py-16">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-5 gap-8">
        <!-- Brand -->
        <div class="lg:col-span-2">
          <div class="flex items-center mb-4">
            <i class="bi bi-book-half text-primary-400 text-3xl mr-2"></i>
            <span class="text-xl font-bold text-white">EduVista</span>
          </div>
          <p class="text-secondary-300 mb-6">
            Empowering learners worldwide with cutting-edge educational content and personalized learning experiences.
          </p>
          <div class="flex space-x-4">
            <a href="#" class="text-secondary-300 hover:text-white transition-colors">
              <i class="bi bi-facebook text-xl"></i>
            </a>
            <a href="#" class="text-secondary-300 hover:text-white transition-colors">
              <i class="bi bi-twitter text-xl"></i>
            </a>
            <a href="#" class="text-secondary-300 hover:text-white transition-colors">
              <i class="bi bi-instagram text-xl"></i>
            </a>
            <a href="#" class="text-secondary-300 hover:text-white transition-colors">
              <i class="bi bi-linkedin text-xl"></i>
            </a>
          </div>
        </div>

        <!-- Quick Links -->
        <div>
          <h3 class="text-lg font-semibold mb-4 text-white">Quick Links</h3>
          <ul class="space-y-3">
            <li><a href="#" class="text-secondary-300 hover:text-white transition-colors">About Us</a></li>
            <li><a href="#" class="text-secondary-300 hover:text-white transition-colors">Courses</a></li>
            <li><a href="#" class="text-secondary-300 hover:text-white transition-colors">Instructors</a></li>
            <li><a href="#" class="text-secondary-300 hover:text-white transition-colors">Events</a></li>
            <li><a href="#" class="text-secondary-300 hover:text-white transition-colors">Blog</a></li>
          </ul>
        </div>

        <!-- Support -->
        <div>
          <h3 class="text-lg font-semibold mb-4 text-white">Support</h3>
          <ul class="space-y-3">
            <li><a href="#" class="text-secondary-300 hover:text-white transition-colors">Help Center</a></li>
            <li><a href="#" class="text-secondary-300 hover:text-white transition-colors">FAQs</a></li>
            <li><a href="#" class="text-secondary-300 hover:text-white transition-colors">Privacy Policy</a></li>
            <li><a href="#" class="text-secondary-300 hover:text-white transition-colors">Terms of Service</a></li>
            <li><a href="#" class="text-secondary-300 hover:text-white transition-colors">Contact Us</a></li>
          </ul>
        </div>

        <!-- Newsletter -->
        <div>
          <h3 class="text-lg font-semibold mb-4 text-white">Stay Updated</h3>
          <p class="text-secondary-300 mb-4">Subscribe to our newsletter for the latest updates.</p>
          <form @submit.prevent="subscribeNewsletter" class="space-y-3">
            <div>
              <input 
                type="email" 
                v-model="email" 
                placeholder="Your email address" 
                class="w-full px-4 py-2 rounded-md bg-secondary-800 border border-secondary-700 text-white placeholder-secondary-400 focus:outline-none focus:ring-2 focus:ring-primary-500"
                required
              />
            </div>
            <button type="submit" class="w-full btn btn-primary">
              Subscribe
            </button>
          </form>
        </div>
      </div>

      <div class="mt-12 pt-8 border-t border-secondary-800 flex flex-col md:flex-row justify-between items-center">
        <p class="text-secondary-400 text-sm mb-4 md:mb-0">
          &copy; {{ new Date().getFullYear() }} EduVista. All rights reserved.
        </p>
        <p class="text-secondary-400 text-sm">
          Designed by <span class="text-primary-400">WebSparks AI</span>
        </p>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
  data() {
    return {
      email: ''
    }
  },
  methods: {
    subscribeNewsletter() {
      // Handle newsletter subscription
      alert('Thank you for subscribing to our newsletter!');
      this.email = '';
    }
  }
}
</script>
