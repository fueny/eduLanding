<template>
  <section id="contact" class="section bg-white">
    <div class="container">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
        <!-- Contact Form -->
        <div data-aos="fade-right">
          <h2 class="text-3xl font-bold mb-6">
            Get in <span class="gradient-text">Touch</span>
          </h2>
          <p class="text-secondary-600 mb-8">
            Have questions about our courses or need help choosing the right learning path? Our education advisors are here to help.
          </p>
          
          <form @submit.prevent="submitForm" class="space-y-6">
            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
              <div>
                <label for="name" class="block text-sm font-medium text-secondary-700 mb-1">Full Name</label>
                <input 
                  type="text" 
                  id="name" 
                  v-model="formData.name" 
                  class="w-full px-4 py-3 rounded-lg border border-secondary-300 focus:outline-none focus:ring-2 focus:ring-primary-500 focus:border-primary-500"
                  placeholder="Your name"
                  required
                >
              </div>
              <div>
                <label for="email" class="block text-sm font-medium text-secondary-700 mb-1">Email Address</label>
                <input 
                  type="email" 
                  id="email" 
                  v-model="formData.email" 
                  class="w-full px-4 py-3 rounded-lg border border-secondary-300 focus:outline-none focus:ring-2 focus:ring-primary-500 focus:border-primary-500"
                  placeholder="your.email@example.com"
                  required
                >
              </div>
            </div>
            
            <div>
              <label for="subject" class="block text-sm font-medium text-secondary-700 mb-1">Subject</label>
              <input 
                type="text" 
                id="subject" 
                v-model="formData.subject" 
                class="w-full px-4 py-3 rounded-lg border border-secondary-300 focus:outline-none focus:ring-2 focus:ring-primary-500 focus:border-primary-500"
                placeholder="How can we help you?"
                required
              >
            </div>
            
            <div>
              <label for="message" class="block text-sm font-medium text-secondary-700 mb-1">Message</label>
              <textarea 
                id="message" 
                v-model="formData.message" 
                rows="5" 
                class="w-full px-4 py-3 rounded-lg border border-secondary-300 focus:outline-none focus:ring-2 focus:ring-primary-500 focus:border-primary-500"
                placeholder="Your message..."
                required
              ></textarea>
            </div>
            
            <button type="submit" class="btn btn-primary">
              Send Message
              <i class="bi bi-send ml-2"></i>
            </button>
          </form>
        </div>
        
        <!-- Contact Info -->
        <div data-aos="fade-left">
          <div class="bg-primary-50 rounded-xl p-8">
            <h3 class="text-xl font-bold mb-6">Contact Information</h3>
            
            <div class="space-y-6">
              <div class="flex items-start">
                <div class="bg-primary-100 rounded-full p-3 mr-4">
                  <i class="bi bi-envelope-fill text-primary-600"></i>
                </div>
                <div>
                  <p class="font-medium text-secondary-900 mb-1">Email Us</p>
                  <a href="mailto:info@eduvista.com" class="text-primary-600 hover:text-primary-700">info@eduvista.com</a>
                </div>
              </div>
              
              <div class="flex items-start">
                <div class="bg-primary-100 rounded-full p-3 mr-4">
                  <i class="bi bi-telephone-fill text-primary-600"></i>
                </div>
                <div>
                  <p class="font-medium text-secondary-900 mb-1">Call Us</p>
                  <a href="tel:+18001234567" class="text-primary-600 hover:text-primary-700">+1 (800) 123-4567</a>
                </div>
              </div>
              
              <div class="flex items-start">
                <div class="bg-primary-100 rounded-full p-3 mr-4">
                  <i class="bi bi-geo-alt-fill text-primary-600"></i>
                </div>
                <div>
                  <p class="font-medium text-secondary-900 mb-1">Visit Us</p>
                  <p class="text-secondary-600">
                    123 Education Street<br>
                    San Francisco, CA 94103<br>
                    United States
                  </p>
                </div>
              </div>
              
              <div class="flex items-start">
                <div class="bg-primary-100 rounded-full p-3 mr-4">
                  <i class="bi bi-clock-fill text-primary-600"></i>
                </div>
                <div>
                  <p class="font-medium text-secondary-900 mb-1">Hours</p>
                  <p class="text-secondary-600">
                    Monday - Friday: 9:00 AM - 6:00 PM<br>
                    Saturday: 10:00 AM - 4:00 PM<br>
                    Sunday: Closed
                  </p>
                </div>
              </div>
            </div>
            
            <div class="mt-8">
              <h4 class="font-medium text-secondary-900 mb-3">Connect With Us</h4>
              <div class="flex space-x-4">
                <a href="#" class="bg-white w-10 h-10 rounded-full flex items-center justify-center shadow-sm hover:shadow-md transition-shadow">
                  <i class="bi bi-facebook text-primary-600"></i>
                </a>
                <a href="#" class="bg-white w-10 h-10 rounded-full flex items-center justify-center shadow-sm hover:shadow-md transition-shadow">
                  <i class="bi bi-twitter text-primary-600"></i>
                </a>
                <a href="#" class="bg-white w-10 h-10 rounded-full flex items-center justify-center shadow-sm hover:shadow-md transition-shadow">
                  <i class="bi bi-instagram text-primary-600"></i>
                </a>
                <a href="#" class="bg-white w-10 h-10 rounded-full flex items-center justify-center shadow-sm hover:shadow-md transition-shadow">
                  <i class="bi bi-linkedin text-primary-600"></i>
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ContactSection',
  data() {
    return {
      formData: {
        name: '',
        email: '',
        subject: '',
        message: ''
      }
    }
  },
  methods: {
    submitForm() {
      // In a real application, this would send the form data to a server
      alert('Thank you for your message! We will get back to you soon.');
      this.formData = {
        name: '',
        email: '',
        subject: '',
        message: ''
      };
    }
  }
}
</script>
