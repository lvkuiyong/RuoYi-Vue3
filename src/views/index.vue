<template>
  <div class="app-container home">
    <el-row :gutter="20">
      <el-col :sm="24" :lg="12" style="padding-left: 20px">

        <!-- <h2>企业管理系统</h2>
        <p>
          前后端分离的后台管理系统
        </p> -->

        <h2>内置功能模块</h2>
        <ol>
          <li>部门管理：配置系统组织机构（公司、部门、小组），树结构展现支持数据权限</li>
          <li>用户管理：用户是系统操作者，该功能主要完成系统用户配置</li>
          <li>岗位管理：配置系统用户所属担任职务</li>
          <li>角色管理：角色菜单权限分配、设置角色按机构进行数据范围权限划分</li>
          <li>登录日志：系统登录日志记录查询包含登录异常</li>
          <li>通知公告：系统通知公告信息发布维护</li>
          <li>在线用户：当前系统中活跃用户状态监控</li>
          <li>服务监控：监视当前系统CPU、内存、磁盘、堆栈等相关信息</li>
          <li>缓存监控：对系统的缓存信息查询，命令统计等</li>
          <li>连接池监视：监视当期系统数据库连接池状态，可进行分析SQL找出系统性能瓶颈</li>
          <li>系统接口：业务代码相关的api接口文档</li>
        </ol>

        <!-- <p>
          <b>当前版本:</b> <span>v{{ version }}</span>
        </p> -->

      </el-col>

      <el-col :sm="24" :lg="12" style="padding-left: 50px">
        <el-row>
          <el-col :span="12">
            <h2>技术选型</h2>
          </el-col>
        </el-row>
        <el-row>
          <el-col :span="6">
            <h4>后端技术</h4>
            <ul>
              <li>Spring Boot</li>
              <li>Spring Security</li>
              <li>Docker</li>
              <li>MYSQL</li>
              <li>Redis</li>
              <li>MyBatis</li>
              <li>Druid</li>
            </ul>
          </el-col>
          <el-col :span="6">
            <h4>前端技术</h4>
            <ul>
              <li>Vue.js</li>
              <li>Node.js</li>
              <li>Yarn</li>
              <li>Vite</li>
              <li>Element Plus</li>
              <li>Axios</li>
              <li>Pinia</li>
            </ul>
          </el-col>
        </el-row>

        <!-- <h2>主要特性</h2>
        <ol>
          <li>完全响应式布局（支持电脑、平板、手机等所有主流设备）</li>
          <li>支持按钮及数据权限，可自定义部门数据权限</li>
          <li>对常用js插件进行二次封装，使js代码变得简洁，更加易维护</li>
          <li>完善的XSS防范及脚本过滤，彻底杜绝XSS攻击</li>
          <li>完善的日志记录体系，简单注解即可实现</li>
        </ol> -->

      </el-col>
    </el-row>
    <el-divider />

    <!-- <el-row :gutter="20">
      <el-col :xs="24" :sm="24" :md="24" :lg="24">
        <el-card class="update-log">
          <template v-slot:header>
            <div class="clearfix">
              <span>更新日志</span>
            </div>
          </template>
          <el-collapse accordion>
            <el-collapse-item title="v3">
              <ol>
                <li>引入路由懒加载、Gzip压缩优化性能。</li>
                <li>核心组件版本迭代，修复漏洞并增强兼容性。</li>
                <li>集成 XSS过滤、防重复提交注解、IP黑名单，屏蔽定时任务远程调用。</li>
                <li>密码策略强化：非法字符验证、错误次数限制、特殊字符兼容。</li>
                <li>用户管理支持部门分栏拖动、过滤已禁用部门，优化导入校验与数据权限控制。</li>
                <li>角色权限实时同步缓存，修复禁用后权限未生效问题；菜单支持多级面包屑、TopNav 布局、路由参数配置。</li>
                <li>数据权限支持多角色合并查询、编程式判断，防止越权访问，菜单权限细化至按钮级别。</li>
                <li>树表展开/折叠，修复上级菜单显示与关联查询问题。</li>
                <li>子列表导出、自定义数据处理器。</li>
                <li>优化导入性能：减少缓存重复查询、兼容大数据量下拉框，修复导出子列表位置与空数组显示问题。</li>
                <li>新增缓存监控，操作日志记录部门名称、IP 地址及 DELETE 请求参数。</li>
                <li>日志优化：索引提升查询性能、过滤敏感字段，修复权限更新后缓存不同步问题。</li>
                <li>布局优化：TopNav 高亮匹配、Mini 布局错乱修复、页签支持关闭指定标签，菜单名称悬停提示。</li>
                <li>交互细节：导出遮罩层、表单拖拽排序、小屏幕适配，修复内链页面参数丢失与标签页刷新问题。</li>
                <li>修复 SQL 注入、XSS、反序列化漏洞，移除高危依赖，升级Spring Security。</li>
                <li>支持多文件批量上传、富文本文件大小限制，修复文件名特殊字符下载与图片透明色显示问题。</li>
                <li>通用工具：自定义 XSS 校验、国际化配置、密码强度验证。</li>
                <li>统一组件版本，修复样式冲突，提升组件稳定性。</li>
              </ol>
            </el-collapse-item>
          </el-collapse>
        </el-card>
      </el-col>
    </el-row> -->

  </div>
</template>

<script setup name="Index">
const version = ref('3')

function goTarget(url) {
  window.open(url, '__blank')
}
</script>

<style scoped lang="scss">
.home {
  blockquote {
    padding: 10px 20px;
    margin: 0 0 20px;
    font-size: 17.5px;
    border-left: 5px solid #eee;
  }
  hr {
    margin-top: 20px;
    margin-bottom: 20px;
    border: 0;
    border-top: 1px solid #eee;
  }
  .col-item {
    margin-bottom: 20px;
  }

  ul {
    padding: 0;
    margin: 0;
  }

  font-family: "open sans", "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-size: 13px;
  color: #676a6c;
  overflow-x: hidden;

  ul {
    list-style-type: none;
  }

  h4 {
    margin-top: 0px;
  }

  h2 {
    margin-top: 10px;
    font-size: 26px;
    font-weight: 100;
  }

  p {
    margin-top: 10px;

    b {
      font-weight: 700;
    }
  }

  .update-log {
    ol {
      display: block;
      list-style-type: decimal;
      margin-block-start: 1em;
      margin-block-end: 1em;
      margin-inline-start: 0;
      margin-inline-end: 0;
      padding-inline-start: 40px;
    }
  }
}
</style>

