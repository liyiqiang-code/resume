<template>
  <div class="home">
    <!-- 个人信息 -->
    <div class="person">
      <Header>个人信息</Header>
      <div>
        <ul class="basic">
          <li>姓名：李一强</li>
          <li>性别：男</li>
          <li>年龄：24</li>
          <li>工作年限：2年</li>
          <li>电话：184-7627-7043</li>
          <li>邮箱：lyq2020928@163.com</li>
        </ul>
      </div>
    </div>
    <!-- 求职意向 -->
    <div class="intention">
      <Header>求职意向</Header>
      <ul class="">
        <li>求职岗位：Web前端开发工程师</li>
        <li>目标地点：深圳</li>
        <li>目前状况：离职</li>
        <li>期望薪资：面议</li>
      </ul>
    </div>
    <!-- 专业技能 -->
    <div class="skill">
      <Header>专业技能</Header>
      <div class="skill_list" v-for="(item, index) in state.skill" :key="index">
        {{ item }}；
      </div>
    </div>

    <!-- 工作经历 -->
    <Header>工作经历</Header>
    <div
      class="work_experience"
      v-for="(item, index) in state.workExperience"
      :key="index"
    >
      <div>{{ item.time }}</div>
      <div>{{ item.name }}</div>
      <div>{{ item.position }}</div>
    </div>

    <!-- 项目经历 -->
    <Header>项目经历</Header>
    <div
      class="project_experience"
      v-for="(item, index) in state.projectExperience"
      :key="index"
    >
      <div class="public">
        <div class="tips">项目名称：</div>
        <div>{{ item.name }}</div>
      </div>
      <div class="public">
        <div class="tips">项目时间：</div>
        <div>{{ item.time }}</div>
      </div>
      <div class="public">
        <div class="tips">项目描述：</div>
        <div>{{ item.describe }}</div>
      </div>
      <div class="public">
        <div class="tips">项目责任：</div>
        <div>{{ item.duty }}</div>
      </div>
      <div>
        <div class="tips">技术描述：</div>
        <div class="kill" v-for="(item2, index2) in item.kill" :key="index2">
          {{ index2 + 1 }}.{{ item2 }}
        </div>
      </div>
    </div>
    <!-- 教育背景 -->
    <Header>教育背景</Header>
    <div class="educate_background">
      <div>2016.09-2019.06</div>
      <div>专科</div>
      <div>通信工程</div>
      <div>东莞理工学院城市学院</div>
    </div>
  </div>
</template>

<script>
import { reactive } from "@vue/reactivity";
// @ is an alias to /src
import Header from "../components/Header.vue";

