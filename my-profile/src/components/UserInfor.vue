<template>
  <div class="user__information">
    <div class="user__information--image">
      <img :src="user.image" alt=""/>
    </div>
    <div class=user__information--myself>
      <ul>
        <li>
          <div>Ngày sinh</div>
          <p>{{ user.dob }}</p>
        </li>
        <li>
          <div>Giới tính</div>
          <p>{{ user.sex }}</p>
        </li>
        <li>
          <div>Điện thoại</div>
          <p>{{ user.phone }}</p>
        </li>
        <li>
          <div>Email</div>
          <p>{{ user.email }}</p>
        </li>
        <li>
          <div>Địa chỉ</div>
          <p>{{ user.address }}</p>
        </li>
        <li>
          <div>Website</div>
          <p>{{ user.website }}</p>
        </li>
        <li>
          <div class="user__information--myself--career">Mục tiêu nghề nghiệp</div>
          <p>{{ user.careerGoals }}</p>
        </li>
        <li>
          <div class="user__information--myself--list--skills">Kỹ năng</div>
          <ul>
            <li v-for="skill in user.skills" :key="skill.index" class="user__information--myself--skill">
              {{skill.name}}
              <progress id="file" :value="skill.percentage" max="100"></progress>
              <el-progress :text-inside="true" :stroke-width="26" :percentage="skill.percentage"></el-progress>
            </li>
          </ul>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'UserInfor',
  data () {
    return {
      user: {
        image: 'https://static.topcv.vn/avatars/YwO3MUsG7TOitxs22eTw_5c2b14f6ab826_cvtpl.jpg?1666705952',
        dob: '11/10/1997',
        sex: 'Nam',
        phone: '0973460759',
        email: 'datnqse@gmail.com',
        address: 'Số 2 , Nghách 86/16 ,  Khương Trung , Thanh Xuân',
        website: 'https://www.facebook.com/cassvip.kolboy',
        careerGoals: 'Muốn được học tập , thực chiến và tiếp thu thêm kinh nghiệp với các kỹ năng Front-end cũng như Back-end để có thể tiến tới vị trí Full-stack',
        skills: [
          {
            name: 'Tin học văn phòng',
            percentage: '80'
          },
          {
            name: 'Tiếng Anh',
            percentage: '50'
          }
        ]
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@media screen and (max-width: 660px) {
  .user .user__information {
    width: 100%;
  }
}
.user__information {
  width: 33%;
}
.user__information .user__information--image img {
  display: block;
  width: 100%;
  object-fit: contain;
}
.user__information--myself {
  background-color: #213f4a;
  padding: 20px 15px;
}
.user__information--myself ul {
  list-style-type: none;
}
.user__information--myself ul li {
  margin-bottom: 10px;
}
.user__information--myself ul li div {
  font-size: 16px;
  color: #627e88;
}
.user__information--myself ul li p {
  font-size: 15px;
  color: #fff;
  word-break: break-word;
}
.user__information--myself ul li .user__information--myself--career,
.user__information--myself ul li .user__information--myself--list--skills {
  font-size: 16px;
  color: #fff;
  text-transform: uppercase;
  padding: 30px 0 15px 0;
}
li.user__information--myself--skill {
  font-size: 16px;
  color: #fff;
}
progress#file {
  width: 100%;
}
</style>
