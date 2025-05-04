<template>
  <div class="index">
    <div class="container">

      <div class="row">
        <div class="col-md-10 col-md-offset-1">
          <div class="title text-center">
            <h1>ohya(當前進度 git actions 完成, 下一步增加個人project)</h1>
            <!-- Will put my linkedin profile URL if needed-->
            <h4><a href="https://github.com/a050949359">github</a></h4>
            <hr />

            <el-space :size="32" direction="horizontal" alignment="center" wrap>
              <i class="devicon-linux-plain"></i>
              <i class="devicon-vuejs-plain"></i>
              <i class="devicon-php-plain"></i>
              <i class="devicon-codeigniter-plain"></i>
              <i class="devicon-laravel-original"></i>
              <i class="devicon-python-plain"></i>
              <i class="devicon-flask-original"></i>
              <i class="devicon-mariadb-original"></i>
              <i class="devicon-influxdb-original"></i>
            </el-space>
          </div>

          <!-- summary section -->
          <div class="summary">
            <h2 class="summary-title">Summary</h2>
            <hr />
            <p class="summary-contain">具備約 五年半軟體開發經驗，曾擔任全端與 iOS 工程師。熟悉 Perl、PHP、Python、Objective-C 等語言，並具備 Web 前後端開發與 API 串接實務經驗。熟練使用 Docker 建立開發環境，並撰寫部署與維運文件。近期因成功承接並完成專案，獲得肯定。</p>
            <ul class="el-list">
              <li>技能：Perl、PHP (CodeIgniter)、Python(flask)、Go（Gin）、Rust、Vue.js、Docker、Docker-compose、SQL</li>
              <li>開發經驗：iOS App 開發(obj-c)、API 設計（REST & SOAP）、XML/JSON 處理、前後端整合、系統維護與升級</li>
              <li>學習與創新：依個人喜好自學 Go、Rust、AI 技術中</li>
            </ul>
          </div>

          <div class="work-experience">
            <h2 class="work-experience-title">工作經歷</h2>
            <hr />
            <ul class="el-list">
              <li>全端工程師 愛訊電網科技股份有限公司（電信相關業 1~30人）</li>
              <li>iOS軟體工程師 PhotoFast（資料儲存媒體製造及複製業 30~100人）</li>
              <li>開發人員 智同科技（消費性電子產品製造業 100~500人）</li>
            </ul>
          </div>

          <div class="learning-experience">
            <h2 class="learning-experience-title">學習經歷</h2>
            <hr />
            <ul class="el-list">
              <li>輔仁大學 電子工程系</li>
              <li><a href="https://www.tibame.com/certificatepage/eyJjZXJ0aWZpY2F0ZVVzZXJJRCI6IldXMjVUQkFaMDI4NTAiLCJjb3Vyc2VVaWQiOjIwMH0%3D">道德駭客實務入門及CEH認證班</a></li>
              <li>華岡興業基金會x NTC.im人 大數據課程</li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
</script>

<style scoped>
@import "devicon/devicon.min.css";

.index {
  width: 100%;
  height: 100%;
}

.container {
  width: 100%;
  height: 100%;
  box-sizing: border-box;
 
  text-align: center;
  color: white;
  background: url("../assets/background.png") #999;
  display: flex;
  flex-direction: column;
  /* justify-content: center; */
  align-items: center;
  text-align: center;
  background-size: 100% 100%;
}

body {
  font-family: "Century Gothic", 'Lato', sans-serif;
}

a {
  text-decoration: none;
}

ul {
  list-style-type: none;
  padding: 0;
}

body {
  background: #1B1B25;
  color: #fff;
  font-family: 'Josefin Sans', sans-serif;
}

.separator {
  width: 30%;
}

.title {
  font-size: 32px;
  margin-top: 40px;
  margin-bottom: 10px;
}

.title a {
  color: #DB4D57;
}

.title a:hover {
  text-decoration: none;
  font-weight: bold;
}

.title hr {
  width: 75%;
}

.summary hr, .work-experience hr, .learning-experience hr {
  margin: 20px 0px;
}

div .summary, div .work-experience, div .learning-experience {
  padding: 20px 15% 0px 15%;
}

.summary p {
  font-size: 1.1rem;
  letter-spacing: .1rem;
}

.summary-contain {
  padding-bottom: 10px;
}

.el-list {
  text-align: left;
  
}
.el-list li{
  padding-bottom: 10px;
}

.container {
  text-align: center;
  width: 100%;
  margin: 0 auto;

}

.row {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.col-md-3 {
  padding: 5px;
  text-align: center;
}

.el-space i {
  font-size: 40px;
}

.work-experience {
  padding: 20px;
}

h2 {
  font-size: 40px;
  text-align: center;
}

</style>