export default {
  name: "Home",
  components: {
    Header,
  },
  setup() {
    const state = reactive({
      skill: [
        "熟悉 W3C 规范，掌握 div+css 布局，能结合 Web 标准，准确还原设计稿",
        "熟悉流式布局(百分比布局)，rem 布局，vw/vh 布局，响应式布局与 less，scss 预编译器",
        "掌握原生 JavaScript 的 API 操作 DOM,BOM 元素",
        "熟悉用Apache ECharts进行可视化开发",
        "熟悉 Ajax 获取数据来进行前后端交互，了解前端各种跨域问题",
        "熟悉 ES6 的新特性(let/const, 模板字符串，展开运算符，解构赋值等常用功能)",
        "掌握使用 Vue.js 、nuxt.js、uniapp 框架，原生微信小程序开发",
        "对于 JS 中的面向对象，继承，闭包，递归等有知识有一定了解",
        "熟悉W3C标准、页面布局架构、前端语义化、浏览器兼容性等，重视用户体验与代码可维护性",
        "熟悉使用 jQuery 操作页面元素，并能实现常见的业务逻辑以及特效",
        "熟悉 git 进行项目版本管理",
      ],
      workExperience: [
        {
          // 公司名称
          name: "佛山市鹰视能效科技公司",
          // 工作时间和职位
          time: "2020-12 - 2021-12",
          // 职位
          position: "WEB前端开发工程师",
        },
        {
          // 公司名称
          name: "佛山市合广通科技有限公司",
          // 工作时间和职位
          time: "2019-09 - 2020-11",
          // 职位
          position: "WEB前端开发工程师",
        },
      ],
      projectExperience: [
        {
          //项目名称
          name: "鹰视能效（小程序）",
          //项目时间
          time: "2020.12~至今",
          // 项目描述
          describe:
            "建立一个围绕设备厂家，客户以及服务团队的基于互联网的电力服务平台，主要模块有我的，设备，能效，消息，用电等",
          // 项目责任
          duty: "主要负责改小程序的迭代开发，新增能效板块，修复bug，新增特性，修改样式，提高用户体验感",
          // 技术描述
          kill: [
            "主要负责用原生微信小程序搭配vant，Apache ECharts",
            "利用Apache ECharts来绘制图标",
            "对wx.request进行封装，把api抽取模块",
            "将比较固定的数据通过wx.setStorage缓存到本地，当第二次切换到这个页面时，先使用本地的缓存数据 进行渲染，后面再通过请求的数据来进行更新",
            "封装图表组件，方便复用组件",
          ],
        },
        {
          //项目名称
          name: "鹰巢（web后台）",
          //项目时间
          time: "2020.12~至今",
          // 项目描述
          describe:
            "善用能源的践行者，帮助企业高效管理用电，监视各个厂商的设备异常情况",
          // 项目责任
          duty: "迭代开发，封装组件，提高用户体验感，修复bug",
          // 技术描述
          kill: [
            "主要负责用vue框架,Ant Design组件快速开发",
            "使用axios实现前后台的数据交互实现表单，增删改查等",
            "使用Ant Design表格展示数据，表单条件查询",
            "文件的上传下载",
            "利用Apache ECharts绘制图表",
            "使用CDN和减少不必要的库来优化打包后的代码体积",
          ],
        },
        {
          //项目名称
          name: " 能效管理（uniapp）",
          //项目时间
          time: " 2021.09~ 2021.10",
          // 项目描述
          describe:
            "善用能源的践行者，帮助企业高效管理用电，监视各个厂商的设备异常情况",
          // 项目责任
          duty: "独立开发，项目需求分析，技术选型",
          // 技术描述
          kill: [
            "主要负责用uniapp,uviewUI组件库快速开发",
            "使用秋云uCharts绘制图表",
            "封装请求文件",
            "文件的上传下载",
            "打包app并测试",
          ],
        },
        {
          //项目名称
          name: "保御-智慧社区预警平台",
          //项目时间
          time: "2019-09 - 2020-11",
          // 项目描述
          describe:
            "接收终端设备的实时情况，当发生报警或异常时，将数据传输到后台",
          // 项目责任
          duty: "从0构建,项目需求分析，技术选型，项目架构搭建，公用代码的封装及优化",
          // 技术描述
          kill: [
            "使用vue全家桶、Element-ui快速构建",
            "使用Apache ECharts绘制图表",
            "封装公共模块,实现组件模块化并复用",
            "使用websocket实时监控各个设备实时情况",
            "使用CDN和减少不必要的库来优化打包后的代码体积",
            "优化代码，提高页面加载速度，优化用户体验感",
          ],
        },
      ],
    });
    return {
      state,
    };
  },
};
</script>

<style lang="scss" scoped>
.home {
  .basic {
    display: flex;
    flex-wrap: wrap;
    li {
      width: 250px;
      height: 30px;
      line-height: 30px;
    }
  }
  .intention {
    ul {
      display: flex;
      flex-wrap: wrap;
      li {
        width: 400px;
        height: 30px;
        line-height: 30px;
      }
    }
  }

  .skill {
    .skill_list {
      height: 30px;
      line-height: 30px;
    }
  }

  .work_experience {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 800px;
    div {
      height: 30px;
      flex: 1;
      line-height: 30px;
    }
  }

  .project_experience {
    margin-bottom: 15px;
    .tips {
      font-weight: 900;
    }
    .kill {
      padding-left: 80px;
    }
    .public {
      display: flex;
    }
  }

  .educate_background {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 700px;
    margin-bottom: 20px;
  }
}
</style>
