<template>
  <div class="app-container home">
    <el-row :gutter="20">
      <el-col :sm="24" :lg="12" style="padding-left: 20px">
        <h2>后台管理</h2>
        <p>
          一款后台管理系统
        </p>
        <p>
          <b>当前版本:</b> <span>v{{ version }}</span>
        </p>
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
              <li>SpringBoot</li>
              <li>Spring Security</li>
              <li>JWT</li>
              <li>MyBatis</li>
              <li>Druid</li>
              <li>Fastjson</li>
            </ul>
          </el-col>
          <el-col :span="6">
            <h4>前端技术</h4>
            <ul>
              <li>Vue</li>
              <li>Vuex</li>
              <li>Element-ui</li>
              <li>Axios</li>
              <li>Sass</li>
              <li>Quill</li>
            </ul>
          </el-col>
        </el-row>
      </el-col>
    </el-row>
    <el-divider />
    <el-row :gutter="20">

      <el-col :xs="24" :sm="24" :md="24" :lg="24">
        <el-card class="update-log">
          <template v-slot:header>
            <div class="clearfix">
              <span>更新日志</span>
            </div>
          </template>
          <el-collapse accordion>
            <el-collapse-item title="v3.8.9">
              <ol>
                <li>单应用重构为<b>多模块项目</b>，提升可维护性，引入路由懒加载、Gzip压缩优化性能。</li>
                <li><b>Spring Boot</b> 升级至 3，核心组件（Druid/FastJSON/Oshi 等）全版本迭代，修复漏洞并增强兼容性。</li>
                <li>集成 <b>XSS过滤</b>、<b>防重复提交注解（@RepeatSubmit）</b>、<b>IP黑名单</b>，屏蔽定时任务远程调用（LDAP/HTTP/S/RMI）。</li>
                <li>密码策略强化：非法字符验证、错误次数限制、特殊字符兼容，身份证脱敏正则优化。</li>
                <li>用户管理支持部门分栏拖动、头像 HTTP(S) 链接、过滤已禁用部门，优化导入校验与数据权限控制。</li>
                <li>角色权限实时同步缓存，修复禁用后权限未生效问题；菜单支持多级面包屑、TopNav 布局、路由参数配置。</li>
                <li>数据权限支持多角色合并查询、编程式判断，防止越权访问，菜单权限细化至按钮级别。</li>
                <li>代码生成器支持<b>主子表结构</b>、<b>Vue3前端模板</b>、自定义路径与文件覆盖，屏蔽违规字符。</li>
                <li>字段映射优化：Boolean 类型支持、字典关联查询、树表展开/折叠，修复上级菜单显示与关联查询问题。</li>
                <li>新增代码预览与复制功能，支持前端模板类型选择，修复代码生成后必填项与数据库不匹配问题。</li>
                <li>Excel 注解增强：单元格换行（wrapText）、背景色/字体颜色、字典映射（dictType）、子列表导出、自定义数据处理器。</li>
                <li>优化导入性能：减少缓存重复查询、兼容大数据量下拉框，修复导出子列表位置与空数组显示问题。</li>
                <li>新增缓存监控、定时任务管理（在线生成 Cron 表达式），操作日志记录部门名称、IP 地址及 DELETE 请求参数。</li>
                <li>日志优化：索引提升查询性能、过滤敏感字段，修复权限更新后缓存不同步问题。</li>
                <li>新增图片预览/上传组件（支持多图）、富文本编辑器（视频上传）、可拖动弹窗指令。</li>
                <li>布局优化：TopNav 高亮匹配、Mini 布局错乱修复、页签（TagsView）支持关闭指定标签，菜单名称悬停提示。</li>
                <li>交互细节：导出遮罩层、表单拖拽排序、小屏幕适配，修复内链页面参数丢失与标签页刷新问题。</li>
                <li>修复 SQL 注入、XSS、反序列化漏洞，移除高危依赖（如 commons-collections 3.2.1），升级 log4j2/Spring Security。</li>
                <li>兼容 IE 浏览器提示、Weblogic 环境、iOS 时间格式，前端依赖适配 Node 18+，降级 jsencrypt 兼容 IE。</li>
                <li>支持多文件批量上传、富文本文件大小限制，修复文件名特殊字符下载与图片透明色显示问题。</li>
                <li>通用工具：数据脱敏注解、自定义 XSS 校验、国际化配置、密码强度验证，优化金额大写转换精度。</li>
                <li>统一组件版本（如 Element UI 2.15.x），修复样式冲突（如 El-Tag 动画、DictTag 显示），提升组件稳定性。</li>
              </ol>
            </el-collapse-item>
          </el-collapse>
        </el-card>
      </el-col>

    </el-row>
  </div>
</template>

<script setup name="Index">
const version = ref('3.8.9')

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

