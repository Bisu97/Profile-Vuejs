<template>
  <div class="heading">
    <h1 class="heading__title">{{ nameTitle }}</h1>
    <div class="heading__job">
      <p class="heading__job--title">{{ jobTitle }}</p>
      <p class="heading__job--description">{{ descriptionJob }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HeadingProfile',
  data () {
    return {
      nameTitle: 'Nguyễn Quốc Đạt',
      jobTitle: 'Lập trình viên',
      descriptionJob: 'HTML,CSS,JavaScript,Jquerry,VueJS,...'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@media screen and (max-width: 660px) {
  .heading h1.heading__title {
    position: unset;
    text-align: center;
    background-color: unset;
    color: #fff;
  }
  .heading .heading__job {
    text-align: center;
  }
}
.heading {
  background-color: #213f4a;
  padding: 20px;
  position: relative;
}
h1.heading__title {
  position: absolute;
  top: 0;
  left: 0;
  background-color: #fff;
  padding: 10px;
  font-size: 36px;
}
.heading__job {
  text-align: right;
  font-size: 16px;
  text-transform: capitalize;
  color: #fff;
}
</style>
