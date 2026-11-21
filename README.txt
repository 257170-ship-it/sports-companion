運動夥伴養成｜75 吋電視網頁圖層

scene/
  meadow.webp           1920 × 1080 草地背景
  title.png             透明標題牌「運動夥伴養成」

characters/
  hedgehog-idle.png     刺蝟站姿
  hedgehog-jump.png     刺蝟跳繩動作圖
  otter-idle.png        水獺站姿
  otter-throw.png       水獺擲飛盤動作圖
  rabbit-idle.png       兔子站姿
  fox-idle.png          狐狸站姿
  turtle-idle.png       烏龜站姿
  duckling-idle.png     小鴨站姿
  red-panda-idle.png    小貓熊站姿

icons/
  jump-rope.png         跳繩圖示
  flying-disc.png       飛盤圖示
  milestone-earned.png  已達標橘色勾勾
  milestone-pending.png 未達標灰色空心圓
  reward-star.png       星星獎勵
  reward-headband.png   運動頭帶獎勵圖示

網頁疊放順序
1. 草地背景置底，使用 background-size: cover。
2. 奶油色卡片、珊瑚色名牌及數字資料列由 CSS 繪製。
3. 角色圖置於卡片圖案區。使用 object-fit: contain，底部對齊。
4. 班級、姓名及累計次數由網頁填入。每個項目呈現三枚達標圖示。
5. 頁首顯示透明標題，底部可顯示兩項門檻。

門檻與顯示
跳繩：3,000／6,000／9,000 次。
飛盤：600／800／1,000 次。
從最低門檻往上逐一判斷，累計次數大於或等於門檻時，顯示橘色勾勾。
角色可依班級人數配置。版面建議為 2 人左右大卡、3～4 人雙欄、5～7 人橫列。

解鎖素材
跳繩達標解鎖動作，七隻夥伴都可使用相同動畫。
  3,000 次　小跳　　motion/landing-puffs.png　　data-motion="hop"
  6,000 次　轉圈跳　motion/spin-trail.png　　　 data-motion="spin"
  9,000 次　三連跳　motion/triple-hop-stars.png data-motion="triple"

飛盤達標解鎖配件。三個配件都是單獨的透明圖層，適合放在角色旁的收藏欄。
  600 次　運動頭帶　accessories/headband.png
  800 次　運動領巾　accessories/bandana.png
1,000 次　星星獎牌　accessories/medal.png

例如跳繩 6,700 次、飛盤 820 次：可使用小跳、轉圈跳，收藏頭帶和領巾。
既有的刺蝟跳繩與水獺擲飛盤插圖可作為展示圖。使用配件旁列方案時，可直接
顯示三個 PNG。若做成穿戴版，需依角色另設定頭部與脖子的定位。

動畫接法
在網頁載入 motion/companion-motion.css。將 data-motion 加到角色容器時會
播放一次。播完可移除該屬性，以便下一次重新加上並播放。沒有觸發時只顯示站姿。
以下是假設 HTML 就在素材根目錄的最小片段。實際應依資料判斷動作是否已解鎖。

<link rel="stylesheet" href="motion/companion-motion.css">
<div class="sports-companion" data-motion="hop">
  <img class="sports-companion__figure" src="characters/rabbit-idle.png" alt="兔子夥伴">
</div>
