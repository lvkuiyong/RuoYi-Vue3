<template>
  <div class="app-container home">
    <el-row :gutter="20">
      <el-col :sm="24" :lg="24" style="padding-left: 20px">
        <div class="feature-card">
          <h2 class="section-title">系统功能概览</h2>
          <div class="feature-list">
            <!-- 部门管理 -->
            <div class="feature-item">
              <div class="feature-icon">
                <svg class="svg-icon" viewBox="0 0 24 24">
                  <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm0 16H5V5h14v14z"/>
                  <path d="M7 12h2v5H7zm4-7h2v12h-2zm4 5h2v7h-2z"/>
                </svg>
              </div>
              <div class="feature-content">
                <h3>部门管理</h3>
                <p>配置系统组织机构（公司、部门、小组），树结构展现支持数据权限</p>
              </div>
            </div>
            
            <!-- 用户管理 -->
            <div class="feature-item">
              <div class="feature-icon">
                <svg class="svg-icon" viewBox="0 0 24 24">
                  <path d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0 2c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"/>
                </svg>
              </div>
              <div class="feature-content">
                <h3>用户管理</h3>
                <p>用户是系统操作者，该功能主要完成系统用户配置</p>
              </div>
            </div>
            
            <!-- 岗位管理 -->
            <div class="feature-item">
              <div class="feature-icon">
                <svg class="svg-icon" viewBox="0 0 24 24">
                  <path d="M20 6h-4V4c0-1.11-.89-2-2-2h-4c-1.11 0-2 .89-2 2v2H4c-1.11 0-2 .89-2 2v11c0 1.11.89 2 2 2h16c1.11 0 2-.89 2-2V8c0-1.11-.89-2-2-2zm-6 0h-4V4h4v2z"/>
                </svg>
              </div>
              <div class="feature-content">
                <h3>岗位管理</h3>
                <p>配置系统用户所属担任职务</p>
              </div>
            </div>
            
            <!-- 角色管理 -->
            <div class="feature-item">
              <div class="feature-icon">
                <svg class="svg-icon" viewBox="0 0 24 24">
                  <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8zm-1-13h2v6h-2zm0 8h2v2h-2z"/>
                </svg>
              </div>
              <div class="feature-content">
                <h3>角色管理</h3>
                <p>角色菜单权限分配、设置角色按机构进行数据范围权限划分</p>
              </div>
            </div>

            <!-- 通知公告 -->
            <div class="feature-item">
              <div class="feature-icon">
                <svg class="svg-icon" viewBox="0 0 24 24">
                  <path d="M12 22c1.1 0 2-.9 2-2h-4c0 1.1.9 2 2 2zm6-6v-5c0-3.07-1.63-5.64-4.5-6.32V4c0-.83-.67-1.5-1.5-1.5s-1.5.67-1.5 1.5v.68C7.64 5.36 6 7.92 6 11v5l-2 2v1h16v-1l-2-2z"/>
                </svg>
              </div>
              <div class="feature-content">
                <h3>通知公告</h3>
                <p>系统通知公告信息发布维护</p>
              </div>
            </div>
            
            <!-- 登录日志 -->
            <div class="feature-item">
              <div class="feature-icon">
                <svg class="svg-icon" viewBox="0 0 24 24">
                  <path d="M19 3h-4.18C14.4 1.84 13.3 1 12 1c-1.3 0-2.4.84-2.82 2H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm-7 0c.55 0 1 .45 1 1s-.45 1-1 1-1-.45-1-1 .45-1 1-1zm2 14H7v-2h7v2zm3-4H7v-2h10v2zm0-4H7V7h10v2z"/>
                </svg>
              </div>
              <div class="feature-content">
                <h3>登录日志</h3>
                <p>系统登录日志记录查询包含登录异常</p>
              </div>
            </div>
            
            <!-- 在线用户 -->
            <div class="feature-item">
              <div class="feature-icon">
                <svg class="svg-icon" viewBox="0 0 24 24">
                  <path d="M16 11c1.66 0 3-1.34 3-3s-1.34-3-3-3-3 1.34-3 3 1.34 3 3 3zm-8 0c1.66 0 3-1.34 3-3s-1.34-3-3-3-3 1.34-3 3 1.34 3 3 3zm0 2c-2.33 0-7 1.17-7 3.5V18c0 .55.45 1 1 1h12c.55 0 1-.45 1-1v-1.5c0-2.33-4.67-3.5-7-3.5zm8 0c-.29 0-.62.02-.97.05.02.01.03.03.04.04 1.14.83 1.93 1.94 1.93 3.41V18c0 .35-.07.69-.18 1H22c.55 0 1-.45 1-1v-1.5c0-2.33-4.67-3.5-7-3.5z"/>
                </svg>
              </div>
              <div class="feature-content">
                <h3>在线用户</h3>
                <p>当前系统中活跃用户状态监控</p>
              </div>
            </div>
          </div>
        </div>
      </el-col>
    </el-row>
    <el-divider />
  </div>
</template>

<script setup>
const version = ref('3.8.0')

function goTarget(url) {
  window.open(url, '__blank')
}
</script>

<style scoped lang="scss">
.home {
  .section-title {
    color: #303133;
    font-size: 20px;
    font-weight: 500;
    margin-bottom: 20px;
    position: relative;
    padding-bottom: 10px;
    
    &::after {
      content: "";
      position: absolute;
      bottom: 0;
      left: 0;
      width: 40px;
      height: 2px;
      background: linear-gradient(90deg, #409EFF, #67C23A);
      border-radius: 2px;
    }
  }
  
  .feature-card {
    background: #fff;
    border-radius: 6px;
    padding: 20px;
    box-shadow: 0 1px 8px 0 rgba(0, 0, 0, 0.08);
    margin-bottom: 15px;
  }
  
  .feature-list {
    .feature-item {
      display: flex;
      align-items: flex-start;
      margin-bottom: 15px;
      padding-bottom: 15px;
      border-bottom: 1px dashed #EBEEF5;
      
      &:last-child {
        border-bottom: none;
        margin-bottom: 0;
        padding-bottom: 0;
      }
      
      .feature-icon {
        width: 32px;
        height: 32px;
        background: #f5f7fa;
        border-radius: 6px;
        display: flex;
        align-items: center;
        justify-content: center;
        margin-right: 12px;
        color: #606266;
        flex-shrink: 0;
        
        .svg-icon {
          width: 16px;
          height: 16px;
          fill: currentColor;
        }
      }
      
      .feature-content {
        flex: 1;
        
        h3 {
          margin: 0 0 4px 0;
          font-size: 14px;
          color: #303133;
          font-weight: 500;
        }
        
        p {
          margin: 0;
          font-size: 12px;
          color: #909399;
          line-height: 1.5;
        }
      }
    }
  }
  
  .el-divider {
    margin: 20px 0;
  }
  
  @media (max-width: 768px) {
    .feature-card {
      padding: 15px;
    }
    
    .feature-item {
      flex-direction: column;
      
      .feature-icon {
        margin-bottom: 8px;
        margin-right: 0;
      }
    }
  }
}
</style>