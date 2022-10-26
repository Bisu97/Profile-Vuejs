<template>
  <div id="app" >
    <div class="wrapper__my-profile">
<!--      <div class="theme__color">-->
<!--        <div class="theme__color&#45;&#45;heading">Tông màu</div>-->
<!--        <div-->
<!--          v-for="l in color_tag"-->
<!--          id="l.key"-->
<!--          :key="l.index"-->
<!--          :class="color===l.color? 'selected' : 'not-selected'"-->
<!--          :style="{backgroundColor:`${l.color}`}"-->
<!--          @click="m__set_color(l.color)"-->
<!--          class="theme__color&#45;&#45;item"-->
<!--        >-->
<!--          <div class="el-icon-check"/>-->
<!--        </div>-->
<!--      </div>-->
      <HeadingProfile/>
      <div class="user">
        <UserInfor/>
        <UserExp/>
      </div>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld'
import HeadingProfile from './components/HeadingProfile'
import UserExp from './components/UserExp'
import UserInfor from './components/UserInfor'

export default {
  name: 'App',
  data () {
    return {
      changeTheme: false
      // color: '',
      // color_tag: [
      //   { key: '0', color: '#213f4a', isSelected: true },
      //   { key: '1', color: '#247ba0', isSelected: false },
      //   { key: '2', color: '#32936f', isSelected: false },
      //   { key: '3', color: '#333333', isSelected: false },
      //   { key: '4', color: '#843b62', isSelected: false },
      //   { key: '5', color: '#ff6d86', isSelected: false },
      //   { key: '6', color: '#665479', isSelected: false }
      // ]
    }
  },
  components: {
    HeadingProfile,
    UserExp,
    UserInfor
    // HelloWorld
  },
  methods: {
    // m__set_color (color) {
    //   this.color = color
    // },
    // select (key) {
    //   for (let i = 0; i < this.color_tag.length; i++) {
    //     if (this.color_tag[i].key !== key) {
    //       this.color_tag[i].isSelected = false
    //     }
    //   }
    //   this.toggleSelection(key)
    // },
    // toggleSelection (key) {
    //   const stepsItem = this.color_tag.find(item => item.key === key)
    //   if (stepsItem) {
    //     stepsItem.isSelected = !stepsItem.isSelected
    //   }
    // }
  }
}
</script>

<style>
.theme__color--heading {
  margin-right: 10px;
}
.theme__color--item {
  width: 30px;
  height: 30px;
  border-radius: 50%;
  margin: 0 5px;
  cursor: pointer;
  position: relative;
}
.theme__color {
  display: flex;
  align-items: center;
  margin-bottom: 10px;
}
#app {
  font-family: 'Lato', sans-serif;
  max-width: 767px;
  margin: 20px auto;
  padding: 20px;
  box-shadow: rgb(0 0 0 / 24%) 0px 3px 8px;
}
*{
  margin: 0;
  padding: 0;
  border: 0;
}
html, body, div, span, applet, object, iframe,h1, h2, h3, h4, h5, h6, p{
  margin: 0;
  padding: 0;
  border: 0;
}
.user {
  display: flex;
  padding-top: 30px;
}
.theme__color--item.not-selected div {
  display: none;
}
.theme__color--item.selected div {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: #fff;
  font-size: 18px;
  display: block;
}
@media screen and (max-width: 660px) {
  .user {
    display: block;
  }
  .user__information,
  .user__exp {
    width: 100%;
  }
}

</style>
