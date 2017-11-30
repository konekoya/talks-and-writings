
# 元素面版 - 動態編輯 CSS
我們用了兩天的時間把如何透過元素面版來動態編輯文件物件模型 (DOM) 講完了，今天我們要一起看的功能是動態編輯元素的樣式。樣式控制台 (Styles pane) 的位置就在元素面版中，通常它會出現在文件物件模型樹區塊 (DOM tree)　的下面，但是如果你的螢幕空間夠大的話，它會改變排版的方式，成為與文件模型樹區塊併排。

> 再次提醒大家，我們在元素面版裡的編輯都是暫存在記憶體裡，當你重新整理頁面後這些內容都會消失

## 檢查元素樣式
要開始查看一個元素的樣式很簡單，我想可能有些人在前面操作編輯文件物件模型的時候就有注意到了。當你[選擇一個元素](https://github.com/konekoya/talks/blob/master/intro-to-chrome-devtools-triathlon/day-7.md#%E5%B0%8B%E6%89%BE%E5%85%83%E7%B4%A0)之後，這時在樣式控制台裡就可以看到現在所選擇元素的所有樣式。我們來介紹一下這個樣式控制台的內容：

- 樣式排序：首先，所有的樣式排序方式是按樣式繼承的方式來排的，最靠近螢幕方向的這樣式是最底層的樣式 (像是來自 html 或是 body 的樣式)，越往上就是靠近目前這個元素的父元素，一直到最後就是元素自己本身的樣式。然後最後一個是 `element.style {}` 這個表示的是這一個元素的行內樣式 (Inline styles)。

- 有衝突的樣式：在看過幾個元素的樣式後，你一定會看到一些元素的某個樣式定義是被劃掉的，這是代表這個樣式的定義與其他的樣式定義有衝突，而最後因為這個定義的權重 (Specificity) 比較低，所以就沒有套用到這個元素上。
> 如果你不知道 CSS 權重是什麼，強烈建議你一定要了解一下，這是 CSS 的核心概念之一，MDN上有一篇說明[權重的文件](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Specificity)

- 樣式來源：所有的樣式都會有來源，其中最明顯的就是來自於開發者也就是你所寫的樣式表，這個來源的資訊會放在每一段樣式的右上角。當你點下來源後，開發者工具會帶你到原始碼面版 (Sources panel) 裡的樣式表檔案裡，你可以在這裡面編輯及更新你的樣式表，這個我們之後介紹原始碼面版後會再介紹。