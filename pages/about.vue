<template>
  <div id="educ" class="educsection-title"><h1>Educations</h1></div>
    <section class="section">
      <div class="content">
        <EducationCard :education="currentEducation" />
        <div class="navigation-arrows">
          <button @click="prevEducation" :disabled="currentIndex === 0">&#9664;</button>
          <button @click="nextEducation" :disabled="currentIndex === educationList.length - 1">&#9654;</button>
        </div>
      </div>
    </section>
    <div id="org" class="orgsection-title"><h1>Organizations</h1></div>
    <section class="section-organizations">
      <div class="scrollable-content">
        <div class="organization-item">
          <img src='/public/ssg.jpg' alt="MSU-Main SSG"/>
          <h3>MSU-Main SSG</h3>
          <p>CICS Chief Minister 2024-2025</p>
        </div>
        <div class="organization-item">
          <img src='/public/bytes.jpg' alt="MSU-BYTES CICS Student Council"/>
          <h3>MSU-BYTES CICS Student Council</h3>
          <p>President 2024-2025</p>
        </div>
        <div class="organization-item">
          <img src='/public/chc.jpg' alt="MSU-Commuters Hardcore"/>
          <h3>MSU-Commuters Hardcore</h3>
          <p>VP for Press and Information 2024-2025</p>
        </div>
        <div class="organization-item">
          <img src='/public/cursor.jpg' alt="The Cursor - CICS Student Publication"/>
          <h3>The Cursor-CICS Student Publication</h3>
          <p>Layout Editor 2023-2024</p>
        </div>
      </div>
</section>

</template>

<script setup>
const educationList = ref([
  { image: 'msu.jpg', level: 'College', institution: 'Mindanao State University - Marawi City', year: '2021 - present', description: 'Bachelor of Science in Computer Science', standing: 'CGPA: 1.48' },
  { image: 'socotech.jpg', level: 'Senior High School', institution: 'Southway College of Technology', year: '2019 - 2021', description: 'TVL - ICT Computer System Servicing NCII', standing: 'With High Honors' },
  { image: 'dlmnhs.jpg', level: 'Junior High School', institution: 'Datu Lipus Makapandong National High School', year: '2015 - 2019', description: '', standing: 'With Honors' },
])

const currentIndex = ref(0)
const currentEducation = ref(educationList.value[currentIndex.value])

const nextEducation = () => {
  if (currentIndex.value < educationList.value.length - 1) {
    currentIndex.value++
    currentEducation.value = educationList.value[currentIndex.value]
  }
}

const prevEducation = () => {
  if (currentIndex.value > 0) {
    currentIndex.value--
    currentEducation.value = educationList.value[currentIndex.value]
  }
}
</script>
