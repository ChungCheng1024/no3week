# URBNSTEP 品牌故事切版介紹

以下將以 **story.html** 與 `css/all.css` 為例，示範如何從零開始完成品牌故事頁的 RWD 版型。文章會依照實際切版流程拆解，讓初學者也能快速了解每一步的目的。

## 1. 前置準備

1. 將 `css` 資料夾與 `story.html` 放在同一層目錄。
2. 在 `<head>` 區塊引入 `all.css`：
   ```html
   <link rel="stylesheet" href="./css/all.css" />
   ```
3. HTML 結構從一個 `.container` 開始，這個區塊會限制寬度並置中顯示內容。

## 2. 自製網格系統

`all.css` 內建簡易的 12 欄網格，用來排版主要區塊。使用方式如下：

```html
<div class="container">
  <div class="row">
    <div class="col-8 col-md-4">主要內容</div>
    <div class="col-4 col-md-4">側邊欄</div>
  </div>
</div>
```

- `.row` 會套用 flex 並處理負邊距。
- `.col-?` 代表桌機寬度，例如 `.col-8` 佔八欄 (約 66%)。
- `.col-md-?` 在螢幕寬度 768px 以下生效，可改為單欄排列。
- 常見的間距工具類別如 `.mb-8`、`.py-6` 可直接在標籤上使用。

透過這些公用類別，只需撰寫少量 CSS 即可完成彈性佈局。

## 3. 導覽列與主視覺

1. 導覽列 `<nav>` 置於 `.container` 中，左右以 flex 排列 Logo 與選單。
2. 手機版利用 `.d-sm-none` 與 `.d-sm-block` 隱藏或顯示項目。
3. 主視覺區 `.brand-title` 使用 `background-image` 放置大圖，並在媒體查詢中換成 `hero-sm.png`。

## 4. 內文排版

故事內容採三欄式設計，做法如下：

1. 文字、圖片與補充資訊皆放在 `.row` 內的不同 `.col-*` 區塊。
2. 在桌機版使用 `.col-8`、`.col-10` 等寬度，手機版則加上 `.col-md-4` 讓各欄滿版堆疊。
3. `.section-line`、`.history-list` 等類別提供底線或邊框效果，搭配 `.mb-*`、`.pb-*` 控制留白。

## 5. 亮點與頁尾

- 會員招募區塊使用 `.bg-hightlight` 加上 `.bg-primary-200` 形成漸層效果。
- 按鈕沿用 `.btn` 系列樣式，可快速變換顏色或大小。
- Footer 同樣以 `.container` 包覆，並在 576px 以下使用 `.d-sm-block` 垂直排列選單。

## 6. 響應式細節

`all.css` 分別針對 768px 與 576px 撰寫 `@media` 斷點，調整文字大小、欄位寬度與顯示狀態。常用的類別有：

- `.h3-md`, `.h4-md`：在行動版縮小標題字級。
- `.d-md-none`, `.d-sm-none`：依螢幕寬度隱藏元素。
- `.text-align-md-start`：手機版改為靠左對齊。

掌握以上規則即可自由組合版面，快速完成具備 RWD 的品牌故事頁。

ps:參考助教直播與同學的https://github.com/zuien-kk/2025-week3 utility class命名法 並了解格線系統 
