<template>
  <section class="section bg-white">
    <div class="container">
      <div class="relative overflow-hidden rounded-xl blue-gradient-bg shadow-xl" data-aos="fade-up">
        <!-- Background Elements -->
        <div class="absolute top-0 right-0 w-64 h-64 bg-white/5 rounded-full -translate-y-1/2 translate-x-1/4"></div>
        <div class="absolute bottom-0 left-0 w-64 h-64 bg-white/5 rounded-full translate-y-1/2 -translate-x-1/4"></div>
        
        <div class="relative z-10 py-16 px-8 md:py-20 md:px-12 text-center">
          <h2 class="text-3xl md:text-4xl font-bold mb-6 text-white">
            Ready to Start Your Learning Journey?
          </h2>
          <p class="text-lg text-primary-100 mb-8 max-w-2xl mx-auto">
            Join thousands of students who are already transforming their careers and lives through our expert-led courses.
          </p>
          
          <div class="flex flex-col sm:flex-row justify-center gap-4">
            <a href="#courses" class="btn bg-white text-primary-700 hover:bg-primary-50">
              Explore Courses
              <i class="bi bi-arrow-right ml-2"></i>
            </a>
            <a href="#" class="btn bg-primary-700 text-white hover:bg-primary-800 border border-primary-600">
              Sign Up for Free
              <i class="bi bi-person-plus ml-2"></i>
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'CtaSection'
}
</script>
