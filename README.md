
<h1><a href="https://mizuyang.github.io/alley-dessert/#/">小巷弄甜點電商(Vue)作品連結</a></h1>
<h2><a href="https://whimsical.com/vue-CJV2RXJ2QmzUewz4bvR1dU">專案結構 </a></h2>
<h2><a href="https://equatorial-alloy-23b.notion.site/Vue-c56d16d8c5584847893e2733bb15e89c">頁面介紹、開發紀錄</a></h2>

<hr />

<article>
  <header>
    <h3>前言</h3>
    <p>
      這個專案是我人生第一次獨自完成一個專案，我在裡面做了非常多的嘗試，也碰到了許多困難，<br />
      不論是專案結構規劃、版型、套件使用、CSS 動畫、Vue Watch...等等。<br />
      但在我克服這些難題後，我才發現自己在實做中也成長不少，同時也覺得在開發的過程中是非常興奮、愉快的，<br />
      雖然很多未知的東西尚未接觸過，但在查找資料、了解它、實做後直到完成它的過程是非常有成就感的！<br />
      在自己獨自完成專案後，才了解工程師的世界裡，沒有一件事情是簡單的，所以必須非常努力，才能看起來豪不費力。<br />
    </p>
    <h3>網站使用技術</h3>
    <ul>
      <li>Vue3  開發專案</li>
      <li>使用 Vue-Router 建構路由 ( SPA )</li>
      <li>components 元件拆分管理</li>
      <li>使用 mixins 拆分元件共用部分出來</li>
      <li>AJAX / JSON 串接 RESTful API</li>
      <li>ESLint 管控程式品質(standard 風格)</li>
      <li>Bootstrap 5 整合 SCSS 開發</li>
      <li>使用 RWD 響應式網頁設計</li>
      <li>localStorage 開發收藏功能</li>
      <li>GitHub Pages 部署靜態網頁</li>
      <li>Swiper 輪播</li>
      <li>Vee-Validate 表單驗證</li>
      <li>AOS 滾動視差</li>
    </ul>
  </header>
  <h3>產品頁面</h3>
  <ul>
    <li>點擊愛心將產品加入收藏、移除收藏 (已收藏產品有自己獨立的頁面)</li>
    <li>點擊類別可做篩選 (filter)</li>
    <li>可透過部分關鍵字搜尋產品名稱</li>
    <li>點擊產品卡片可進入單一產品頁面 ($router.push)</li>
    <li>加入購物車功能</li>
  </ul>
  <img src="https://github.com/MizuYang/alley-dessert/blob/main/src/assets/imageUrl/README/%E7%94%A2%E5%93%81.png?raw=true" alt="產品頁面" height="700" width="900">
  <br />
  <h3>單一產品頁面</h3>
  <ul>
    <li>可選擇購買數量並將產品加入購物車</li>
    <li>可返回前一個頁面繼續購買 ($router.back)</li>
    <li>下方 Swiper 輪播，推薦其他產品 (當前產品不會重複顯示, filter)</li>
  </ul>
  <img src="https://github.com/MizuYang/alley-dessert/blob/main/src/assets/imageUrl/README/%E5%96%AE%E4%B8%80%E7%94%A2%E5%93%81.png?raw=true" alt="單一產品頁面" height="700" width="900">
  <br />
  <h3>購物車頁面</h3>
  <ul>
    <li>購物車沒商品時，會有引導客人前往購買的提示 (v-if 判斷購物車有無產品)</li>
    <li>下方也有產品輪播，持續推薦更多的產品刺激購買</li>
    <li>購物車產品可增加、減少數量</li>
    <li>可以勾選刪除、單一刪除、全部刪除</li>
    <li>在不同的結帳環節，購物流程的顏色會跟著變動 (watch 監聽)</li>
    <li>點選訂單編號即可複製編號碼</li>
    <li>完成訂單頁面，點擊訂單查詢就會直接跳轉到訂單查詢頁面，<br />
      並直接幫用戶貼上他的訂單編號，並且直接查詢結果供使用者查看。</li>
  </ul>
  <img src="https://github.com/MizuYang/alley-dessert/blob/main/src/assets/imageUrl/README/%E8%B3%BC%E7%89%A9%E8%BB%8A.png?raw=true" alt="購物車頁面" height="850" width="1000">
  <img src="https://github.com/MizuYang/alley-dessert/blob/main/src/assets/imageUrl/README/%E8%B3%BC%E7%89%A9%E8%BB%8A-%E6%89%8B%E6%A9%9F.png?raw=true" alt="購物車頁面" height="550" width="250">
  <br />
  <h3>查詢訂單頁面</h3>
  <ul>
    <li>使用者沒輸入訂單編號、訂單編號低於20碼會讓送出按鈕：顯示紅色、並且無法點擊，disabled狀態( :class )</li>
    <li>如果訂單碼有20碼，即解除 disabled 狀態，按鈕呈現綠色、游標指向為手指圖示</li>
    <li>查詢失敗會提示用戶，可能編號錯誤了，並清空查詢欄位的值</li>
    <li>查詢訂單會以綠色和紅色區分 已付款、未付款</li>
    <li>如果是未付款訂單，會出現按鈕讓用戶點擊了可以前往付款頁面</li>
  </ul>
  <img src="https://github.com/MizuYang/alley-dessert/blob/main/src/assets/imageUrl/README/%E6%9F%A5%E8%A9%A2%E8%A8%82%E5%96%AE.png?raw=true" alt="查詢訂單頁面" height="500" width="800">
  <br />
  <h3>主頁面</h3>
  <img src="https://github.com/MizuYang/alley-dessert/blob/main/src/assets/imageUrl/README/%E4%B8%BB%E9%A0%81-1.png?raw=true" alt="主頁面" height="400" width="1000">
  <img src="https://github.com/MizuYang/alley-dessert/blob/main/src/assets/imageUrl/README/%E4%B8%BB%E9%A0%81-2.png?raw=true" alt="主頁面" height="1300" width="1000">
  <img src="https://github.com/MizuYang/alley-dessert/blob/main/src/assets/imageUrl/README/%E4%B8%BB%E9%A0%81-3.png?raw=true" alt="主頁面" height="500" width="1000">
  <img src="https://github.com/MizuYang/alley-dessert/blob/main/src/assets/imageUrl/README/%E4%B8%BB%E9%A0%81-4.png?raw=true" alt="主頁面" height="500" width="1000">
  <img src="https://github.com/MizuYang/alley-dessert/blob/main/src/assets/imageUrl/README/%E4%B8%BB%E9%A0%81-5.png?raw=true" alt="主頁面" height="150" width="1000">

