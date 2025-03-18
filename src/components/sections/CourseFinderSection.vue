<template>
  <section id="course-finder" class="section blue-gradient-bg text-white">
    <div class="container">
      <!-- Section Header -->
      <div class="text-center max-w-3xl mx-auto mb-16" data-aos="fade-up">
        <h2 class="text-3xl md:text-4xl font-bold mb-4 text-white">
          Find Your Perfect Learning Path
        </h2>
        <p class="text-lg text-primary-100">
          Answer a few questions to discover personalized course recommendations tailored to your goals and interests.
        </p>
      </div>
      
      <!-- Course Finder -->
      <div class="bg-white rounded-xl shadow-xl overflow-hidden" data-aos="fade-up">
        <div class="grid grid-cols-1 lg:grid-cols-3">
          <!-- Finder Form -->
          <div class="p-8 lg:col-span-1 bg-primary-800 text-white">
            <h3 class="text-2xl font-bold mb-6">Course Finder</h3>
            
            <form @submit.prevent="findCourses" class="space-y-6">
              <!-- Learning Goal -->
              <div>
                <label class="block text-sm font-medium mb-2">What is your learning goal?</label>
                <select 
                  v-model="formData.goal" 
                  class="w-full px-4 py-3 rounded-lg bg-primary-700 border border-primary-600 text-white placeholder-primary-300 focus:outline-none focus:ring-2 focus:ring-primary-400"
                >
                  <option value="" disabled>Select your goal</option>
                  <option value="career">Career Advancement</option>
                  <option value="skills">Learn New Skills</option>
                  <option value="degree">Earn a Degree</option>
                  <option value="hobby">Personal Interest</option>
                </select>
              </div>
              
              <!-- Field of Interest -->
              <div>
                <label class="block text-sm font-medium mb-2">Field of Interest</label>
                <select 
                  v-model="formData.field" 
                  class="w-full px-4 py-3 rounded-lg bg-primary-700 border border-primary-600 text-white placeholder-primary-300 focus:outline-none focus:ring-2 focus:ring-primary-400"
                >
                  <option value="" disabled>Select a field</option>
                  <option value="technology">Technology</option>
                  <option value="business">Business</option>
                  <option value="design">Design</option>
                  <option value="marketing">Marketing</option>
                  <option value="science">Science</option>
                  <option value="humanities">Humanities</option>
                </select>
              </div>
              
              <!-- Experience Level -->
              <div>
                <label class="block text-sm font-medium mb-2">Experience Level</label>
                <div class="space-y-2">
                  <label class="flex items-center">
                    <input type="radio" v-model="formData.level" value="beginner" class="text-primary-500 focus:ring-primary-400">
                    <span class="ml-2">Beginner</span>
                  </label>
                  <label class="flex items-center">
                    <input type="radio" v-model="formData.level" value="intermediate" class="text-primary-500 focus:ring-primary-400">
                    <span class="ml-2">Intermediate</span>
                  </label>
                  <label class="flex items-center">
                    <input type="radio" v-model="formData.level" value="advanced" class="text-primary-500 focus:ring-primary-400">
                    <span class="ml-2">Advanced</span>
                  </label>
                </div>
              </div>
              
              <!-- Time Commitment -->
              <div>
                <label class="block text-sm font-medium mb-2">Time Commitment</label>
                <select 
                  v-model="formData.time" 
                  class="w-full px-4 py-3 rounded-lg bg-primary-700 border border-primary-600 text-white placeholder-primary-300 focus:outline-none focus:ring-2 focus:ring-primary-400"
                >
                  <option value="" disabled>Select time commitment</option>
                  <option value="1-3">1-3 hours/week</option>
                  <option value="4-6">4-6 hours/week</option>
                  <option value="7-10">7-10 hours/week</option>
                  <option value="10+">10+ hours/week</option>
                </select>
              </div>
              
              <button type="submit" class="w-full btn bg-white text-primary-700 hover:bg-primary-50">
                Find My Courses
                <i class="bi bi-search ml-2"></i>
              </button>
            </form>
          </div>
          
          <!-- Results -->
          <div class="p-8 lg:col-span-2 bg-white">
            <div v-if="!showResults">
              <div class="flex flex-col items-center justify-center h-full py-12">
                <img 
                  src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExNjM2OTI5MzY1NjQzMjk5MjQzNjQ3NjM4NjM5MzIzNjQ3MzgzODM4MyZlcD12MV9pbnRlcm5hbF9naWZzX2dpZklkJmN0PWc/JIX9t2j0ZTN9S/giphy.gif" 
                  alt="Course finder illustration" 
                  class="w-48 h-48 object-contain mb-6"
                >
                <h3 class="text-xl font-bold text-secondary-900 mb-2">Discover Your Learning Path</h3>
                <p class="text-secondary-600 text-center max-w-md">
                  Fill out the form to get personalized course recommendations based on your interests and goals.
                </p>
              </div>
            </div>
            
            <div v-else>
              <h3 class="text-xl font-bold text-secondary-900 mb-6">Recommended Learning Path</h3>
              
              <div class="space-y-6">
                <div v-for="(path, index) in learningPaths" :key="index" class="border border-primary-100 rounded-lg p-6 hover:shadow-md transition-shadow">
                  <h4 class="text-lg font-bold text-primary-700 mb-2">{{ path.title }}</h4>
                  <p class="text-secondary-600 mb-4">{{ path.description }}</p>
                  
                  <div class="flex flex-wrap gap-2 mb-4">
                    <span v-for="(tag, i) in path.tags" :key="i" class="text-xs bg-primary-50 text-primary-700 px-2 py-1 rounded-full">
                      {{ tag }}
                    </span>
                  </div>
                  
                  <div class="flex items-center justify-between">
                    <div class="flex items-center">
                      <i class="bi bi-clock text-secondary-500 mr-1"></i>
                      <span class="text-sm text-secondary-500">{{ path.duration }}</span>
                    </div>
                    <a href="#" class="text-primary-600 hover:text-primary-700 font-medium text-sm">
                      View Details
                      <i class="bi bi-arrow-right ml-1"></i>
                    </a>
                  </div>
                </div>
              </div>
              
              <div class="mt-8 text-center">
                <button @click="showResults = false" class="text-primary-600 hover:text-primary-700 font-medium">
                  <i class="bi bi-arrow-left mr-1"></i>
                  Start Over
                </button>
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
  name: 'CourseFinderSection',
  data() {
    return {
      showResults: false,
      formData: {
        goal: '',
        field: '',
        level: 'beginner',
        time: ''
      },
      learningPaths: [
        {
          title: 'Web Development Career Path',
          description: 'A comprehensive program to become a professional web developer, covering front-end and back-end technologies.',
          tags: ['HTML/CSS', 'JavaScript', 'React', 'Node.js', 'Career-focused'],
          duration: '6 months'
        },
        {
          title: 'UX/UI Design Fundamentals',
          description: 'Master the principles of user experience and interface design to create intuitive digital products.',
          tags: ['Design Thinking', 'Wireframing', 'Prototyping', 'User Research'],
          duration: '3 months'
        },
        {
          title: 'Data Science Essentials',
          description: 'Learn the core concepts of data analysis, visualization, and machine learning with Python.',
          tags: ['Python', 'Data Analysis', 'Machine Learning', 'Statistics'],
          duration: '4 months'
        }
      ]
    }
  },
  methods: {
    findCourses() {
      // In a real application, this would make an API call to get personalized recommendations
      // For now, we'll just show the static results
      this.showResults = true;
    }
  }
}
</script>
