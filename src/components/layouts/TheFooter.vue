<template>
  <footer class="footer">
    <div class="container">
      <div class="row footer-top">
        <div class="col-sm-5 col-lg-5">
          <p class="padding-top-xsm">{{ description }}</p>

          <div class="text-md">
            <a v-for="item in contacts" v-title="item.title" :href="item.link" :style="contactStyle" target="_blank">
              <i :class="`fa fa-${item.icon}`"></i>
            </a>
          </div>

          <br>

          <span v-html="designer"></span>
        </div>

        <div class="col-sm-6 col-lg-6 col-lg-offset-1">
          <div class="row">
            <div class="col-sm-4">
              <h4>{{ sponsor.title }}</h4>

              <ul class="list-unstyled">
                <li v-for="item in sponsor.list">
                  <a :href="item.link" target="_blank">
                    <img v-title="item.title" :src="item.logo" :alt="item.title" class="footer-sponsor-link" width="98">
                  </a>
                </li>
              </ul>
            </div>

            <div class="col-sm-4">
              <h4>{{ statistics.title }}</h4>

              <ul class="list-unstyled">
                <li v-for="item in statistics.list">{{ item.title }}: {{ item.description }}</li>
              </ul>
            </div>

            <div class="col-sm-4">
              <h4>{{ other.title }}</h4>

              <ul class="list-unstyled">
                <li v-for="item in other.list">
                  <a :href="item.link" :title="item.title" target="_blank">
                    <i :class="`fa fa-${item.icon}`"></i> {{ item.title }}
                  </a>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
  import title from "@/directives/title.js"
  export default {
    name: 'TheFooter',
    // 添加 directives 选项，并注册 title
    directives: {
      title
    },
    data() {
      return {
        description: 'VuejsCaff 是一个 Vue.js 的知识社区',
        contacts: [
          {
            icon: 'envelope',
            title: '反馈问题',
            link: 'mailto:982397045@qq.com'
          },
          {
            icon: 'weibo',
            title: '站长微博',
            link: 'https://weibo.com/1837553744/profile?topnav=1&wvr=6'
          },
          {
            icon: 'weixin',
            title: '加我微信',
            link: 'https://vuejscaff.com/contact'
          }
        ],
        contactStyle: {
          paddingRight: '8px'
        },
        designer: `
        <span style="font-size:0.9em">Designed by
          <span style="color: #e27575;font-size: 14px;">❤</span>
          <a href="https://github.com/userNamepnn"target="_blank"style="color:inherit">PanNinan</a>
        </span>`,
        sponsor: {
          title: '赞助商',
          list: [
            {
              logo: 'https://iocaffcdn.phphub.org/uploads/banners/bQawWl3vT5dc2lYx5JZ7.png',
              title: '本站服务器没由 UCloud 赞助',
              link: 'http://www.ucloud.cn/?utm_source=zanzhu&utm_campaign=phphub&utm_medium=display&utm_content=yejiao&ytag=phphubyejiao'
            },
            {
              logo: 'https://iocaffcdn.phphub.org/uploads/banners/XPtLlZmIN1cQbLuDFEON.png',
              title: 'Composer 镜像赞助商没有赞助',
              link: 'https://www.upyun.com/'
            },
            {
              logo: 'https://iocaffcdn.phphub.org/uploads/banners/JpTCK6OKYBIrBIWdtob8.png',
              title: '订阅邮件赞助商：SendCloud也没有赞助',
              link: 'http://www.sendcloud.net/'
            }
          ]
        },
        statistics: {
          title: '统计信息',
          list: [
            {
              title: '社区会员',
              description: '1'
            },
            {
              title: '话题数',
              description: '100'
            },
            {
              title: '评论数',
              description: '250'
            }
          ]
        },
        other: {
          title: '其他信息',
          list: [
            {
              icon: 'thumbs-up',
              title: '吹牛皮服务',
              link: '#'
            },
            {
              icon: 'globe',
              title: '瞎扯淡网站',
              link: '#'
            }
          ]
        }
      }
    }
  }
</script>

<style scoped>
  a:hover, a:focus { color: #e27575; transition: color .15s;}
</style>