<hr />
<h3>專案發想</h3>
<details>
  <summary><h3>初期列點</h3></summary>

  - [x]  最終作業要註冊新的 path
      - [x]  記得把 path 保管好
  - [x]  規劃前、後台路由結構
      - [x]  確定前後台會有的頁面，繪圖
  - [x]  每個結構分頁命名，定義路由 path
  - [x]  確定版型
      - [x]  專案主題色調
  - [x]  架 Vue cli 專案
      - [x]  設定環境變數
      - [x]  新增 **`vue.config.js`** 更改路徑
      - [x]  測試上傳 github
  - [x]  建立環境
      - [x]  安裝 Bootstrap
          - [x]  匯入
      - [x]  安裝 Bootstrap icons
          - [x]  匯入+測試圖片顯示
      - [x]  安裝 Axios
          - [x]  匯入
      - [x]  安裝 表單驗證
          - [x]  匯入+測試
      - [x]  安裝 mitt
          - [x]  新增 `utils` 資料夾，並加入 `emitter.js`
      - [x]  全站設定
          - [x]  修改 Bootstrap 變數 (修改變數，註解時使用 `//*` ，之後回來找就很容易)
              - [x]  在 `assets` 中建立 `stylesheets` 資料夾，用來存放樣式，並建立 `all.scss` 檔案
                  - [x]  匯入 Bootstrap 和自己客製化的 `.scss` 到 `all.scss`
              - [x]  `stylesheets` 中開一個 `helpers` 資料夾用來存放變數
                  - [x]  將`node_modules` 裡的 `_variables.scss` 複製到 `helpers` 資料夾
              - [x]  在 **`App.vue`** 匯入`all.scss`
          - [x]  字體設定 'Microsoft JhengHei’ 微軟正黑體
  - [x]  建立分頁、檔案，使用資料夾管理
  - [x]  建立路由表，測試每個網頁能正常開啟
      - [x]  前台
      - [x]  後台
  - [x]  建立 NavBar，並加入對應 `router-link`
  - [x]  製作 LOGO
</details>

