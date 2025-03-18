<template>
  <section id="courses" class="section bg-white">
    <div class="container">
      <!-- Section Header -->
      <div class="text-center max-w-3xl mx-auto mb-16" data-aos="fade-up">
        <h2 class="text-3xl md:text-4xl font-bold mb-4">
          Explore Our <span class="gradient-text">Featured Courses</span>
        </h2>
        <p class="text-lg text-secondary-600">
          Discover our most popular courses designed to help you master new skills and advance your career.
        </p>
      </div>
      
      <!-- Category Tabs -->
      <div class="flex flex-wrap justify-center gap-2 mb-12" data-aos="fade-up">
        <button 
          v-for="category in categories" 
          :key="category"
          @click="selectedCategory = category"
          :class="[
            'px-4 py-2 rounded-full text-sm font-medium transition-all',
            selectedCategory === category 
              ? 'bg-primary-600 text-white shadow-md' 
              : 'bg-primary-50 text-primary-700 hover:bg-primary-100'
          ]"
        >
          {{ category }}
        </button>
      </div>
      
      <!-- Courses Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <CourseCard 
          v-for="(course, index) in filteredCourses" 
          :key="course.id"
          :course="course"
          :delay="index * 100"
        />
      </div>
      
      <!-- View All Button -->
      <div class="text-center mt-12" data-aos="fade-up">
        <a href="#" class="btn btn-secondary">
          View All Courses
          <i class="bi bi-arrow-right ml-2"></i>
        </a>
      </div>
    </div>
  </section>
</template>

<script>
import CourseCard from '../ui/CourseCard.vue'

export default {
  name: 'CoursesSection',
  components: {
    CourseCard
  },
  data() {
    return {
      selectedCategory: 'All Courses',
      categories: ['All Courses', 'Technology', 'Business', 'Design', 'Marketing', 'Personal Development'],
      courses: [
        {
          id: 1,
          title: 'Complete Web Development Bootcamp',
          description: 'Learn HTML, CSS, JavaScript, React, Node.js and more to become a full-stack web developer.',
          instructor: 'Sarah Johnson',
          rating: 4.9,
          reviews: 1245,
          students: 15420,
          price: 89.99,
          originalPrice: 199.99,
          image: 'https://images.unsplash.com/photo-1498050108023-c5249f4df085?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1744&q=80',
          category: 'Technology',
          level: 'Beginner to Advanced',
          duration: '24 weeks'
        },
        {
          id: 2,
          title: 'Data Science & Machine Learning',
          description: 'Master data analysis, visualization, and machine learning algorithms with Python.',
          instructor: 'Michael Chen',
          rating: 4.8,
          reviews: 987,
          students: 12350,
          price: 94.99,
          originalPrice: 189.99,
          image: 'https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1740&q=80',
          category: 'Technology',
          level: 'Intermediate',
          duration: '16 weeks'
        },
        {
          id: 3,
          title: 'Digital Marketing Masterclass',
          description: 'Learn SEO, social media marketing, email campaigns, and content strategy.',
          instructor: 'Emma Rodriguez',
          rating: 4.7,
          reviews: 756,
          students: 9870,
          price: 79.99,
          originalPrice: 159.99,
          image: 'https://images.unsplash.com/photo-1432888498266-38ffec3eaf0a?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1774&q=80',
          category: 'Marketing',
          level: 'All Levels',
          duration: '12 weeks'
        },
        {
          id: 4,
          title: 'UX/UI Design Fundamentals',
          description: 'Master user experience design principles and create stunning user interfaces.',
          instructor: 'David Kim',
          rating: 4.9,
          reviews: 632,
          students: 7845,
          price: 84.99,
          originalPrice: 169.99,
          image: 'https://images.unsplash.com/photo-1561070791-2526d30994b5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80',
          category: 'Design',
          level: 'Beginner to Intermediate',
          duration: '10 weeks'
        },
        {
          id: 5,
          title: 'Business Leadership & Management',
          description: 'Develop essential leadership skills to effectively manage teams and drive business growth.',
          instructor: 'Robert Williams',
          rating: 4.8,
          reviews: 542,
          students: 6320,
          price: 99.99,
          originalPrice: 199.99,
          image: 'https://images.unsplash.com/photo-1552664730-d307ca884978?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1770&q=80',
          category: 'Business',
          level: 'Intermediate to Advanced',
          duration: '8 weeks'
        },
        {
          id: 6,
          title: 'Personal Productivity Mastery',
          description: 'Learn time management, goal setting, and productivity systems to achieve more in less time.',
          instructor: 'Lisa Thompson',
          rating: 4.7,
          reviews: 487,
          students: 5940,
          price: 69.99,
          originalPrice: 139.99,
          image: 'https://images.unsplash.com/photo-1434030216411-0b793f4b4173?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1770&q=80',
          category: 'Personal Development',
          level: 'All Levels',
          duration: '6 weeks'
        }
      ]
    }
  },
  computed: {
    filteredCourses() {
      if (this.selectedCategory === 'All Courses') {
        return this.courses;
      }
      return this.courses.filter(course => course.category === this.selectedCategory);
    }
  }
}
</script>
