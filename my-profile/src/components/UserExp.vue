<template>
  <div class="user__exp">
    <div v-for="(userExp,i) in usersExp" :key="i" class="user__exp-wrapper">
      <div class="user__exp--heading">
        <h3>{{ userExp.name }}</h3>
      </div>
      <div v-for="(activity,i) in userExp.jobsActivities" :key="i" class="user__exp--main-work">
        <div class="user__exp--main-work--name--company">
          <p class="user__exp--main-work--name--company--address">{{ activity.workAt }}</p>
          <p class="user__exp--main-work--name--company--year">{{ activity.timeLine }}</p>
        </div>
        <div v-if="activity.specialized.length !== 0" class="user__exp--main-work--name--specialized">Chuyên nghành: {{ activity.specialized }}</div>
        <ul>
          <li v-for="(workname,i) in activity.content" :key="i">
            <p class="user__exp--main-work--description">{{ workname }}</p>
          </li>
        </ul>
        <div v-if="activity.project.length !== 0" class="user__exp--main-work--project">
          <div class="user__exp--main-work--project--heading">
            + Các dự án đã tham gia
          </div>
          <ul>
            <li v-for="(item,i) in activity.project" :key="i">
              <div class="">
                <p class="user__exp--main-work--project--name">{{ item.nameProject }}<span class="user__exp--main-work--project--platform">({{ item.platform }})</span></p>
                <p v-if="item.website.length !== 0" class="user__exp--main-work--project-website">Website : <span><a class="user__exp--main-work--project-website-name" :href="item.website" target="">{{ item.website }}</a></span></p>
              </div>
              <div>
                <ul>
                  <li v-for="(content,i) in item.description" :key="i">
                    <p class="user__exp--main-work--project-task">{{ content }}</p>
                  </li>
                </ul>
              </div>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'UserExp',
  data () {
    return {
      usersExp: [
        {
          name: 'Học vấn',
          jobsActivities: [
            {
              workAt: 'Đại học FPT-Hòa Lạc',
              timeLine: '06/2015 - 05/2020',
              specialized: 'Software-Engineering',
              project: [],
              content: ['Tiếng Anh : Chứng chỉ Submit 2 theo quy định của trường đại học FPT', 'Sản phẩm đồ án được yêu cầu bởi các nhân viên của trường đại học FPT : Hệ thống quản lý các nguồn tài nguyên ( mảng Front-End )']
            },
            {
              timeLine: '01/2018 - 5/2018',
              workAt: 'Thực tập chuyên nghành Frond-end tại Fsoft-Hòa Lạc',
              specialized: '',
              project: [],
              content: ['Học tập về HTML , CSS , Jquery , JavaScript , Bootstraps , thiết kế giao diện website , SQL(Basic),...', 'Sử dụng HTML , CSS , Responsive để thiết kế cho dự án PirollThiết kế dự án cuối khóa với website BookStoreCó kiến thức về Responsive cho website và Bootstraps', 'Có kiến thức về JavaScript phục vụ cho việc tạo hiệu ứng website', 'Có kiến thức về SQL cơ bản', 'Học kỹ năng mềm như thuyết trình , Tiếng Anh , làm việc nhóm , ...']
            },
            {
              timeLine: '04/2020 - 9/2020',
              workAt: 'Nhân viên IT tại Công Ty Cổ Phần Đầu Tư Châu á Thái Bình Dương APEC',
              specialized: '',
              project: [],
              content: ['Được học tập và nghiên cứu về Angular framework', 'Thực hành tạo một website cơ bản Phatthinhrating.com với Angular framework', 'Thực hiện chức năng filter , hiển thị số phòng trong dự án Smart-Hotel', 'Được học tập và nghiên cứu về Laravel framework , sử dụng Mysql', 'Thực hành tạo một website cơ bản với CRUD', 'Tìm hiểu code với website Booking.mandalainn.com trong dự án Smart-Hotel ( sử dụng Backpack pakage )', 'Tạo thêm chức năng cho website Booking.mandalainn.com là thanh toán bằng voucher , gửi email thông báo về cho người dùng , import file excel vào trong phần admin của website', 'Có tìm hiểu về Python và code theo hướng dẫn ra một trợ lý ảo']
            },
            {
              timeLine: '11/2020 - 6/2022',
              workAt: 'Front-end Developer tại Công ty AHT JSC',
              specialized: '',
              content: [
                'Tham gia vào các dự án xây dựng trang web với HTML, CSS, JQ',
                'Đảm bảo chất lượng , responsive trang web cho các thiết bị',
                'Làm việc với nền tảng Shopify',
                'Làm việc với nền tảng Bigcommerce',
                'Nâng cấp , chỉnh sửa các store Shopify'
              ],
              project: [
                {
                  nameProject: 'Karolyna York',
                  platform: 'Bigcommerce',
                  website: '',
                  description: [
                    'Làm việc và xây dựng page theo design có sẵn (cms page,account page,cart page)',
                    'Viết jq cho các chức năng và custom function theo design'
                  ]
                },
                {
                  nameProject: 'Restoration',
                  platform: 'Bigcommerce',
                  website: 'https://restoration-online.mybigcommerce.com/',
                  description: [
                    'Làm việc và xây dựng page theo design có sẵn (cms page,account page,cart page)',
                    'Viết jq cho các chức năng và custom function theo design',
                    'Call API get data và xây dựng page theo data trả về'
                  ]
                },
                {
                  nameProject: 'Swagnsend',
                  platform: 'Shopify',
                  website: 'https://swagnsend.com/',
                  description: [
                    'Làm việc và xây dựng page theo design có sẵn (cms page,account page,cart page)',
                    'Viết jq cho các chức năng và custom function theo design'
                  ]
                },
                {
                  nameProject: 'Homie furniture',
                  platform: 'Shopify',
                  website: '',
                  description: [
                    'Làm việc và xây dựng page theo design có sẵn (cms page,account page,cart page)',
                    'Viết jq cho các chức năng và custom function theo design',
                    'Các công việc ourcourcing về nâng cấp , chỉnh sửa và update store Shopify'
                  ]
                },
                {
                  nameProject: 'The Base Warehouse',
                  platform: 'Shopify',
                  website: 'https://www.thebasewarehouse.com.au/',
                  description: [
                    'Làm việc và xây dựng page theo design có sẵn (cms page,account page,cart page)',
                    'Viết jq cho các chức năng và custom function theo design',
                    'Các công việc về nâng cấp , chỉnh sửa và update store Shopify'
                  ]
                },
                {
                  nameProject: 'Tiger Lily',
                  platform: 'Shopify',
                  website: 'https://tigerlily-au-staging.myshopify.com/',
                  description: [
                    'Làm việc và xây dựng page theo design có sẵn (cms page,account page,cart page)',
                    'Viết jq cho các chức năng và custom function theo design'
                  ]
                },
                {
                  nameProject: 'Brendan',
                  website: '',
                  platform: 'Shopify',
                  description: [
                    'Là công việc outsourcing , một công ty của Đan Mạch, làm việc với các yêu cầu của khách hàng về Shopify'
                  ]
                }
              ]
            },
            {
              workAt: 'Front-end Developer tại Atosa',
              specialized: '',
              timeLine: '6/2022 - 11/2022',
              project: [
                {
                  nameProject: 'Atosa Search keywords',
                  platform: 'ReactJS',
                  website: '',
                  description: [
                    'Xây dựng layout cho website (html,css)',
                    'Dùng ReactJS để xây dựng tính năng cho website',
                    'Call API get data và xây dựng page theo data trả về',
                    'Dùng các thư viện liên quan để tạo bố cục , tính năng cho website'
                  ]
                },
                {
                  nameProject: 'Atosa chat',
                  platform: 'VueJS',
                  website: '',
                  description: [
                    'Xây dựng layout cho website (html,css)',
                    'Dùng VueJS để xây dựng tính năng cho website',
                    'Call API get data và xây dựng page theo data trả về',
                    'Dùng các thư viện liên quan để tạo bố cục , tính năng cho website',
                    'Các tính năng cơ bản : Tìm kiếm , bộ lọc , chat realtime , showdate , validate , xem/thêm/sửa/xoá , ...'
                  ]
                }
              ],
              content: ['Trainning ReactJS', 'Trainning Vuejs']
            }
          ]
        },
        {
          name: 'HOẠT ĐỘNG',
          jobsActivities: [
            {
              workAt: 'Tham gia Chess Club',
              timeLine: '06/2017 - 06/2018',
              specialized: '',
              project: [],
              content: ['Cựu chủ nhiệm Chess Club', 'Tham gia các giải Cờ tại các trường đại học tổ chức cũng như làm các công tác về tổ chức giải Cờ tại Đại Học FPT']
            }
          ]
        },
        {
          name: 'CHỨNG CHỈ',
          jobsActivities: [
            {
              workAt: '',
              specialized: '',
              project: [],
              content: ['Tiếng Anh : Summit 2 ( theo quy định của trường đại học FPT )', 'Chứng chỉ khóa học online về Đạo đức nghề nghiệp trên Coursera', 'Chứng chỉ khóa học Project Management trên Coursera ', 'Tham gia các khóa học online trên Code Learn']
            }
          ]
        },
        {
          name: 'THÔNG TIN THÊM',
          jobsActivities: [
            {
              workAt: '',
              specialized: '',
              project: [],
              content: ['Mong muốn được tiếp thu thêm kiến thức cũng như kinh nghiệp khi đi làm ở một vị trí lập trình viên', 'Sẵn sàng học và tiếp thu công nghệ mới trong môi trường 4.0', 'Bản thân là người hòa đồng và thích các công việc hoạt động tập thể , ngoại khóa vv..']
            }
          ]
        }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@media screen and (max-width: 660px) {
  .user .user__exp {
    width: 100%;
    padding: 0;
    margin-top: 40px;
  }
  .user__exp--main-work .user__exp--main-work--name--company {
    display: block;
  }
  .user__exp--main-work .user__exp--main-work--name--company p.user__exp--main-work--name--company--year {
    padding: 5px 0;
  }
}
.user__exp {
  width: 67%;
  padding-left: 30px;
}
.user__exp--heading {
  font-size: 16px;
  position: absolute;
  padding-right: 20px;
  top: 0;
  transform: translate(0,-50%);
  background-color: #fff;
}
.user__exp--main-work {
  padding: 18px 0 15px;
}
.user__exp-wrapper {
  border-top: 1px solid #213f4a;
  position: relative;
  margin-top: 10px;
}
h3 {
  text-transform: uppercase;
  font-size: 24px;
  color: #213f4a;
  background-color: #fff;
  display: inline;
}
.user__exp--main-work--name--company {
  font-weight: 700;
  font-size: 21px;
  display: flex;
  align-items: end;
  justify-content: space-between;
}
p.user__exp--main-work--name--company--year {
  font-size: 12px;
  font-weight: 500;
}
.user__exp--main-work ul {
  padding-inline-start: 18px;
  line-height: 21px;
}
.user__exp--main-work--project--heading {
  text-decoration: underline;
  font-size: 18px;
  padding-top: 10px;
  font-weight: 700;
}
p.user__exp--main-work--project--name {
  padding-top: 10px;
  font-weight: 700;
  font-size: 18px;
}
p.user__exp--main-work--project-task {
  font-size: 16px;
  margin-bottom: 5px;
}
span.user__exp--main-work--project--platform {
  font-size: 14px;
  font-weight: 500;
  margin-left: 5px;
}
</style>