<details>

  <summary><h3>中期製作</h3></summary>

  ### 前台設定

  - [x]  **製作主頁面**
      - [x]  輪播功能
  - [x]  layout
      - [x]  NavBar
          - [x]  額外製作透明效果
      - [x]  Footer
  - [x]  **產品頁面**
      - [x]  產品可以點擊愛心，加入收藏，加入購物車按鈕
      - [x]  加上分頁元件
      - [x]  滑鼠 hover 圖片放大效果
      - [x]  創建產品資料夾，規劃每個產品獨立一個資料夾
      - [x]  尋找產品圖片素材 ( 圖片大小、色調、角度)
      - [x]  產品內容發想放在每個產品的獨立資料夾 (名稱、分類、描述、價格、推薦度)
          - [x]  分類：蛋糕、布丁、優格、泡芙、舒芙蕾、聖代
      - [x]  價格低到高、推薦度高到低、預設排序
      - [x]  篩選分類按鈕、商品名稱搜尋欄位  //嘗試做了將近三小時，失敗告終，時間壓力暫時先放著
      - [x]  用 v-if 判斷該產品是否已收藏（實心、空心愛心） ~~//後來做得有點混亂後續要在整理複習~~
      - [ ]  點圖片查看更多時，判斷是從**產品頁面**過去產品單一頁面，v-if 顯示**產品頁面**的麵包屑
          - [ ]  或定義一個值，點圖片時將該值=收藏，並 `props` 傳到單一產品頁面，給他v-if判斷顯示哪個麵包屑
  - [x]  **常見問題 頁面**
  - [x]  **關於我們 頁面**
  - [x]  **聯絡我們 頁面**
  - [x]  **訂單查詢頁面(要加分頁)**
  - [x]  結帳流程製作，確認購物車>訂購資訊>確認結帳>訂購成功
  - [x]  **收藏產品頁面**
      - [ ]  點圖片查看更多時，判斷是從**收藏頁面**過去產品單一頁面，v-if 顯示**收藏頁面**的麵包屑
          - [ ]  或定義一個值，點圖片時將該值=收藏，並props傳到單一產品頁面，給他v-if判斷顯示哪個麵包屑
      - [x]  增加 localStorage 功能
      - [x]  用 v-if 判斷該產品是否已收藏（實心愛心）
      
        ### 
        

    - [x]  關鍵字搜尋
    
  ### 後台設定

  - [x]  新增後台入口 ( `router-link` )
  - [x]  後台登入頁面
  - [x]  後台主頁面，登入驗證
  - [x]  `if(token),check=true`，但沒有登入的話，`check=false`(預設是false)，
      - [x]  後台主頁面 `router-view v-if=”check”`

</details>
<details>

  <summary><h3>後期優化</h3></summary>

  - [x]  點擊LOGO會滾動到最畫面上面，搜尋 vue3 router >****滾動設置 scrollBehavior****
  - [x]  滾動視差
  - [x]  加上吐司邊視窗
  - [ ]  加上麵包屑
  - [x]  加上 loading 效果，全螢幕、單一物件 //有更換圖示
  - [x]  按鈕增加 disabled 效果，防止多次點擊
  - [x]  HTML 標籤增加 title 屬性，讓使用者體驗更好
  - [x]  所有圖片補上 alt 網頁親和力
  - [ ]  下拉選單 (Dropdowns) ，點購物車，會有 table
  - [x]  千分號
  - [x]  文字截斷
  - [x]  為按鈕加上 hover、active 效果
  - [x]  404 導向
  - [x]  [變更游標 cursor](https://www.google.com/search?q=CSS+%E6%B8%B8%E6%A8%99+%E8%AE%8A%E6%9B%B4&rlz=1C1CHBF_zh-TWTW975TW975&oq=CSS+%E6%B8%B8%E6%A8%99+%E8%AE%8A%E6%9B%B4&aqs=chrome..69i57j0i546l3.7847j0j15&sourceid=chrome&ie=UTF-8)
      - [x]  按鈕 disabled 時，游標過去會是禁止圖案
  - [ ]  增加一個輸入管理者密碼的欄位，如果密碼對了才可以刪後台產品
      - [ ]  新增 .env.local 檔案，VUE_APP_PASSWORD=密碼
      - [ ]  點擊新增、編輯、刪除時，先判斷
      - [ ]  if (VUE_APP_PASSWORD === 管理者密碼的欄位){ 這裡才跑API流程 }
      
  - [x]  更新 `README.md`
  <details>
</article>
