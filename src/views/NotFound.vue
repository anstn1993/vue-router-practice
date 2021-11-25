<template>
  <div>
    <h1>Not Found</h1>
    <p>
      Opps we coudn't find tha page. Try going
      <router-link :to="{ name: 'home' }">home</router-link>
    </p>
  </div>
</template>
