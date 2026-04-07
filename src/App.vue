<script setup>
import HelloWorld from './components/HelloWorld.vue'
import UserCard from './components/UserCard.vue'
import Tags from './components/Tags.vue'
</script>


<template>
  <Tags/>
  <HelloWorld />
  <section id="user-info">
  <UserCard 
    name="شهاب بندر" 
    role="مصمم واجهات" 
    status="نشط" 
    
  />
  <UserCard 
    name="علي توفيق" 
    role="مصمم تجربة مستخدم" 
    status="غير متصل" 
  />
</section>


</template>
