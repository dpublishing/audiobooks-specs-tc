台灣數位出版聯盟有聲書範本 2024

本專案是承繼前一版的[「台灣數位出版聯盟有聲書範本」](https://github.com/dpublishing/audiobooks-samples)，並針對上次推出範本後，出版品同步媒體社群小組所推出的規格草稿，重新製作新的的有聲書範本。範本所使用的音檔及內文是授權自台灣小說家劉芷妤的短篇小說集《女神自助餐》中的〈同學會〉。

範本內容符合 W3C Audiobooks 有聲書規格，並參考[W3C出版品宣告](https://www.w3.org/TR/pub-manifest/)製作五種不同參考範例。

	請注意：此次版本所使用的同步旁白規格 SyncMedia，為參考出版品同步媒體社群小組制定中的草稿，並非 W3C 的推薦標準。

---

## 範本說明（此處說明內容主要沿襲自 2020 年版的[「台灣數位出版聯盟有聲書範本」](https://github.com/dpublishing/audiobooks-samples)）

### 範例一：具備所有元素的有聲書範本（Case 1）

- 內容包含：
	- 出版品宣告：`publication.json`
	- 主要進入頁面（內嵌目錄）：`index.html`
	- 獨立目錄：`toc.html`
	- 封面：`cover.jpg`
	- 對應時間：`sync/reunion.smil`
	- 文字內容：`html/reunion.html`
	- 音檔：`reunion.mp3`

- 說明：
在主要進入頁面（Primary Entry Page）

在主要進入頁面(Primary Entry Page)中，以`link`元素包含對出版品宣告(Publication Manifest) `publication.json`的參照。然後在出版品宣告中提供閱讀順序(readingOrder)與音檔位置等資訊，在閱讀順序中使用alternate指定對應同步朗讀時間的`reunion.smil`檔案。

在`reunion.smil`中的`text`指定標註同步ID的`html/forward.html`檔案。

封面圖片、主要進入頁面、獨立目錄與文字內容另宣告在出版品宣告的資源（resources）中。

### 範例二：使用獨立目錄的有聲書範本（Case 2）

- 說明：
與 Case 1大致相同，不同之處是在主要進入頁面中不提供嵌入目錄，而改連結到獨立目錄。處理方式為在`resources`中，將`”rel": "contents"`指定到獨立目錄，而非Case 1的主要進入頁面。

### 範例三：使用獨立目錄且出版品宣告嵌入在主要進入頁面中的有聲書範例（Case 3）

- 說明：
- 與 Case 2 大致相同，不同之處是參考[W3C出版品宣告](https://www.w3.org/TR/pub-manifest/)，將出版品宣告嵌入在主要進入頁面之中。處理方式是在將原先放置在`publication.json`的資訊，放入`index.html`的`head`的`script`標籤之中。

### 範例四：簡單有聲書範本（Case 4）

- 內容包含：
	- 出版品宣告：`publication.json`
	- 獨立目錄：`toc.html`
	- 封面：`cover.jpg`
	- 音檔：`reunion.mp3`
- 說明：

相較於Case 1—3，此範例較偏向於一般包裝有聲書作為交換使用。音檔不位於遠端伺服器，而位於本地端，同時也沒有主要進入頁面，程式應該直接搜尋出版品宣告進行處理。也不包含同步旁白資源。

### 範例五：最小限度的有聲書範本（Case 5）

- 內容包含：
	- 出版品宣告：`publication.json`
	- 封面：`cover.jpg`
	- 音檔：`reunion.mp3`
- 說明：

最小限度的有聲書範本，連獨立目錄也不具備。僅提供出版品宣告與音檔，甚至可以進一步刪除封面圖片。