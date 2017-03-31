
Growth: 全棧增長工程師指南
===

這是一本不止於全棧工程師的學習手冊，它也包含了如何成為一個 Growth Hacker 的知識。

全棧工程師是未來
---

> 謹以此文獻給每一個為成為優秀全棧工程師奮鬥的人。

技術在過去的幾十年裡進步很快，也將在未來的幾十年裡發展得更快。今天技術的門檻下降得越來越快，原本需要一個團隊做出來的 Web 應用，現在只需要一兩個人就可以了。

同時，由於公司組織結構的變遷，以及到變化的適應度，也決定了賦予每個人的職責將會越來越多。儘管我們看到工廠化生產帶來的優勢，但是我們也看到了**精益思想**帶來的變革。正是這種變革讓越來越多的專家走向全棧，讓組織內部有更好的交流。

你還將看到專家和全棧的兩種不同的學習模式，以及全棧工程師的未來。

###技術的革新史

從開始的 CGI 到 MVC 模式，再到前後端分離的架構模式，都在不斷地降低技術的門檻。而這些門檻的降低，已經足以讓一兩個人來完成大部分的工作了。

####CGI

二十年前的網站以靜態的形式出現，這樣的網站並不需要太多的人去維護、管理。接著，人們發明了 CGI (通用閘道器介面，英語：Common Gateway Interface)來實現動態的網站。下圖是一個早期網站的架構圖：

![CGI 網站架構](assets/article/prelude/cgi-arch.gif)

當時這種網站的URL類似於：

```bash
https://www.phodal.com/cgi-bin/getblog
```

(PS：這個連結是為了講解而存在的，並沒有真實存在。)

使用者訪問上面的網頁的時候就會訪問，cgi-bin 的路徑下對應的 getblog 指令碼。你可以用 Shell 返回這個網頁：

```bash
#!/bin/sh
echo Content-type: text/plain
echo hello,world
```

Blabla，各種程式碼混亂地夾雜在一起。不得不說一句：這樣的程式碼在2012年，我也看了有一些。簡單地來說，這個時代的程式碼結構就是這樣的：

![CGI指令碼檔案 ](assets/article/prelude/cgi-script.png)

這簡直就是一場惡夢。不過，在今天好似那些 PHP 新手也是這樣寫程式碼的。

好了，這時候我們就可以討論討論 MVC 模式了。

####MVC架構

我有理由相信 Martin Fowler 的《企業應用架構模式》在當時一定非常受歡迎。程式碼從上面的耦合狀態變成了：

![MVC 架構](assets/article/prelude/caf_mvc_arch.png)

相似大家也已經對這樣的架構很熟悉了，我們就不多解釋了。如果你還不是非常瞭解的話，可以看看這本書後面的部分。

####後臺服務化與前端一致化架構

在今天看來，我們可以看到如下圖所示的架構：

![後臺服務化與前臺一致化架構](assets/article/prelude/oneui-serviceful-arch.png)

後臺在不知不覺中已經被服務化了，即只提供API介面和服務。前端在這時已經儘量地和 APP 端在結合，使得他們可以保持一致。

###軟體開發的核心難題：溝通

軟體開發在過去的幾十年裡都是大公司的專利，小公司根本沒有足夠的能力去做這樣的事。在計算機發明後的幾十年裡，開發軟體是大公司才能做得起的。一般的非技術公司無法定製自己的軟體系統，只能去購買現有的軟體。而隨著技術成本的下降，到了今天一般的小公司也可以僱傭一兩個人來做同樣的事。這樣的演進過程還真是有意思：

![開發演進](assets/article/prelude/develop-history.png)

在這其中的每一個過程實質上都是為了解決溝通的問題。從瀑布到敏捷是為了解決組織內溝通的問題，從敏捷到精益不僅僅優化了組織內的溝通問題，還強化了與外部的關係。換句話說，精益結合了一部分的網際網路思維。

####瀑布式

在最開始的時候，我們預先設計好我們的功能，然後編碼，在適當的時候釋出我們的軟體：

![預先式設計的瀑布流](assets/article/prelude/old-se.jpg)

然而這種開發方式很難應對市場的變化——當我們花費了幾年的時間開發出了一個軟體，而這個軟體是幾年前人們才需要的。同時，由於軟體開發本身的複雜度的限制，複製的系統在後期需要大量的系統整合工作。這樣的整合工作可能要花費上大量的時間——幾星期、幾個月。

![瀑布流的溝通模型](assets/article/prelude/waterfall-process.png)

當人們意識到這個問題的時候，開始改進工作流程。出現了敏捷軟體開發，這可以解釋為什麼產品經理會經常改需求。如果一個功能本身是沒必要出現的話，那麼為什麼要花功夫去開發。但是如果一個功能在設計的初期就沒有好好設計，那麼改需求也是必然的。

####敏捷式

現有的網際網路公司的工作流程和敏捷軟體開發在很多部分上是相似的，都有迭代、分析等等的過程：

![敏捷軟體開發](assets/article/prelude/scrum.png)

但是據我的所知：國內的多數網際網路公司是不寫測試的、沒有 Code Review 等等。當然，這也不是一篇關於如何實踐敏捷的文章。敏捷與瀑布式開發在很大的區別就是：溝通問題。傳統的軟體開發在調研完畢後就是分析、開發等等。而敏捷開發則會強調這個過程中的溝通問題：

![敏捷軟體開發的溝通模型](assets/article/prelude/scrum-communication.png)

在整個過程中都不斷地強調溝通問題，然而這時還存在一個問題：組織結構本身的問題。這樣的組織結構，如下圖所示：

![組織結構](assets/article/prelude/scrum-issues.png)

如果市場部門/產品經理沒有與研發團隊坐一起來分析問題，那麼問題就多了。當一個需求在實現的過程中遇到問題，到底是哪個部門的問題？

同樣的如果我們的研發部門是這樣子的結構：

![研發部門](assets/article/prelude/tech-org.png)

那麼在研發、上線的過程中仍然會遇到各種的溝通問題。

現在，讓我們回過頭來看看大公司的專家與小公司的全棧。

###大公司的專家與小公司的全棧

如果你經常看一些關於全棧和專家的技術文章的時候，你就會發現不同的人在強調不同的方向。大公司的文章喜歡強調成為某個領域的專家，小公司喜歡小而美的團隊——全棧工程師。

如我們所見的：大公司和小公司都在解決不同類型的問題。大公司要解決效能問題，小公司要活下去需要依賴於近乎全能的人。並且，大公司和小公司都在加班。如果從這種意義上來說，我們可以發現其實大公司是在剝削勞動力。

**專家**

我們所見到的那些關於技術人員應該成為專家的文章，多數是已經成為某個技術領域裡的專家寫的文章。並且我們可以發現很有意思的一點是：他們都是**管理者**。管理者出於招聘的動機，因此更需要細分領域的專家來幫助他們解決問題。

**全棧**

相似的，我們所看到的那些關於成為全棧工程師的文章，多數是初創公司的 CTO 寫的。而這些初創公司的 CTO 也多數是全棧工程師，他們需要招聘全棧工程師來幫助他們解決問題。

####兩種不同的學習模型

而不知你是否也注意到一點：專家們也在強調**“一專多長”**。因為單純依靠於一個領域的技術而存在的專家已經很少了，技術專家們不得不依據於公司的需求去開拓不同的領域。畢竟“公司是指全部資本由股東出資構成，以營利為目的而依法設立的一種企業組織形式；”，管理人們假設技術本身是相通的，既然你在技術領域裡有相當高的長板，那麼進入一個新的技術也不是一件難事。

作為一個技術人員，我們是這個領域中的某個子領域專家。而作為這樣一個專家，我們要擴充套件向另外一個領域的學習也不是一件很難的事。借鑑於我們先前的學習經驗，我們可以很快的掌握這個新子域的知識。如我們所見，我們可以很快地補齊圖中的短板：

![木桶](assets/article/prelude/bucket.jpg)

在近來的探索中發現有一點非常有意思：如果依賴於20/80法則的話，那麼成為專家和全棧的學習時間是相當的。在最開始的時候，我們要在我們的全棧工程和專家都在某個技術領域達到80分的水平。

那麼專家，還需要80%的時間去深入這個技術領域。而全棧工程師，則可以依賴於這80%的時候去開拓四個新的領域：

![全棧與專家學習時間](assets/article/prelude/expert-vs-fullstack.png)

儘管理論上是如此，但是專家存在跨領域的學習障礙——套用現有模式。而全棧也存在學習障礙——如何成為專家，但是懂得如何學習新的領域。

####解決問題的思路：不同的方式

有意思的是——成為專家還是成為全棧，取決於人的天性，這也是兩種不同的性格決定的。成為管理者還是技術人員看上去就像一種簡單的劃分，而在技術人員裡成為專家還是全棧就是另外一種劃分。這取決於人們對於一個問題的思考方式：這件事情是藉由外部來解決，還是由內部解決。下面這張圖剛好可以表達我的想法：

![內向與外向思維](assets/article/prelude/in-out-thinking.jpeg)

而這種思維依據於不同的事情可能會發生一些差異，但是總體上來說是相似的。當遇到一個需要創輪子的問題時，我們就會看到兩種不同的方式。

對於全棧工程師來說，他們喜歡依賴於外部的思維，用於產生顛覆式思維。如 AngularJS 這樣的框架便是例子，前端結合後端開發語言 Java 的思維而產生。而專家則依賴於內部的條件，創造出不一樣的適應式創新。如之前流行的 Backbone 框架，適應當時的情況而產生。

###全棧工程師的未來：無棧

全棧工程師本身不應該僅僅侷限於前端和後臺的開發，而可以嘗試去開拓更廣泛的領域——因為全棧本身是依賴於工程師本身的學習能力，正是這種優秀的學習能力可以讓他們接觸更廣泛的知識。

####全棧的短板

如果你也嘗試過面試過全棧工程師，你會怎麼去面試他們呢？把你知道的所有的不同領域的問題都拿出來問一遍。是的，這就是那些招聘全棧工程師的公司會問你的問題。

人們以為全棧工程師什麼都會，這是一個明顯的誤區——然而要改變這個誤區很難。最後，導致的結果是大家覺得全棧工程師的水平也就那樣。換句來說，人們根本不知道什麼是全棧工程師。在平時的工作裡，你的隊伍都知道你在不同領域有豐富的知識。而在那些不瞭解你的人的印象裡，就是猜測你什麼都會。

因此，這就會變成一個罵名，也是一個在目前看來很難改變的問題。在這方面只能儘可能地去了解一些通用的問題，並不能去了解所有的問題。在一次被面試全棧工程師的過程中，有一個面試官準備了幾個不同語言（JavaScript、Java、Python、Ruby)的問題來問我，我只想說 Ciao —— 義大利語：你好！

除了這個問題——人們不瞭解什麼是全棧工程師。還有一個問題，就是剛才我們說的成為專家的老大難問題。

####無棧

讓我毫不猶豫地選擇當全棧工程師有兩個原因：

1. 這個世界充滿了未解的迷，但是我只想解開我感興趣的部分。
2. 沒有探索，哪來的真愛？你都沒有探索過世界，你就說這是你最喜歡的領域。

當我第一次看到全棧工程師這個名字的時候，我發現我已然是一個全棧工程師。因為我的學習路線比較獨特：

 - 中小學，因為比賽，開始學習程式設計
 - 高中，因為興趣，開始學習作業系統核心設計以及遊戲程式設計
 - 大學，因為專業走向硬體的道路，因為生活拮据，用Web開發來賺錢
 - 工作：主要工作領域便是：Java後端、前後端分離、SPA前端，業餘還寫寫APP、遊戲、寫作

而在當時我對 SEO 非常感興趣，我發現這分析和 Marketing 似乎做得還可以。然後便往 Growth Hacking 發展了：

![Growth Hacking](assets/article/prelude/growth-hacking.jpg)

而這就是全棧學習帶來的優勢，學過的東西多，學習能力就變強。學習能力往上提的同時，你就更容易進入一個新的領域。

參考書籍

 - 《精益企業： 高效能組織如何規模化創新》
 - 《企業應用架構模式》
 - 《敏捷軟體開發》
 - 《技術的本質》



基礎知識篇
===

在我們第一次開始寫程式的時候，都是以 Hello World 開始的。或者：

```c
printf("hello,world");
```

又或許：

```javascript
alert('hello,world');
```

過去的十幾年裡，試過用二十幾種不同的語言，每個都是以 hello,world 作為開頭。在一些特定的軟體，如 Nginx，則是 **It Works**。

這是一個很長的故事，這個程式最早出現於1972年，由貝爾實驗室成員布萊恩·柯林漢撰寫的內部技術檔案《A Tutorial Introduction to the Language B》之中。不久，同作者於1974年所撰寫的《Programming in C: A Tutorial》，也延用這個範例；而以本檔案擴編改寫的《C語言程式設計》也保留了這個範例程式。工作時，我們也會使用類似於 hello,world 的 boilerplate 來完成基本的項目建立。

同時需要注意的一點是，在每個大的項目開始之前我們應該去找尋好開發環境。搭建環境是一件非常重要的事，它決定了你能不能更好地工作。畢竟環境是生產率的一部分。高效的程式設計師和低效程式設計師間的十倍差距，至少有三倍是因為環境差異。

因此在這一章裡，我們將講述幾件事情：

1. 使用怎樣的作業系統
2. 如何去選擇工具
3. 如何搭建相應作業系統上的環境
4. 如何去學習一門語言

工具只是輔助
---

一個好的工具確實有助於程式設計，但是他只會給我們帶來的是幫助。我們寫出來的程式碼還是和我們的水平保持著一致的。

什麼是好的工具，這個說法就有很多了，但是有時候我們往往沉迷於事物的表面。有些時候 Vim 會比 Visual Studio 強大，當你只需要修改的是一個配置檔案的時候，簡單且足夠快捷——在我們還未用 VS 開啟的時候，我們已經用 Vim 做完這個活了。

> “好的裝備確實能帶來一些幫助，但事實是，你的演奏水平是由你自己的手指決定的。” -- 《REWORK》

###WebStorm 還是 Sublime?

作為一個 IDE 有時候忽略的因素會過多，一開始的程式碼由類似於 Sublime text 之類的編輯器開始會比較合適。於是我們又開始陷入 IDE 及 Editor 之戰了，無聊的時候討論一下這些東西是有點益處的。相互瞭解一下各自的優點，也是不錯的，偶爾可以換個環境試試。

剛開始學習的時候，我們只需要普通的工具，或者我們習慣了的工具去開始我們的工作。我們要的是把主要精力放在學習的東西上，而不是工具。剛開始學習一種新的語言的時候，我們不需要去討論哪個是最好的開發工具，如 Java，有時候可能是 Eclipse，有時候可能是 Vim，如果我們為的只是去寫一個 hello,world。在 Eclipse 上浪費太多的時間是不可取的，因為他用起來的效率可不比你在鍵盤上敲打來得快，當你移動你的手指去動你的滑鼠的時候，我想你可以用那短短的時間完成編譯，執行了。

####工具是為了效率

尋找工具的目的和尋找捷徑是一樣的，我們需要更快更有效率地完成我們的工作，換句話說，我們為了獲取更多的時間用於其他的事情。而這個工具的用途是要看具體的事物的，如果我們去寫一個小說、部落格的時候，word 或者 web editor 會比 tex studio 來得快，不是麼。我們用 TEX 來排版的時候會比我們用 WORD 排版的時候來得更快，所以這個工具是相對而論的。有時候用一個順手的工具會好很多，但是不一定會是事半功倍的。我們應該將我們的目標專注於我們的內容，而不是我們的工具上。

我們用 Windows 自帶的畫圖就可以完成裁剪的時候，我們就沒必要執行起 GIMP 或者 Photoshop 去完成這個簡單的任務。效率在某些時候的重要性，會比你選擇的工具有用得多，學習的開始就是要去了解那些大眾推崇的東西。

####瞭解、熟悉你的工具

Windows 的功能很強大，只是大部分人用的是隻是小小一部分。而不是一小部分，即使我們天天用著，我們也沒有學習到什麼新的東西。和這個就如同我們的工具一樣，我們天天用著他們，如果我們只用 Word 來寫寫東西，那麼我們可以用 Abiword 來替換他。但是明顯不太可能，因為強大的工具對於我們來說有些更大的吸引力。

如果你負擔得起你手上的工具的話，那麼就儘可能去了解他能幹什麼。即使他是一些無關僅要的功能，比如 Emacs 的煮咖啡。有一本手冊是最好不過的，手冊在手邊可以即時查閱，不過出於環保的情況下，就不是這樣子的。手冊沒有辦法即時同你的軟體一樣更新，電子版的更新會比你手上用的那個手冊更新得更快。

Linux 下面的命令有一大堆，只是我們常用的只有一小部分——20%的命令能夠完成80%的工作。如同 CISC 和 RISC 一樣，我們所常用的指令會讓我們忘卻那些不常用的指令。而那些是最實用的，如同我們日常工作中使用的 Linux 一樣，記憶過多的不實用的東西，不比把他們記在筆記上實在。我們只需要瞭解有那些功能，如何去用他。

###語言也是一種工具

越來越多的框架和語言出現、更新得越來越快。特別是這樣一個高速發展的產業，每天都在湧現新的名詞。如同我們選擇語言一樣，選擇合適的有時候會比選得順手的來得重要。然而，這個可以不斷地被推翻。

當我們熟悉用 Python、Ruby、PHP 等去構建一個網站的時候，JavaScript 用來做網站後臺，這怎麼可能——於是 Node.js 火了。選擇工具本身是一件很有趣的事，因為有著越來越多的可能性。

過去 PHP 是主流的開發，不過現在也是，PHP 為 WEB 而生。有一天 Ruby on Rails 出現了，一切就變了，變得高效，變得更 Powerful。MVC 一直很不錯，不是麼？於是越來越多的框架出現了，如 Django，Laravel 等等。不同的語言有著不同的框架，JavaScript 上也有著合適的框架，如 AngularJS。不同語言的使用者們用著他們合適的工具，因為學習新的東西，對於多數的人來說就是一種新的挑戰。在學面嚮物件語言的時候，人們很容易把程式寫成過程式的。

沒有合適的工具，要麼創造一個，要麼選擇一個合適的。

####小結

學習 Django 的時候習慣了有一個後臺，於是開始使用 Laravel 的時候，尋找 Administartor。需要編譯的時候習慣用 IDE，不需要的時候用 Editor，只是因為有效率，嵌入式的時候 IDE 會有效率一點。

以前不知道 WebStorm 的時候，習慣用 DW 來格式化 HTML，Aptana 來格式化 JavaScript。

以前，習慣用 WordPress 來寫部落格，因為可以有移動客戶端，使用電腦時就不喜歡開啟瀏覽器去寫。

等等

等

提高效率的工具
---

在提高效率的 N 種方法裡：有一個很重要的方法是使用快捷鍵。熟練掌握快捷鍵可以讓我們隨著自己的感覺編寫程式——有時候如果我們手感不好，是不是就說明今天不適合寫程式碼！笑~~

由於我們可能使用不同的作業系統來完成不同的工具。下面就先說說一些通用的、不限操作的工具：

###快速啟動軟體

在我還不和道有這樣的工具的時候，我都是把圖示放在下面的工作列裡：

![Windows工作列](assets/article/chapter1/windows-launch.png)


直到有一天，我知道有這樣的工具。這裡不得不提到一本書《卓有成效的程式設計師》，在書中提到了很多提高效率的工具。使用快捷鍵是其中的一個，而還有一個是使用快速啟動軟體。於是，我在 Windows 上使用了 Launcy:

![Launchy](assets/article/chapter1/launchy.png)

通過這個軟體，我們可以在電腦上通過輸入軟體名，然後執行相關的軟體。我們不再需要點選某個選單，再從選單裡選中某個軟體開啟。

###IDE

儘管在上一篇中，我們說過 IDE 和編輯器沒有什麼好爭論的。但是如果是從頭開始搭建環境的話，IDE 是最好的——編輯器還需要安裝相應的外掛。所以，這也就是為什麼面試的時候會用編輯器的原因。

IDE 的全稱是整合開發環境，顧名思義即它整合了你需要用到的一些工具。而如果是編輯器的話，你需要自己去找尋合適的工具來做這件事。不過，這也意味著使用編輯器會有更多的自由度。如果你沒有足夠的時間去打造自己的開發環境就使用 IDE 吧。

一般來說，他們都應該有下面的一些要素：

 - **shortcut（快捷鍵）**
 - **Code HighLight（程式碼高亮）**
 - **Auto Complete（自動補全）**
 - **Syntax Check（語法檢查）**

而如果是編輯器的話，就需要自己去找尋這些相應的外掛。

IDE 一般是針對特定語言才產生的，並且優化更好。而，編輯器則需要自己去搭配。這也意味著如果你需要在多個語言上工作時，並且喜歡折騰，你可以考慮使用編輯器。

###DEBUG 工具

不得不提及的是在有些 IDE 自帶了 Debug 工具，這點可能使得使用 IDE 更有優勢。在簡單的項目裡，我們可能不需要這樣的 Debug 工具。因為我們對我們的程式碼庫比較熟悉，一個簡單的問題一眼就知道是哪裡的問題。而對於那些複雜的項目來說，可能就沒有那麼簡單了。特別是當你來到一個新的大中型項目，一個簡單的邏輯在實現上可能要經過一系列的函數才能處理完。

這時候我們就需要 Debug 工具——對於前端開發來說，我們可能使用 Chrome 的 Dev Tools。但是對於後端來說，我們就需要使用別的工具。如下圖所示的是 Intellij Idea 的 Debug 介面：

![Intellij Idea Debug](assets/article/chapter1/idea-debug.png)

在 Debug 的過程中，我們可以根據程式碼的執行流程一步步向下執行。這也意味著，當出現 Bug 的時候我們可以更容易找到 Bug。這就是為什麼他叫 Debug 工具的原因了。

###終端或命令提示符

在開始寫程式碼的時候，使用 GUI 可能是難以戒掉的一個習慣。但是當你習慣了使用終端之後，或者說使用終端的工具，你會發現這是另外一片天空。對於 GUI 應用上同樣的選單來說，在終端上也會有同樣的工具——只是你覺得記住更多的命令。而且不同的工具對於同一實現可能會不同的規範，而 GUI 應用則會有一致的風格。不過，總的來說使用終端是一個很有益的習慣——從速度、便捷性。忘了提到一點，當你使用 Linux 伺服器的時候，你不得不使用終端。

![Linux 終端截圖](assets/article/chapter1/linux-server-console.jpg)

使用終端的優點在於我們可以擺脫滑鼠的操作——這可以讓我們更容易集中精力於完成任務。而這也是兩種不同的選擇，便捷還是更快。雖是如此，但是這也意味著學習 Linux 會越來越輕鬆。

![Linux 與 Windows 的學習曲線](assets/article/chapter1/linux-learn-line.png)

雖然這是以 Linux 和 Windows 作了兩個不同的對比，但是兩個系統在終端工具上的差距是很大的。Linux 自身的哲學鼓勵使用命令列來完成任務，這也意味著在 Linux 上會有更多的工具可以在命令列下使用。雖然 Windows 上也可以——如使用 CygWin 來完成，但是這看上去並不是那麼讓人滿意！

###包管理

雖然包管理不僅僅存在於作業系統中，還存在著語言的包管理工具。在作業系統中安裝軟體，最方便的東西莫過於包管理了。引自 OpenSUSE 官網的說明及圖片:

![包管理](assets/article/chapter1/pm.png)

Linux 發行版無非就是一堆軟體包 (package) 形式的應用程式加上整體地管理這些應用程式的工具。通常這些 Linux 發行版，包括 OpenSUSE，都是由成千上萬不同的軟體包構成的。

 - 軟體包: 軟體包不止是一個檔案，內含構成軟體的所有檔案，包括程式本身、共享庫、開發包以及使用說明等。

 - 後設資料 (metadata) 包含於軟體包之中，包含軟體正常執行所需要的一些資訊。軟體包安裝之後，其後設資料就儲存於本地的軟體包資料庫之中，以用於軟體包檢索。

 - 依賴關係 (dependencies) 是軟體包管理的一個重要方面。實際上每個軟體包都會涉及到其他的軟體包，軟體包里程式的執行需要有一個可執行的環境（要求有其他的程式、庫等），軟體包依賴關係正是用來描述這種關係的。

我們經常會使用各式各樣的包管理工具，來加速我們地日常使用。而不是 Google 某個軟體，然後下載，接著安裝。

環境搭建
---

由於我近期工作在 Mac OS X 上，所以先以 Mac OS X 為例。

###OS X

**[Homebrew](http://brew.sh/)**

> 包管理工具，官方稱之為 The missing package manager for OS X。

**[Homebrew Cask](https://caskroom.github.io/)**

> brew-cask 允許你使用命令列安裝 OS X 應用。

**[iTerm2](https://www.iterm2.com/)**

> iTerm2 是最常用的終端應用，是 Terminal 應用的替代品。

**[Zsh](http://www.zsh.org/)**

Zsh 是一款功能強大終端（shell）軟體，既可以作為一個互動式終端，也可以作為一個指令碼直譯器。它在相容 Bash 的同時 (預設不相容，除非設定成 emulate sh) 還有提供了很多改進，例如：

 - 更高效
 - 更好的自動補全
 - 更好的檔名展開（通配符展開）
 - 更好的陣列處理
 - 可定製性高

**[Oh My Zsh](http://ohmyz.sh/)**

> Oh My Zsh 同時提供一套外掛和工具，可以簡化命令列操作。

**[Sublime Text 2](https://www.sublimetext.com/)**

> 強大的檔案編輯器。

**[MacDown](http://macdown.uranusjr.com/)**

> MacDown 是 Markdown 編輯器。

**[CheatSheet](https://www.mediaatelier.com/CheatSheet/)**

> CheatSheet 能夠顯示當前程式的快捷鍵列表，預設的快捷鍵是長按⌘。

**[SourceTree](https://www.sourcetreeapp.com/)**

> SourceTree 是 Atlassian 公司出品的一款優秀的 Git 圖形化客戶端。

**[Alfred](https://www.alfredapp.com/)**

> Mac 使用者不用滑鼠鍵盤的必備神器，配合大量 Workflows，習慣之後可以大大減少操作時間。

上手簡單，調教成本在後期自定義 Workflows，不過有大量雷鋒使用者提供的現成擴充套件，訪問這裡挑選喜歡的，並可以極其簡單地根據自己的需要修改。

**[Vimium](https://vimium.github.io/)**

> Vimium 是一個 Google Chrome 擴充套件，讓你可以純鍵盤操作 Chrome。

相關參考：

 - [Mac web developer apps](https://gist.github.com/erikreagan/3259442)
 - [強迫症的 Mac 設定指南](https://github.com/macdao/ocds-guide-to-setting-up-mac)

###Windows

**[Chocolatey](https://chocolatey.org/)**

> Chocolatey 是一個軟體包管理工具，類似於 Ubuntu 下面的 apt-get,不過是執行在 Windows 環境下面。

**[Wox](http://www.getwox.com/)**

> Wox 是一個高效的快速啟動器工具，通過快捷鍵撥出，然後輸入關鍵字來搜尋程式進行快速啟動，或者搜尋本地硬碟的檔案，開啟百度、Google 進行搜尋，甚至是通過一些外掛的功能實現單詞翻譯、關閉螢幕、查詢剪貼簿歷史、查詢程式設計文件、查詢天氣等更多功能。它最大的特點是可以支援中文拼音的模糊匹配。

**[PowerShell](https://msdn.microsoft.com/en-us/powershell/mt173057.aspx)**

> Windows PowerShell 是微軟公司為 Windows 環境所開發的殼程式（shell）及指令碼語言技術，採用的是命令列介面。這項全新的技術提供了豐富的控制與自動化的系統管理能力。

**[cmder](http://cmder.net/)**

> cmder 把 conemu，msysgit 和 clink 打包在一起，讓你無需配置就能使用一個真正乾淨的 Linux 終端！她甚至還附帶了漂亮的 monokai 配色主題。

**[Total Commander](http://www.ghisler.com/)**

> Total Commander 是一款應用於 Windows 平臺的檔案管理器 ，它包含兩個並排的視窗，這種設計可以讓使用者方便地對不同位置的“檔案或資料夾”進行操作，例如複製、移動、刪除、比較等，相對 Windows 資源管理器而言方便很多，極大地提高了檔案操作的效率，被廣大軟體愛好者親切地簡稱為：TC 。

###GNU/Linux


**[Zsh](http://www.zsh.org/)**

Zsh 是一款功能強大終端（shell）軟體，既可以作為一個互動式終端，也可以作為一個指令碼直譯器。它在相容 Bash 的同時 (預設不相容，除非設定成 emulate sh) 還有提供了很多改進，例如：

 - 更高效
 - 更好的自動補全
 - 更好的檔名展開（通配符展開）
 - 更好的陣列處理
 - 可定製性高

**[Oh My Zsh](http://ohmyz.sh/)**

> Oh My Zsh 同時提供一套外掛和工具，可以簡化命令列操作。

**[ReText](https://github.com/retext-project/retext)**

> ReText 是一個使用 Markdown 語法和 reStructuredText (reST) 結構的文字編輯器，編輯的內容支援匯出到 PDF、ODT 和 HTML 以及純文字，支援即時預覽、網頁生成以及 HTML 語法高亮、全屏模式，可匯出檔案到 Google Docs 等。

**[Launchy](http://www.launchy.net/)**

> Launchy 是一款免費開源的協助您摒棄 Windows “執行”的 Dock 式替代工具，既方便又實用，自帶多款面板，作為美化工具也未嘗不可。

環境搭建完畢！現在，就讓我們來看看如何學好一門語言！

學好一門語言的藝術
---

###一次語言學習體驗

在我們開始學習一門語言或者技術的時候，我們可能會從一門 "hello,world" 開始。

好了，現在我是 Scala 語言的初學者，接著我用搜尋引擎去搜尋『Scala』來看看『Scala』是什麼鬼：

>  Scala 是一門類 Java 的程式語言，它結合了物件導向程式設計和函數語言程式設計。

接著又開始看『Scala 'hello,world'』，然後找到了這樣的一個示例：

```
object HelloWorld {
  def main(args: Array[String]): Unit = {
    println("Hello, world!")
  }
}
```

GET 到了5%的知識。

看上去這門語言相比於 Java 語言來說還行。然後我找到了一本名為『Scala 指南』的電子書，有這樣的一本目錄：

 - 表示式和值
 - 函數是一等公民
 - 借貸模式
 - 按名稱傳遞參數
 - 定義類
 - 鴨子類型
 - 柯里化
 - 範型
 - Traits
 - ...

看上去還行， 又 GET 到了5%的知識點。接著，依照上面的程式碼和搭建指南在自己的電腦上安裝了 Scala 的環境：

```bash
brew install scala
```

Windows 使用者可以用:

```
choco install scala
```

然後開始寫一個又一個的 Demo，感覺自己 GET 到了很多特別的知識點。

到了第二天忘了！

![Bro Wrong](assets/article/chapter1/wrong.jpg)

接著，你又重新把昨天的知識過了一遍，還是沒有多大的作用。突然間，你聽到別人在討論什麼是**這個世界上最好的語言**——你開始加入討論了。

於是，你說出了 Scala 這門語言可以：

 - 支援高階函數。lambda，閉包...
 - 支援偏函數。 match..
 - mixin，依賴注入..
 - 等等

雖然隔壁的 Python 小哥贏得了這次辯論，然而你發現你又回想起了 Scala 的很多特性。

![最流行的語言](assets/article/chapter1/popular.jpg)

你發現隔壁的 Python 小哥之所以贏得了這場辯論是因為他把 Python 語言用到了各個地方——機器學習、人工智慧、硬體、Web開發、移動應用等。而你還沒有用 Scala 寫過一個真正的應用。

讓我想想我能做什麼？我有一個部落格。對，我有一個部落格，可以用 Scala 把我的部落格重寫一遍：

1. 先找一 Scala 的 Web 框架，Play 看上去很不錯，就這個了。這是一個 MVC 框架，原來用的 Express 也是一個 MVC 框架。Router 寫這裡，Controller 類似這個，就是這樣的。
2. 既然已經有 PyJS，也會有 Scala-js，前端就用這個了。

好了，部落格重寫了一遍了。

感覺還挺不錯的，我決定向隔壁的 Java 小弟推銷這門語言，以解救他於火海之中。

『讓我想想我有什麼殺手鐗？』

『這裡的知識好像還缺了一點，這個是什麼？』

好了，你已經 GET 到了90%了。如下圖所示：

![Learn](assets/article/chapter1/learn.jpg)

希望你能從這張圖上 GET 到很多點。

###輸出是最好的輸入

上面那張圖『學習金字塔』就是在說明——輸出是最好的輸入。

如果你不試著去寫點部落格、整理資料、準備分享，那麼你可能並沒有意識到你缺少了多少東西。雖然你已經有了很多的實踐，然並卵。

因為你一直在完成功能、完成工作，你總會有意、無意地漏掉一些知識，而你也沒有意識到這些知識的重要性。

![Output is Input](assets/article/chapter1/output-input.png)

從我有限的（500+）部落格寫作經驗裡，我發現多數時候我需要更多地參考資料才能更好也向人們展示這個過程。為了輸出我們需要更多的輸入，進而加速這個過程。

而如果是寫書的時候則是一個更高水平的學習，你需要發現別人在他們的書中欠缺的一些知識點。並且你還要展示一些在別的書中沒有，而這本書會展現這個點的知識，這意味著你需要挖掘得更深。

所以，如果下次有人問你如何學一門新語言、技術，那麼答案就是寫一本書。

###如何應用一門新的技術

對於多數人來說，寫書不是一件容易的事，而應用新的技術則是一件迫在眉睫的事。

通常來說，技術出自於對現有的技術的改進。這就意味著，在掌握現有技術的情況下，我們只需要做一些小小的改動就更可以實現技術升級。

而學習一門新的技術的最好實踐就是用這門技術對現有的系統行重寫。

第一個系統(v1)： ``Spring MVC`` + ``Bootstrap`` + ``jQuery``

那麼在那個合適的年代裡， 我們需要單頁面應用，就使用了Backbone。然後，我們就可以用 Mustache + HTML 來替換掉 JSP。

第二個系統(v2)： ``Spring MVC`` +  ``Backbone`` + ``Mustache``

在這時我們已經實現了前後端分離了，這時候系統實現上變成了這樣。

第二個系統(v2.2)： ``RESTful  Services`` +  ``Backbone`` + ``Mustache``

或者

第二個系統(v2.2)： ``RESTful Services`` +  ``AngularJS 1.x``

Spring 只是一個 RESTful 服務，我們還需要一些問題，比如 DOM 的渲染速度太慢了。

第三個系統(v3)： ``RESTful  Services`` + ``React``

系統就是這樣一步步演進過來的。

儘管在最後系統的架構已經不是當初的架構，而系統本身的業務邏輯變化並沒有發生太大的變化。

特別是對於如部落格這一類的系統來說，他的一些技術實現已經趨於穩定，而且是你經常使用的東西。所以，下次試試用新的技術的時候，可以先從對你的部落格的重寫開始。



Web 程式設計基礎
---

###從瀏覽器到伺服器

如果你的作業系統帶有 cURL 這個軟體(在 GNU/Linux、Mac OS 都自帶這個工具，Windows 使用者可以從[http://curl.haxx.se/download.html](http://curl.haxx.se/download.html)下載到)，那麼我們可以直接用下面的命令來看這看這個過程(-v 參數可以顯示一次 http 通訊的整個過程)：

```
curl -v https://www.phodal.com
```

我們就會看到下面的響應過程:

```bash
* Rebuilt URL to: https://www.phodal.com/
*   Trying 54.69.23.11...
* Connected to www.phodal.com (54.69.23.11) port 443 (#0)
* TLS 1.2 connection using TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384
* Server certificate: www.phodal.com
* Server certificate: COMODO RSA Domain Validation Secure Server CA
* Server certificate: COMODO RSA Certification Authority
* Server certificate: AddTrust External CA Root
> GET / HTTP/1.1
> Host: www.phodal.com
> User-Agent: curl/7.43.0
> Accept: */*
>
< HTTP/1.1 403 Forbidden
< Server: phodal/0.19.4
< Date: Tue, 13 Oct 2015 05:32:13 GMT
< Content-Type: text/html; charset=utf-8
< Content-Length: 170
< Connection: keep-alive
<
<html>
<head><title>403 Forbidden</title></head>
<body bgcolor="white">
<center><h1>403 Forbidden</h1></center>
<hr><center>phodal/0.19.4</center>
</body>
</html>
* Connection #0 to host www.phodal.com left intact
```

我們嘗試用 cURL 去訪問我的網站，會根據訪問的域名找出其 IP，通常這個對映關係是來源於 ISP 快取 DNS（英語：Domain Name System）伺服器[^DNSServer]。

以“\*”開始的前8行是一些連線相關的資訊，稱為**響應首部**。我們向域名 [https://www.phodal.com/](https://www.phodal.com/)發出了請求，接著 DNS伺服器告訴了我們網站伺服器的 IP，即54.69.23.11。出於安全考慮，在這裡我們的示例，我們是以 HTTPS 協議為例，所以在這裡連線的埠是 443。因為使用的是 HTTPS 協議，所以在這裡會試圖去獲取伺服器證書，接著獲取到了域名相關的證書資訊。

隨後以“>”開始的內容，便是向Web伺服器傳送請求。Host 即是我們要訪問的主機的域名，GET / 則代表著我們要訪問的是根目錄，如果我們要訪問 [https://www.phodal.com/about/](https://www.phodal.com/about/)頁面在這裡，便是 GET 資原始檔 /about。緊隨其後的是 HTTP 的版本號（HTTP/1.1）。User-Agent 通常指向的是使用者行為的軟體，通常會加上硬體平臺、系統軟體、應用軟體和使用者個人偏好等等的一些資訊。Accept 則指的是告知伺服器傳送何種媒體類型。

這個過程，大致如下圖所示：

![DNS 到伺服器的過程](assets/article/chapter1/server-dns-forward.jpg)

在圖中，我們會發現解析 DNS 的時候，我們需要先本地 DNS 伺服器查詢。如果沒有的話，再向根域名伺服器查詢——這個域名由哪個伺服器來解析。直至最後拿到真正的伺服器IP才能獲取頁面。

當我們拿到相應的 HTML、JS、CSS 後，我們就開始渲染這個頁面了。

####HTTP 協議

說到這裡，我們不得不說說 HTTP 協議——超文字傳輸協議。它也是一個基於文字的傳輸協議，這就是為什麼你在上面看到的都是文字的傳輸過程。

###從 HTML 到頁面顯示

而瀏覽器接收到文字的時候，就要開始著手將 HTML 變成螢幕上顯示的內容。下圖是 Chrome 渲染頁面的一個時間線：

![Chrome 渲染的 Timeline](assets/article/chapter1/chrome-timeline.jpg)

及其整個渲染過程如下圖所示：

![Render HTML](assets/article/chapter1/render-html.png)

（PS: 需要注意的是這裡用的是 WebKit 核心的渲染過程，即 Chrome 和 Safari 等瀏覽器所使用的核心。）

從上面的兩圖可以看出來第一步都 Parse HTML，而 Parse HTML 實質上就是將其將解析為 DOM Tree。與此同時，CSS 解析器會解析 CSS 會產生 CSS 規則樹。

隨後會根據生成的 DOM 樹和 CSS 規則樹來構建 Render Tree，接著生成 Render Tree的佈局，最後就是繪製出 Render Tree。


詳細的內容還得參見相關的書籍~~。

相關內容：

 - 《[How browsers work](http://taligarsiel.com/Projects/howbrowserswork1.htm)》

HTML
---

讓我們先從身邊的語言下手，也就是現在無處不在的 HTML+Javascript+CSS。

之所以從 HTML 開始，是因為我們不需要配置一個複雜的開發環境，也許你還不知道開發環境是什麼東西，不過這也沒關係，畢竟這些知識需要慢慢的接觸才能有所瞭解，尤其是對於普通的業餘愛好者來說，當然，對於專業選手而言自然不是問題。HTML 是 Web 的核心語言，也算是比較基礎的語言。

###hello,world

hello,world 是一個傳統，所以在這裡也遵循這個有趣的傳統，我們所要做的事情其實很簡單，雖然也有一點點 hack 的感覺。——讓我們先來新建一個檔案並命名為"helloworld.html"。

(PS:大部分人應該都是在 Windows 環境下工作的，所以你需要新建一個文字，然後重新命名，或者你需要一個編輯器，在這裡我們推薦用 **Sublime Text** 。破解不破解，註冊不註冊都不會對你的使用有太多的影響。)

1. 新建檔案

2. 輸入 <pre><code class="html">hello,world</code></pre>

3. 儲存為->"helloworld.html"，

4. 雙擊開啟這個檔案。 正常情況下都應該是用你的預設瀏覽器開啟。只要是一個正常工作的現代瀏覽器，都應該可以看到上面顯示的是"Hello,world"。

這才是最短的 hello,world 程式，但是呢？在 Ruby 中會是這樣子的

``` bash
2.0.0-p353 :001 > p "hello,world"
"hello,world"
	=> "hello,world"
2.0.0-p353 :002 >
```

等等，如果你瞭解過 HTML 的話，會覺得這一點都不符合語法規則，但是他工作了，沒有什麼比安裝完 Nginx 後看到 It works! 更讓人激動了。

遺憾的是，它可能無法在所有的瀏覽器上工作，所以我們需要去偵錯其中的 bug。

####偵錯 hello,world

我們會發現我們的程式碼在瀏覽器中變成了下面的程式碼，如果你和我一樣用的是 Chrome，那麼你可以右鍵瀏覽器中的空白區域，點選審查元素，就會看到下面的程式碼。

``` html
<html>
	<head></head>
	<body>hello,world</body>
</html>
```

這個才是真正能在大部分瀏覽器上工作的程式碼，所以複製它到編輯器裡吧。

####說說 hello,world

我很不喜歡其中的<\*></*>，但是我也沒有找到別的方法來代替它們，所以這是一個設計得當的語言。甚至大部分人都說這算不上是一門真正的語言，不過 HTML 的原義是

> 超文字標記語言

所以我們可以發現其中的關鍵詞是標記——markup，也就是說 html 是一個 markup，head 是一個 markup，body 也是一個 markup。

然而，我們真正工作的程式碼是在 body 裡面，至於為什麼是在這裡面，這個問題就太複雜了。打個比方來說：

1. 我們所使用的漢語是人類用智慧創造的，我們所正在學的這門語言同樣也是人類創造的。

2. 我們在自己的語言裡遵循著 **桌子是桌子，凳子是凳子** 的原則，很少有人會問為什麼。


###中文？

所以我們也可以把計算機語言與現實世界裡用於交流溝通的語言劃上一個等號。而我們所要學習的語言，並不是我們最熟悉的漢語語言，所以我們便覺得這些很複雜，但是如果我們試著用漢語替換掉上面的程式碼的話
```HTML
<語言>
	<頭><結束頭>
	<身體>你好，世界<結束身體>
<結束語言>
```
這看上去很奇怪，只是因為是直譯過去的原因，也許你會覺得這樣會好理解一點，但是輸入上可就一點兒也不方便，因為這鍵盤本身就不適合我們去輸入漢字，同時也意味著可能你輸入的會有問題。

讓我們把上面的程式碼代替掉原來的程式碼然後儲存，開啟瀏覽器會看到下面的結果
```HTML
<語言> <頭><結束頭> <身體>你好，世界<結束身體> <結束語言>
```

更不幸的結果可能是

```HTML
<璇█> <澶�><緇撴潫澶�> <韜綋>浣犲ソ錛屼笘鐣�<緇撴潫韜綋> <緇撴潫璇█>
```

這是一個編碼問題，對中文支援不友好。

我們把上面的程式碼改為和標記語言一樣的結構

```HTML
<語言>
	<頭></頭>
	<身體>你好，世界</身體>
</語言>
```

於是我們看到的結果便是

```HTML
<語言> <頭> <身體>你好，世界
```

被 Chrome 瀏覽器解析成什麼樣了？

``` html
<html><head></head><body><語言>
		<頭><!--頭-->
		<身體>你好，世界<!--身體-->
	<!--語言-->
</body></html>
```

以`<!--`開頭，`-->`結尾的是註釋，寫給人看的程式碼，不是給機器看的，所以機器不會去理解這些程式碼。

但是當我們把程式碼改成

```HTML
<whatwewanttosay>你好世界</whatwewanttosay>
```

瀏覽器上面顯示的內容就變成了

```HTML
你好世界
```

或許你會覺得很神奇，但是這一點兒也不神奇，雖然我們的中文語法也遵循著標記語言的標準，但是我們的瀏覽器不支援中文標記。

結論:

1. 瀏覽器對中文支援不友好。
2. 瀏覽器對英文支援友好。

剛開始的時候不要對中文程式設計有太多的想法，這是很不現實的:

1. 現有的系統都是基於英語語言環境構建的，對中文支援不是很友好。
2. 中文輸入的速度在某種程度上來說沒有英語快。

我們離開話題已經很遠了，但是這裡說的都是針對於那些不滿於英語的人來說的，只有當我們可以從頭構建一箇中文系統的時候才是可行的，而這些就要將 CPU、軟體、硬體都包含在內，甚至我們還需要考慮重新設計 CPU 的結構，在某種程度上來說會有些不現實。或許，需要一代又一代人的努力。忘記那些吧，師夷之長技以制夷。

###其它 HTML 標記

新增一個標題，

```HTML
<html>
	<head>
		<title>標題</title>
	</head>
	<body>hello,world</body>
</html>
```

我們便可以在瀏覽器的最上方看到“標題”二字，就像我們常用的淘寶網，也包含了上面的東西，只是還包括了更多的東西，所以你也可以看懂那些我們可以看到的淘寶的標題。

``` html
<html>
<head>
	<title>標題</title>
</head>
<body>
hello,world
<h1>大標題</h1>
<h2>次標題</h2>
<h3>...</h3>
<ul>
	<li>列表1</li>
	<li>列表2</li>
</ul>
</body>
</html>
```

更多的東西可以在一些書籍上看到，這邊所要說的只是一次簡單的語言入門，其它的東西都和這些類似。

###小結

####美妙之處

我們簡單地上手了一門不算是語言的語言，瀏覽器簡化了這其中的大部分過程，雖然沒有 C 和其他語言來得有專業感，但是我們試著去開始寫程式碼了。我們可能在未來的某一篇中可能會看到類似的語言，諸如 Python，我們所要做的就是

```bash
$ python file.py
=>hello,world
```

然後在終端上返回結果。只是因為在我看來學會 HTML 是有意義的，簡單的上手，然後再慢慢地深入，如果一開始我們就去理解指針，開始去理解類。我們甚至還知道程式是怎麼編譯執行的時候，在這個過程中又發生了什麼。雖然現在我們也沒能理解這其中發生了什麼，但是至少展示了

1. 中文程式語言在當前意義不大，不現實，效率不高相容性差
2. 語言的語法是固定的。（ps:雖然我們也可以進行擴充，我們將會在後來支援上述的中文標記。）
3. 已經開始寫程式碼，而不是還在配置開發環境。
4. 隨身的工具才是最好的，最常用的 code 也才是實在的。


####更多

我們還沒有試著去解決“某商店裡的糖一顆5塊錢，小明買了3顆糖，小明一共花了多少錢”的問題。也就是說我們學會的是一個還不能解決實際問題的語言，於是我們還需要學點東西，比如 JavaScript, CSS。我們可以將 JavaScript 理解為解決問題的語言，HTML 則是前端顯示，CSS 是配置檔案，這樣的話，我們會在那之後學會成為一個近乎專業的程式設計師。我們剛剛學習了一下怎麼在前端顯示那些程式碼的行為，於是我們還需要 JavaScript。

CSS
---

如果說 HTML 是建築的框架，CSS 就是房子的裝修。那麼 JavaScript 呢，我聽到的最有趣的說法是小三——還是先讓我們回到程式碼上來吧。

下面就是我們之前說到的程式碼，CSS 將 Red 三個字母變成了紅色。

```HTML
<!DOCTYPE html>
<html>
<head>
</head>
<body>
	<p id="para" style="color:red">Red</p>
</body>
	<script type="text/javascript" src="app.js"></script>
</html>
```

只是，

``` javascript
var para=document.getElementById("para");
para.style.color="blue";
```

將字型變成了藍色，CSS+HTML 讓頁面有序的工作著，但是 JavaScript 卻打亂了這些秩序，有著唯恐世界不亂的精彩，也難怪被冠以小三之名了——或許終於可以理解，為什麼以前人們對於 JavaScript 沒有好感了——不過這裡要講的是正室，也就是 CSS，這時還沒有 JavaScript。

![Red Fonts](assets/article/chapter1/redfonts.png)

###簡介

這不是一篇專業講述 CSS 的書籍，所以我不會去說 CSS 是怎麼來的，有些東西我們既然可以很容易從其他地方知道，也就不需要花太多時間去重複。諸如重構等這些的目的之一也在於去除重複的程式碼，不過有些重複是不可少的，也是有必要的，而通常這些東西可能是由其他地方複製過來的。

到目前為止我們沒有依賴於任何特殊的硬體或者是軟體，對於我們來說我們最基本的需求就是一臺電腦，或者可以是你的平板電腦，當然也可以是你的智慧手機，因為他們都有個瀏覽器，而這些都是能用的，對於我們的 CSS 來說也不會有例外的。

CSS(Cascading Style Sheets)，到今天我也沒有記得他的全稱，CSS 還有一箇中文名字是層疊式樣式表，事實上翻譯成什麼可能並不是我們關心的內容，我們需要關心的是他能做些什麼。作為三劍客之一，它的主要目的在於可以讓我們方便靈活地去控制 Web 頁面的外觀表現。我們可以用它做出像淘寶一樣複雜的介面，也可以像我們的書本一樣簡單，不過如果要和我們書本一樣簡單的話，可能不需要用到 CSS。HTML 一開始就是依照報紙的格式而設計的，我們還可以繼續用上面說到的編輯器，又或者是其他的。如果你喜歡 DreamWeaver 那也不錯，不過一開始使用 IDE 可無助於我們寫出良好的程式碼。

忘說了，CSS 也是有版本的，和 Windows，Linux 核心等等一樣，但是更新可能沒有那麼頻繁，HTML 也是有版本的，JavaScript 也是有版本的，複雜的東西不是當前考慮的內容。

####程式碼結構

對於我們的上面的 Red 示例來說，如果沒有一個好的結構，那麼以後可能就是這樣子。

```HTML
<!DOCTYPE html>
<html>
<head>
</head>
<body>
	<p style="font-size: 22px;color: #f00;text-align: center;padding-left: 20px;">如果沒有一個好的結構</p>
	<p style="font-size: 44px;color: #3ed;text-indent: 2em;padding-left: 2em;">那麼以後可能就是這樣子。。。。</p>
</body>
</html>
```

雖然我們看到的還是一樣的:

![No Style](assets/article/chapter1/nostyle.png)

於是我們就按各種書上的建議重新寫了上面的程式碼

```HTML
<!DOCTYPE html>
<html>
<head>
	<title>CSS example</title>
	<style type="text/css">
		.para{
			font-size: 22px;
			color: #f00;
			text-align: center;
			padding-left: 20px;
		}
		.para2{
			font-size: 44px;
			color: #3ed;
			text-indent: 2em;
			padding-left: 2em;
		}
	</style>
</head>
<body>
	<p class="para">如果沒有一個好的結構</p>
	<p class="para2">那麼以後可能就是這樣子。。。。</p>
</body>
</html>
```

總算比上面好看也好理解多了，這只是臨時的用法，當檔案太大的時候，正式一點的寫法應該如下所示:

```HTML
<!DOCTYPE html>
<html>
<head>
	<title>CSS example</title>
	<style type="text/css" href="style.css"></style>
</head>
<body>
	<p class="para">如果沒有一個好的結構</p>
	<p class="para2">那麼以後可能就是這樣子。。。。</p>
</body>
</html>
```

我們需要

```HTML
<!DOCTYPE html>
<html>
<head>
	<title>CSS example</title>
	<link href="./style.css" rel="stylesheet" type="text/css" />
</head>
<body>
	<p class="para">如果沒有一個好的結構</p>
	<p class="para2">那麼以後可能就是這樣子。。。。</p>
</body>
</html>
```

然後我們有一個像 app.js 一樣的 style.css 放在同目錄下，而他的內容便是

```CSS
.para{
	font-size: 22px;
	color: #f00;
	text-align: center;
	padding-left: 20px;
}
.para2{
	font-size: 44px;
	color: #3ed;
	text-indent: 2em;
	padding-left: 2em;
}
```

這程式碼和 JS 的程式碼有如此多的相似

```javascript
var para={
	font_size: '22px',
	color: '#f00',
	text_align: 'center',
	padding_left: '20px',
}
```

而22px、20px以及#f00都是數值，因此：

```javascript
var para={
	font_size: 22px,
	color: #f00,
	text_align: center,
	padding_left: 20px,
}
```

目測差距已經儘可能的小了，至於這些話題會在以後討論到，如果要讓我們的編譯器更正確的工作，那麼我們就需要非常多這樣的符號，除非你樂意去理解:

```lisp
(dotimes (i 4) (print i))
```

總的來說我們減少了符號的使用，但是用 lisp 便帶入了更多的括號，不過這是一種簡潔的表達方式，也許我們可以在其他語言中看到。

```
\d{2}/[A-Z][a-z][a-z]/\d{4}
```

上面的程式碼，是為了從一堆資料中找出“某日/某月/某年”。如果一開始不理解那是正規表示式，就會覺得那個很複雜。

這門語言可能是為設計師而設計的，但是設計師大部分還是不懂程式設計的，不過相對來說這門語言還是比其他語言簡單易懂一些。

###樣式與目標

如下所示，就是我們的樣式

```css
.para{
	font-size: 22px;
	color: #f00;
	text-align: center;
	padding-left: 20px;
}
```

我們的目標就是

> 如果沒有一個好的結構

所以樣式和目標在這裡牽手了，問題是他們是如何在一起的呢？下面就是 CSS 與 HTML 溝通的重點所在了:

###選擇器

我們用到的選擇器叫做類選擇器，也就是 class，或者說應該稱之為 class 選擇器更合適。與類選擇器最常一起出現的是 ID 選擇器，不過這個適用於比較高階的場合，諸如用 JS 控制 DOM 的時候就需要用到 ID 選擇器。而基本的選擇器就是如下面的例子:

```css
p.para{
	color: #f0f;
}
```

將程式碼新增到 style.css 的最下面會發現“如果沒有一個好的結構”變成了粉紅色，當然我們還會有這樣的寫法

```css
p>.para{
	color: #f0f;
}
```

為了產生上面的特殊的樣式，雖然不好看，但是我們終於理解什麼叫層疊樣式了，下面的程式碼的權重比上面高，也因此有更高的優先規則。

而通常我們可以通過一個

```css
p{
	text-align: left;
}
```

這樣的元素選擇器來給予所有的 p 元素一個左對齊。

還有複雜一點的複合型選擇器，下面的是 HTML 檔案

```html
<!DOCTYPE html>
<html>
<head>
	<title>CSS example</title>
	<link href="./style.css" rel="stylesheet" type="text/css" />
</head>
<body>
	<p class="para">如果沒有一個好的結構</p>
	<div id="content">
		<p class="para2">那麼以後可能就是這樣子。。。。</p>
	</div>
</body>
</html>
```

還有 CSS 檔案

```css
.para{
	font-size: 22px;
	color: #f00;
	text-align: center;
	padding-left: 20px;
}
.para2{
	font-size: 44px;
	color: #3ed;
	text-indent: 2em;
	padding-left: 2em;
}

p.para{
	color: #f0f;
}
div#content p {
	font-size: 22px;
}
```

###更有趣的 CSS

一個包含了 para2 以及 para_bg 的例子

```html
<div id="content">
	<p class="para2 para_bg">那麼以後可能就是這樣子。。。。</p>
</div>
```

我們只是新增了一個黑色的背景

```css
.para_bg{
	background-color: #000;
}
```

重新改變後的網頁變得比原來有趣了很多，所謂的繼承與合併就是上面的例子。

我們還可以用 CSS3 做出更多有趣的效果，而這些並不在我們的討論範圍裡面，因為我們討論的是 be a geek。

或許我們寫的程式碼都是那麼的簡單，從 HTML 到 JavaScript，還有現在的 CSS，只是總有一些核心的東西，而不是去考慮那些基礎語法，基礎的東西我們可以在實踐的過程中一一發現。但是我們可能發現不了，或者在平時的使用中考慮不到一些有趣的用法或者說特殊的用法，這時候可以通過觀察一些精緻設計的程式碼中學習到。複雜的東西可以變得很簡單，簡單的東西也可以變得很複雜。

JavaScript
---

JavaScript 現在已經無處不在了，也許你正開啟的某個網站，他便可能是 node.js+json+javascript+mustache.js 完成的，雖然你還沒理解上面那些是什麼，也正是因為你不理解才需要去學習更多的東西。但是你只要知道 JavaScript 已經無處不在了，它可能就在你手機上的某個 app 裡，就在你瀏覽的網頁裡，就執行在你 IDE 中的某個程序裡。

###hello,world

這裡我們還需要有一個 helloworld.html，JavaScript 是專為網頁互動而設計的指令碼語言，所以我們一點點來開始這部分的旅途，先寫一個符合標準的 helloworld.html

``` html
<!DOCTYPE html>
<html>
	<head></head>
	<body></body>
</html>
```

然後開始融入我們的 JavaScript，向 HTML 中插入JavaScript 的方法，就需要用到 HTML 中的 \<script> 標籤，我們先用頁面嵌入的方法來寫 helloworld。

``` html
<!DOCTYPE html>
<html>
	<head>
		<script>
			document.write('hello,world');
		</script>
	</head>
	<body></body>
</html>
```

按照標準的寫法，我們還需要聲明這個指令碼的類型

``` html
<!DOCTYPE html>
<html>
	<head>
		<script type="text/javascript">
			document.write('hello,world');
		</script>
	</head>
	<body></body>
</html>
```

沒有顯示 hello,world ?試試下面的程式碼

``` html
<!DOCTYPE html>
<html>
	<head>
		<script type="text/javascript">
			document.write('hello,world');
		</script>
	</head>
	<body>
		<noscript>
			disable Javascript
		</noscript>
	</body>
</html>
```

###JavaScriptFul

我們需要讓我們的程式碼看上去更像是 js，同時是以 js 結尾。就像 C 語言的源碼是以 C 結尾的，我們也同樣需要讓我們的程式碼看上去更正式一點。於是我們需要在 helloworld.html 的同一資料夾下建立一個 app.js 檔案，在裡面寫著

``` javascript
document.write('hello,world');
```

同時我們的 helloworld.html 還需要告訴我們的瀏覽器 js 程式碼在哪裡

``` html
<!DOCTYPE html>
<html>
	<head>
		<script type="text/javascript" src="app.js"></script>
	</head>
	<body>
		<noscript>
			disable Javascript
		</noscript>
	</body>
</html>
```

####從數學出發

讓我們回到第一章講述的小明的問題，**從實際問題下手程式設計，更容易學會程式設計**。小學時代的數學題最喜歡這樣子了——某商店裡的糖一個5塊錢，小明買了3個糖，小明一共花了多少錢。在程式設計方面，也許我們還算是小學生。最直接的方法就是直接計算 3x5=?

``` javascript
document.write(3*5);
```

document.write 實際也我們可以理解為輸出，也就是往頁面裡寫入 3*5 的結果，在有雙引號的情況下會輸出字元串。我們便會在瀏覽器上看到15，這便是一個好的開始，也是一個糟糕的開始。

####設計和程式設計

對於實際問題，如果我們只是止於所要得到的結果，很多年之後，我們就成為了 code monkey。對這個問題進行再一次設計，所謂的設計有些時候會把簡單的問題複雜化，有些時候會使以後的擴充套件更加簡單。這一天因為這家商店的糖價格太高了，於是店長將價格降為了4塊錢。

``` javascript
document.write(3*4);
```

於是我們又得到了我們的結果，但是下次我們看到這些程式碼的時候沒有分清楚哪個是糖的數量，哪個是價格，於是我們重新設計了程式

``` javascript
price=4;
num=3;
document.write(price*num);
```

這才能叫得上是程式設計，或許你注意到了";"這個符號的存在，我想說的是這是另外一個標準，我們不得不去遵守，也不得不去 fuck。

####函數

記得剛開始學三角函數的時候，我們會寫

    sin 30=0.5

而我們的函數也是類似於此，換句話說，因為很多搞計算機的先驅都學好了數學，都把數學世界的規律帶到了計算機世界，所以我們的函數也是類似於此，讓我們從一個簡單的開始。

``` javascript
function hello(){
	return document.write("hello,world");
}
hello();
```

當我第一次看到函數的時候，有些小激動終於出現了。我們寫了一個叫 hello 的函數，它返回了往頁面中寫入 hello,world 的方法，然後我們呼叫了 hello 這個函數，於是頁面上有了 hello,world。

``` javascript
function sin(degree){
	return document.write(Math.sin(degree));
}
sin(30);
```

在這裡 degree 就稱之為變數。
於是輸出了 -0.9880316240928602，而不是 0.5，因為這裡用的是弧度制，而不是角度制。

    sin(30)

的輸出結果有點類似於sin 30。寫括號的目的在於，括號是為了方便解析，這個在不同的語言中可能是不一樣的，比如在 Ruby 中我們可以直接用類似於數學中的表達:

``` ruby
2.0.0-p353 :004 > Math.sin 30
=> -0.9880316240928618
2.0.0-p353 :005 >
```

我們可以在函數中傳入多個變數，於是我們再回到小明的問題，就會這樣去編寫程式碼。

``` javascript
function calc(price,num){
	result=price*num;
	document.write(result);
}
calc(3,4);
```

但是從某種程度上來說，我們的 calc 做了計算的事又做了輸出的事，總的來說設計上有些不好。

####重新設計

我們將輸出的工作移到函數的外面，

``` javascript
function calc(price,num){
	return price*num;
}
document.write(calc(3,4));
```

接著我們用一種更有意思的方法來寫這個問題的解決方案

``` javascript
function calc(price,num){
	return price*num;
}
function printResult(price,num){
	document.write(calc(price,num));
}
printResult(3, 4)
```

看上去更專業了一點點，如果我們只需要計算的時候我們只需要呼叫 calc，如果我們需要輸出的時候我們就呼叫 printResult 的方法。

####object 和函數

我們還沒有說清楚之前我們遇到過的 document.write 以及 Math.sin 的語法為什麼看上去很奇怪，所以讓我們看看他們到底是什麼，修改 app.js 為以下內容

``` javascript
document.write(typeof document);
document.write(typeof Math);
```

typeof document 會返回 document 的資料類型，就會發現輸出的結果是

``` javascript
object object
```

所以我們需要去弄清楚什麼是 object。物件的定義是

> 無序屬性的集合，其屬性可以包含基本值、物件或者函數。

建立一個 object，然後觀察這便是我們接下來要做的

``` javascript
store={};
store.candyPrice=4;
store.candyNum=3;
document.write(store.candyPrice * store.candyNum);
```

我們就有了和 document.write 一樣的用法，這也是物件的美妙之處，只是這裡的物件只是包含著基本值，因為

    typeof story.candyPrice="number"

一個包含物件的物件應該是這樣子的。

``` javascript
store={};
store.candyPrice=4;
store.candyNum=3;
document.writeln(store.candyPrice * store.candyNum);

var wall=new Object();
wall.store=store;
document.write(typeof wall.store);
```

而我們用到的 document.write 和上面用到的 document.writeln 都是屬於這個無序屬性集合中的函數。

下面程式碼說的就是這個無序屬性集合中的函數。

``` javascript
var IO=new Object();
function print(result){
	document.write(result);
};
IO.print=print;
IO.print("a obejct with function");
IO.print(typeof IO.print);
```

我們定義了一個叫 IO 的物件，聲明物件可以用

    var store={};

又或者是

    var store=new Object();

兩者是等價的，但是用後者的可讀性會更好一點，我們定義了一個叫print的函數，他的作用也就是 document.write，IO 中的print 函數是等價於 print() 函數，這也就是物件和函數之間的一些區別，物件可以包含函數，物件是無序屬性的集合，其屬性可以包含基本值、物件或者函數。

複雜一點的物件應該是下面這樣的一種情況。

``` javascript
var Person={name:"phodal",weight:50,height:166};
function dream(){
	future;
};
Person.future=dream;
document.write(typeof Person);
document.write(Person.future);
```

而這些會在我們未來的實際程式設計過程中用得更多。

###物件導向

開始之前先讓我們簡化上面的程式碼，

``` javascript
Person.future=function dream(){
	future;
}
```

看上去比上面的簡單多了，不過我們還可以簡化為下面的程式碼。。。

``` javascript
var Person=function(){
	this.name="phodal";
	this.weight=50;
	this.height=166;
	this.future=function dream(){
		return "future";
	};
};
var person=new Person();
document.write(person.name+"<br>");
document.write(typeof person+"<br>");
document.write(typeof person.future+"<br>");
document.write(person.future()+"<br>");
```

只是在這個時候 Person 是一個函數，但是我們聲明的 person 卻變成了一個物件 **一個Javascript函數也是一個物件，並且，所有的物件從技術上講也只不過是函數。** 這裡的"\<br\>"是 HTML 中的元素，稱之為 DOM，在這裡起的是換行的作用，我們會在稍後介紹它，這裡我們先關心下 this。this 關鍵字表示函數的所有者或作用域，也就是這裡的 Person。

上面的方法顯得有點不可取，換句話說和一開始的

    document.write(3*4);

一樣，不具有靈活性，因此在我們完成功能之後，我們需要對其進行優化，這就是程式設計的真諦——解決完實際問題後，我們需要開始真正的設計，而不是解決問題時的程式設計。

``` javascript
var Person=function(name,weight,height){
	this.name=name;
	this.weight=weight;
	this.height=height;
	this.future=function(){
		return "future";
	};
};
var phodal=new Person("phodal",50,166);
document.write(phodal.name+"<br>");
document.write(phodal.weight+"<br>");
document.write(phodal.height+"<br>");
document.write(phodal.future()+"<br>");
```

於是，產生了這樣一個可重用的 JavaScript 物件, this 關鍵字確立了屬性的所有者。

###其他

JavaScript 還有一個很強大的特性，也就是原型繼承，不過這裡我們先不考慮這些部分，用盡量少的程式碼及關鍵字來實際我們所要表達的核心功能，這才是這裡的核心，其他的東西我們可以從其他書本上學到。

所謂的繼承，

``` javascript
var Chinese=function(){
	this.country="China";
}

var Person=function(name,weight,height){
	this.name=name;
	this.weight=weight;
	this.height=height;
	this.futrue=function(){
		return "future";
	}
}
Chinese.prototype=new Person();

var phodal=new Chinese("phodal",50,166);
document.write(phodal.country);
```

完整的 JavaScript 應該由下列三個部分組成:

 - 核心(ECMAScript)——核心語言功能
 - 文件物件模型(DOM)——訪問和操作網頁內容的方法和介面
 - 瀏覽器物件模型(BOM)——與瀏覽器互動的方法和介面

我們在上面講的都是 ECMAScript，也就是語法相關的，但是 JS 真正強大的，或者說我們最需要的可能就是對 DOM 的操作，這也就是為什麼 jQuery 等庫可以流行的原因之一，而核心語言功能才是真正在哪裡都適用的，至於 BOM，真正用到的機會很少，因為沒有完善的統一的標準。

一個簡單的 DOM 示例,

``` html
<!DOCTYPE html>
<html>
<head>
</head>
<body>
	<noscript>
		disable Javascript
	</noscript>
	<p id="para" style="color:red">Red</p>
</body>
	<script type="text/javascript" src="app.js"></script>
</html>
```

我們需要修改一下 helloworld.html 新增

```HTML
<p id="para" style="color:red">Red</p>
```

同時還需要將 script 標籤移到 body 下面，如果沒有意外的話我們會看到頁面上用紅色的字型顯示 Red，修改 app.js。

``` javascript
var para=document.getElementById("para");
para.style.color="blue";
```

接著，字型就變成了藍色，有了 DOM 我們就可以對頁面進行操作，可以說我們看到的絕大部分的頁面效果都是通過 DOM 操作實現的。

####美妙之處

這裡說到的 JavaScript 僅僅只是其中的一小小部分，忽略掉的東西很多，只關心的是如何去設計一個實用的 app，作為一門程式語言，它還有其他強大的內製函數，要學好需要一本有價值的參考書。這裡提到的只是其中不到20%的東西，其他的80%或者更多會在你解決問題的時候出現。

 - 我們可以建立一個物件或者函數，它可以包含基本值、物件或者函數。
 - 我們可以用 JavaScript 修改頁面的屬性，雖然只是簡單的示例。
 - 我們還可以去解決實際的程式設計問題。

前端與後臺
===

> 前端 Front-end 和後端 Back-end 是描述程序開始和結束的通用詞彙。前端作用於採集輸入資訊，後端進行處理。

這種說法給人一種很模糊的感覺，但是他說得又很對，它負責視覺展示。在 MVC 或者 MVP 結構中，負責視覺顯示的部分只有 View 層，而今天大多數所謂的 View 層已經超越了 View 層。前端是一個很神奇的概念，但是而今的前端已經發生了很大的變化。你引入了 Backbone、Angluar，你的架構變成了 MVP、MVVM。儘管發生了一些架構上的變化，但是項目的開發並沒有因此而發生變化。這其中涉及到了一些職責的問題，如果某一個層級中有太多的職責，那麼它是不是加重了一些人的負擔？

後臺在過去的歲月裡起著很重要的作用，當然在未來也是。就最近幾年的解耦趨勢來看，它在變得更小，變成一系列的服務。並向前臺提供很多 RESTful API，看上去有點像提供一些輔助性的工作。

因此在這一章裡，我們將講述詳細介紹：

1. 後臺語言與選型
2. 前端框架與選型
3. 前端一致化，後臺服務化的趨勢
4. 前後端通訊

後臺語言選擇
---

如何選擇一門好的後臺語言似乎是大家都很感興趣的問題？大概只是因為他們想要在一開始的時候去學一門很實用的語言——至少會經常用到，而不是學好就被遺棄了。或者它不會因為一門新的語言的出現而消亡。

###JavaScript

在現在看來，JavaScript 似乎是一個價效比非常高的語言。只要是 Web 就會有前端，只要有前端就需要有 JavaScript。與此同時 Node.js 在後臺中的地位已經愈發重要了。

對於 JavaScript 來說，它可以做很多類型的應用。這些應用都是基於瀏覽器來執行的，有：

 - Electron + Node.js + JavaScript 做桌面應用
 - Ionic + JavaScript 做移動應用
 - Node.js + JavaScript 網站前後臺
 - JavaScript + Tessl 做硬體

So，這是一門很有應用前景的語言。

###Python

Python 誕生得比較早，其語言特性——做事情只有一件方法，也決定了這門語言很簡單。在 ThoughtWorks University 的學習過程中，接觸了一些外國小夥伴，這是大多數人學習的第一門語言。

Python 在我看來和 JavaScript 是相當划算的語言，除了它不能在前端執行，帶來了一點劣勢。Python 是一門簡潔的語言，而且有大量的數學、科學工具，這意味著在不遠的將來它會發揮更大的作用。我喜歡在我的各種小項目上用 Python，如果不是因為我對前端及資料視覺化更感興趣，那麼Python 就是我的第一語言了。

###Java

除此呢，我相信 Java 在目前來說也是一個不錯的選擇。

在學校的時候，一點兒也不喜歡 Java。後來才發現，我從 Java 上學到的東西比其他語言上學得還多。如果 Oracle 不毀壞 Java，那麼他會繼續存活很久。我可以用 JavaScript 造出各種我想要的東西，但是通常我無法保證他們是優雅的實現。過去人們在 Java 上花費了很多的時間，或在架構上，或在語言上，或在模式上。由於這些投入，都給了人們很多的啟發。這些都可以用於新的語言，新的設計，畢竟沒有什麼技術是獨立於舊的技術產生出來的。

###PHP

PHP 呢，據說是這個『世界上最好的語言』，我伺服器上執行著幾個不同的 WordPress 例項。對於這門語言，我還是相當放心的。並且這門語言由於上手簡單，同時國內有大量的程式設計師已經掌握好了這門語言。不得不提及的是 WordPress 已經佔領了 CMS 市場超過一半的份額，並且它也佔領了全球網站的四分之一。還有 Facebook，這個世界上最大的 PHP 站點也在使用這門語言。

###其他

個人感覺 Go 也不錯，雖然沒怎麼用，但是效能應該是相當可以的。

Ruby、Scala，對於寫程式碼的人來說，這是非常不錯的語言。但是如果是團隊合作時，就有待商榷。

MVC
---

人們在不斷地反思這其中複雜的過程，整理了一些好的架構模式，其中不得不提到的是我司 Martin Fowler 的《企業應用架構模式》。該書中文譯版出版的時候是2004年，那時對於系統的分層是

層次	   | 職責
-------| -----
表現層  | 	提供服務、顯示資訊、使用者請求、HTTP請求和命令列呼叫。
領域層  | 	邏輯處理，系統中真正的核心。
資料層  | 	與資料庫、訊息系統、事物管理器和其他軟體包通訊。

化身於當時最流行的 Spring，就是 MVC。人們有了 iBatis 這樣的資料持久層框架，即 ORM，物件關係對映。於是，你的 package 就會有這樣的幾個資料夾：

```
|____mappers
|____model
|____service
|____utils
|____controller
```

在 mappers 這一層，我們所做的莫過於如下所示的資料庫相關查詢：

```java
@Insert(
        "INSERT INTO users(username, password, enabled) " +
                "VALUES (#{userName}, #{passwordHash}, #{enabled})"
)
@Options(keyProperty = "id", keyColumn = "id", useGeneratedKeys = true)
void insert(User user);
```

model 資料夾和 mappers 資料夾都是資料層的一部分，只是兩者間的職責不同，如：

```java
public String getUserName() {
    return userName;
}

public void setUserName(String userName) {
    this.userName = userName;
}
```

而他們最後都需要在 Controller，又或者稱為 ModelAndView 中處理：

```java
@RequestMapping(value = {"/disableUser"}, method = RequestMethod.POST)
public ModelAndView processUserDisable(HttpServletRequest request, ModelMap model) {
    String userName = request.getParameter("userName");
    User user = userService.getByUsername(userName);
    userService.disable(user);
    Map<String,User> map = new HashMap<String,User>();
    Map <User,String> usersWithRoles= userService.getAllUsersWithRole();
    model.put("usersWithRoles",usersWithRoles);
    return new ModelAndView("redirect:users",map);
}
```

在多數時候，Controller 不應該直接與資料層的一部分，而將業務邏輯放在 Controller 層又是一種錯誤，這時就有了 Service 層，如下圖：

![Service MVC](assets/article/chapter2/service-mvc.png)

Domain（業務）是一個相當複雜的層級，這裡是業務的核心。一個合理的 Controller 只應該做自己應該做的事，它不應該處理業務相關的程式碼：

我們在 Controller 層應該做的事是：

1. 處理請求的參數
2. 渲染和重定向
3. 選擇 Model 和 Service
4. 處理 Session 和 Cookies

業務是善變的，昨天我們可能還在和對手競爭誰先推出新功能，但是今天可能已經合併了。我們很難預見業務變化，但是我們應該能預見 Controller 是不容易變化的。在一些設計裡面，這種模式就是 Command 模式。

###Model

> 模型用於封裝與應用程式的業務邏輯相關的資料以及對資料的處理方法。

它是介於資料與控制器之間的層級，擁有對資料直接訪問的權力——增刪改查(CRUD)。Web 應用中，資料通常是由資料庫來儲存，有時也會用搜尋引擎來儲存

因此在實現這個層級與資料庫互動時，可以使用 SQL 語句，也可以使用 ORM 框架。

SQL(Structured Query Language，即結構化查詢語言)， 語句是資料庫的查詢語言

ORM(Object Relational Mapping)，即物件關係對映，主要是將資料庫中的關係資料對映稱為程式中的物件。

###View

View 層在 Web 應用中，一般是使用模板引擎裝載對應 HTML。如下所示的是一段 JSP 程式碼：

```jsp
<html>
<head><title>First JSP</title></head>
<body>
  <%
    double num = Math.random();
    if (num > 0.95) {
  %>
      <h2>You'll have a luck day!</h2><p>(<%= num %>)</p>
  <%
    } else {
  %>
      <h2>Well, life goes on ... </h2><p>(<%= num %>)</p>
  <%
    }
  %>
  <a href="<%= request.getRequestURI() %>"><h3>Try Again</h3></a>
</body>
</html>
```

上面的 JSP 程式碼在經過程式解析、處理後，會變成相對應的 HTML。而我們可以發現在這裡的 View 層不僅僅只有模板的作用，還加入了部分的邏輯。我們可以在後面細細看這些問題，對於前端的 View 層來說，它可能是這樣的：

```html
<div class="information pure-g">
    {{#.}}
    <div class="pure-u-1 ">
        <div class="l-box">
            <h3 class="information-head"><a href="#/blog/{{slug}}" alt="{{title}}">{{title}}</a></h3>
            <p>
                釋出時間:<span>{{created}}</span>
            <p>
                {{{content}}}
            </p>

            </p>
        </div>
    </div>
    {{/.}}
</div>
```

在這裡的 View 層只是單純的一個顯示作用，這也是我們推薦的做法。業務邏輯應該儘可能的放置於業務層。

###Controller

> 控制器層起到不同層面間的組織作用，用於控制應用程式的流程。

###更多

在前後端解耦合的系統中，通常系統的架構模式就變成了 MVP，又或者是 MVVM。

![MVC、MVVM、MVP 對比](assets/article/chapter2/mvc-mvvm-mvp.png)

三者間很大的不同在於層級間的通訊模型、使用場景。

####MVP

> MVP 是從經典的模式 MVC 演變而來，它們的基本思想有相通的地方：Controller/Presenter 負責邏輯的處理，Model 提供資料，View 負責顯示。

####MVVM

MVVM 是 Model-View-ViewModel 的簡寫。相比於MVC悠久的歷史來說，MVVM 是一個相當新的架構，它最早於2005年被由的 WPF 和Silverlight 的架構師 John Gossman 提出，並且應用在微軟的軟體開發中。而 MVC 已經被提出了二十多年了，可見兩者出現的年代差別有多大。

MVVM 在使用當中，通常還會利用雙向繫結技術，使得 Model 變化時，ViewModel 會自動更新，而 ViewModel 變化時，View 也會自動變化。所以，MVVM 模式有些時候又被稱作：model-view-binder 模式。

後臺即服務
---

> BaaS（Backend as a Service）是一種新型的雲服務，旨在為移動和 Web 應用提供後端雲服務，包括雲端資料/檔案儲存、賬戶管理、訊息推送、社交媒體整合等。

產生這種服務的主要原因之一是因為移動應用的流行。在移動應用中，我們實際上只需要一個 API 介面來連線資料庫，並作一些相應的業務邏輯處理。對於不同的應用產商來說，他們打造 API 的方式可能稍有不同，然而他們都只是將後臺作為一個服務。

在一些更特殊的例子裡，即有網頁版和移動應用端，他們也開始使用同一個 API。前端作為一個單頁面的應用，或者有後臺渲染的應用。其架構如下圖所示：

![Backend As A Service](assets/article/chapter2/baas-diagram.png)

###API 演進史

在早期的工作中，我們會將大量的業務邏輯放置到 View 層——如迭代出某個結果。

而在今天，當我們有大量的邏輯一致時，我們怎麼辦，重複實現三次？

如下所示是筆者之前重構的系統的一個架構縮圖：

![重複邏輯的系統架構](assets/article/chapter2/duplicate-business-logic.png)

上面系統產生的主要原因是：技術本身的演進所造成的，並非是系統在一開始沒有考慮到這個問題。

![API 演進史](assets/article/chapter2/api-history.png)

從早期到現在的網際網路公司都有這樣的問題，也會有同樣的過程：

第一階段： 因為創始人對於某個領域的看好，他們就建立了這樣的一個桌面網站。這個時間點，大概可以在2000年左右。

第二階段： 前“智慧手機”出現了，人們需要開發移動版本的網站來適用使用者的需要。由於當時的開發環境，以及技術條件所限，網站只會是桌面模板的簡化。這時還沒有普及 Ajax 請求、SPA 這些事物。

第三階段： 手機應用的製作開始流行起來了。由於需要製作手機應用，人們就需要在網站上建立 API。由於當時的業務或者項目需求，這個 API 是直接耦合在系統中的。

第四階段： 由於手機效能的不斷提高，並且行動網路速度不斷提升，人們便開始在手機上製作單頁面應用。

由於他們使用的是相同業務邏輯、程式碼邏輯相同而**技術棧不同**的程式碼，當有一個新的需求出現時，他們需要重複多次實現，如下圖所示：

![重複業務邏輯的系統架構](assets/article/chapter2/duplicate-business-logic-with-domain.png)

隨後——也就是今天，各種新的解決方案出現了，如 React、混合應用、原生 + Web 的混合式應用、他們的目的就是解決上述的問題。不過，這些解決方案只是為了解決在前端中可能出現的問題，詳細的內容可以見《前端演進史》。

而人們也藉此機會在統一後臺——因為我們可以藉助於混合應用或混合式應用（即原生 + 內嵌 WebView，可以同時解決效能和跨平臺問題）統一移動端，藉助於響應式設計的理念可以統一桌面、平板和手機端。

因此，我們需要的就只是這樣的一個 API：

![One API](assets/article/chapter2/one-api.png)

###後臺即服務

現在，讓我們來看看一個採用後臺即服務的網站架構會是怎樣的？

資料持久化
---

資訊源於資料，我們在網站上看到的內容都應該是屬於資訊的範疇。這些資訊是應用從資料庫中根據業務需求查詢、過濾出來的資料。

資料通常以檔案的形式儲存，畢竟檔案是儲存資訊的基本單位。只是由於業務本身對於 Create、Update、Query、Index 等有不同的組合需求就引發了不同的資料儲存軟體。

如上章所說，View 層直接從 Model 層取資料，無遺也會暴露資料的模型。作為一個前端開發人員，我們對資料的操作有三種類型：

1. 資料庫。由於 Node.js 在最近幾年裡發展迅猛，越來越多的開發者選擇使用 Node.js 作為後臺語言。這與傳統的 Model 層並無多大不同，要麼直接操作資料庫，要麼間接操作資料庫。即使在 NoSQL 資料庫中也是如此。
2. 搜尋引擎。對於以查詢為主的領域來說，搜尋引擎是一個更好的選擇，而搜尋引擎又不好直接向 View 層暴露介面。這和招聘資訊一樣，都在暴露公司的技術棧。
3. RESTful。RESTful 相當於是 CRUD 的衍生，只是傳輸介質變了。
4. LocalStorage。LocalStorage 算是另外一種方式的 CRUD。

說了這麼多都是廢話，他們都是可以用類 CRUD 的方式操作。

###檔案儲存

通常來說，以這種方式儲存最常見的方式是 log(日誌)，如 Nginx 的 access.log。像這樣的檔案就需要一些專業的軟體，如 GoAccess、又或者是 Hadoop、Spark 來做對應的事。

在資料庫出現之前，人們都是使用檔案來儲存資料的。資料以檔案為單位儲存在硬碟上，並且這些檔案不容易一起管理、修改等等。如下圖所示的是我早期儲存檔案的一種方式：

```
├── 3.12
│   ├── cover.png
│   └── favicon.ico
└── 3.13
    └── template.tex
```

每天我們都會修改、檢視大量的不同類型的檔案。而由於工作繁忙，我們可能沒有辦法一一地去分類這些檔案。有時選擇的便是，優先先按日期把檔案一劃分，接著再在隨後的日子裡歸檔。而這種儲存方式大量的依賴於人來索引的工作，在很多時候往往顯得不是很靠譜。並且當我們將資料儲存進去後，往往很難進行修改。大量的 Log 檔案就需要專門的工作來分析和使用，依賴於人來解析這些日誌往往顯得不是很靠譜。這時我們就需要一些重量級的工具，如用 Logstash、ElasticSearch、Kibana 來處理 Nginx 訪問日誌。

而對於那些非專業人員來說，使用 Excel 這樣的工具往往顯得比較方便。他們不需要去操作資料庫，也不需要專業的知識來處理這些知識。只是從某種意義上來說，Excel 應該歸屬於資料庫的範疇。

###資料庫

當我們開始一個 Web 應用的時候，如建立一個使用者管理系統，我們就需要不斷對檔案進行查詢、修改、插入和刪除等操作。不僅如此，我們還需要定義資料之間的關係，如這個使用者對應這個密碼。在一些更復雜的情況下，我們還需要尋找這些使用者中對應的一些操作資料等等。如果還是將這些工作交給檔案來處理，那麼我們便是在向自己挖坑。

> 資料庫，簡單來說可視為電子化的檔案櫃——儲存電子檔案的處所，使用者可以對檔案中的資料執行新增、擷取、更新、刪除等操作。

在操作庫的時候，我們會使用到一名為 SQL（英語：Structural Query Language，中文： 結構化查詢語言）的領域特定語言來對資料進行操作。

> SQL 是高階的非過程化程式語言，它允許使用者在高層資料結構上工作。它不要求使用者指定對資料的存放方法，也不需要使用者瞭解其具體的資料存放方式。

資料庫裡儲存著大量的資料，在我們對系統建模的時候，也在決定系統的基礎模型。

####ORM

在傳統 SQL 資料庫中，我們可能會依賴於 ORM，也可能會自己寫 SQL。在使用 ORM 框架時，我們需要先定義 Model，如下是 Node.js 的 ORM 框架 Sequelize 的一個示例：

```javascript
var User = sequelize.define('user', {
  firstName: {
    type: Sequelize.STRING,
    field: 'first_name'
  },
  lastName: {
    type: Sequelize.STRING
  }
}, {
  freezeTableName: true
});

User.sync({force: true}).then(function () {
  // Table created
  return User.create({
    firstName: 'John',
    lastName: 'Hancock'
  });
});
```

上面定義的 Model，在程式初始化的時候將會建立相應的資料庫欄位。並且會建立一個 firstName 為 'John'，lastName 為 'Hancock' 的使用者。而這個過程中，我們並不需要操作資料庫。

像 MongoDB 這類的資料庫，也存在資料模型，但說的卻是嵌入子文件。在業務量大的情況下，資料庫在考驗公司的技術能力，想想便覺得 Amazon RDS 挺好的。

###搜尋引擎

儘管百科上對於搜尋引擎的定義是這樣的：

> 搜尋引擎指自動從因特網蒐集資訊，經過一定整理以後，提供給使用者進行查詢的系統。

但是這樣描述並不是非常準確，因為有相當多的網站採用了搜尋引擎作為基礎的儲存服務架構，而且他們並非自動從網際網路上搜尋資訊。搜尋引擎應該分成三個部分來組成：

1. 索引服務
2. 搜尋服務
3. 索引資料

索引服務用於將資料儲存到索引資料中，而搜尋服務正是搜尋引擎存在的意義。對於查詢條件複雜的網站來說，採用搜尋引擎就意味著減少了非常多的繁瑣資料處理事務。在一些架構中，人們用資料庫儲存資料，並使用工具來將資料注入到搜尋引擎中。

從架構上來說，使用搜尋引擎的優點是：分離儲存、查詢部分。從開發上來說，它可以讓我們更關注於業務本身的價值，而不是去實現這樣一個搜尋邏輯。

如下圖所示的 Lucene 應用的架構：

![Lucene 應用架構](assets/article/chapter2/lucene-arch.jpg)

可以從圖中看到系統明顯被劃分成兩部分：

1. Index Documents。索引文件部分，將用於儲存資料到檔案系統中。
2. Search Index。搜尋部分，用於查詢相應的資料。

前端框架選擇
---

選擇前端框架似乎是一件很難的事，然而這件事情並不是看上去那麼難。只是有時候你只想追隨潮流，或者因為你在技術選型受到一些影響。但是總的來說，選擇一個框架並不是一件很難的事。同時也不是一件非常重要的事，因為框架本身是相通的。如果我們不盡量去解耦系統，那麼選擇什麼框架也都是一樣的。

###Angular

AngularJS 對於後端人員寫前端程式碼來說，是一個非常不錯的選擇。Angular 框架採用並擴充套件了傳統 HTML，通過雙向的資料繫結來適應動態內容，雙向的資料繫結允許模型和檢視之間的自動同步。

並且類似於 Ionic 這樣的混合框架，也將 Ionic 帶到了移動應用的領域。

###React

React 似乎很受市場歡迎，各種各樣的新知識——虛擬 DOM、JSX、Component 等等。React 只是我們在上面章節裡說到的 View 層，而這個 View 層需要輔以其他框架才能完成更多的工作。

並且 React 還有一個不錯的殺手鐗——React Native，雖然這個框架還在有條不紊地挖坑中，但是這真的是太爽了。以後我們只需要一次開發就可以多處執行了，再也沒有比這更爽的事情發生了。

###Vue

Vue.js 是一個輕量級的前端框架。它是一個更加靈活開放的解決方案。它允許你以希望的方式組織應用程式，你可以將它嵌入一個現有頁面而不一定要做成一個龐大的單頁應用。

###jQuery 系

jQuery 還是一個不錯的選擇，不僅僅對於學習來說，而且對於工作來說也是如此。如果你們不是新起一個項目或者重構舊的項目，那麼必然你是沒有多少機會去超越 DOM。而如果這時候嘗試去這樣做會付出一定的代價，如我在前端演進史所說的那樣——晚點做出選擇，可能會好一點。

因為誰說 jQuery 不會去解放 DOM，React 帶來的一些新的思想可能就比不上它的缺點。除此，jQuery 耕織幾年的生態系統也是不可忽略。

####Backbone + Zepto + Mustache

這是前幾年（今年2016）的一個技術方向，今天似乎已經不太常見了。在這種模式下，人們使用 Backbone 來做一些路由、模型、檢視、集合方面的工作，而由 jQuery 的相容者 Zepto 來負責對 DOM 的處理，而 Mustache 在這裡則充當模板系統的工作。

前臺與後臺互動
---

在我們把後臺服務化後，前端跨平臺化之前，我們還需要了解前臺和後臺之間怎麼通訊。從現有的一些技術上來看，Ajax 和 WebSocket 是比較受歡迎的。

###Ajax

AJAX 即 “Asynchronous JavaScript And XML”（非同步 JavaScript 和 XML），是指一種建立互動式網頁應用的網頁開發技術。這個功能在之前的很多年來一直被 Web 開發者所忽視，直到 Gmail、Google Suggest 和 Google Maps 的出現，才使人們開始意識到其重要性。通過在後臺與伺服器進行少量資料交換，AJAX 可以使網頁實現非同步更新。這意味著可以在不重新載入整個網頁的情況下，對網頁的某部分進行更新。傳統的網頁如果需要更新內容，必須過載整個網頁頁面。

![Ajax 請求](assets/article/chapter2/ajax_request.png)

說起 Ajax，我們就需要用 JavaScript 向伺服器傳送一個 HTTP 請求。這個過程要從 XMLHttpRequest 開始說起，它是一個 JavaScript 物件。它最初由微軟設計，隨後被 Mozilla、Apple 和 Google 採納。如今，該物件已經被 W3C 組織標準化。

如下的所示的是一個 Ajax 請求的示例程式碼：

```javascript
var xhr = new XMLHttpRequest();
xhr.onreadystatechange = function() {
    if (xhr.readyState == XMLHttpRequest.DONE) {
        alert(xhr.responseText);
    }
}
xhr.open('GET', 'http://example.com', true);
xhr.send(null);
```

我們只需要簡單的建立一個請求物件例項，開啟一個 URL，然後傳送這個請求。當傳輸完畢後，結果的 HTTP 狀態以及返回的響應內容也可以從請求物件中獲取。

而這個返回的內容可以是多種格式，如 XML 和 JSON，但是從近年的趨勢來看，XML 基本上已經很少看到了。這裡我們以 JSON 為主，來簡單地介紹一下返回資料的解析。

###JSON

> JSON(JavaScript Object Notation) 是一種輕量級的資料交換格式。它基於 ECMAScript 的一個子集。 JSON採用完全獨立於語言的文字格式，但是也使用了類似於 C 語言家族的習慣（包括 C、C++、C#、Java、JavaScript、Perl、Python等）。這些特性使 JSON 成為理想的資料交換語言。易於人閱讀和編寫，同時也易於機器解析和生成(一般用於提升網路傳輸速率)。

####XML VS JSON

JSON 格式的資料具有以下的一些特點：

 - 容易閱讀
 - 解析速度更快
 - 佔用空間更少

如下所示的是一個簡單的對比過程：

```javascript
myJSON = {"age" : 12, "name" : "Danielle"}
```

如果我們要取出上面數值中的age，那麼我們只需要這樣做：

```javascript
anObject = JSON.parse(myJSON);
anObject.age === 12 // True
```

同樣的，對於 XML 來說，我們有下面的格式:

```
<person>
    <age>12</age>
    <name>Danielle</name>
</person>
```

而如果我們要取出上面資料中的age的值，他將是這樣的：

```javascript
myObject = parseThatXMLPlease();
thePeople = myObject.getChildren("person");
thePerson = thePeople[0];
thePerson.getChildren("age")[0].value() == "12" // True
```

對比一下，我們可以發現XML的資料不僅僅解析上比較麻煩，而且還繁瑣。

####JSON WEB Tokens

> JSON Web Token (JWT) 是一種基於 token 的認證方案。

在人們大規模地開始 Web 應用的時候，我們在授權的時候遇到了一些問題，而這些問題不是 Cookie 所能解決的。Cookie 存在一些明顯的問題：不支援跨域、並且不是無狀態的、不能使用CDN、與系統耦合等等。除了解決上面的問題，它還可以提高效能等等。基於 Session 的授權機制需要服務端來儲存這個狀態，而使用 JWT 則可以跳過這個問題，並且使我們設計出來的 API 滿足 RESTful 規範。即，我們 API 的狀態應該是沒有狀態的。因此人們提出了 JWT 來解決這一系列的問題。

通過 JWT 我們可以更方便地寫出適用於前端應用的認證方案，如登陸、註冊這些功能。當我們使用 JWT 來實現我們的註冊、登陸功能時，我們在登陸的時候將向伺服器傳送使用者名稱和密碼，伺服器驗證後將生成對應的 Token。在下次我們進行頁面操作的時候，如訪問 /Dashboard 時，發出的 HTTP 請求的 Header 中會包含這個 Token。伺服器在接收到請求後，將對這個 Token 進行驗證並判斷這個 Token 是否已經過期了。

![JWT 流程](assets/article/chapter2/jwt-process.jpeg)

需要注意的一點是：在使用 JWT 的時候也需要注意安全問題，在允許的情況下應該使用 HTTPS 協議。

###WebSocket

在一些網站上為了實現推送技術，都採用了輪詢的技術。即在特定的時間間隔裡，由瀏覽器向伺服器發出 HTTP 請求，然後瀏覽器便可以從伺服器獲取最新的訊息。如下圖所示的是 Google Chrome 申請開發者賬號時發出的對應的請求：

![Chrome Ajax 輪詢](assets/article/chapter2/chrome-ajax-poll.jpg)

從上圖中我們可以看到，Chrome 的前臺正在不斷地向後臺查詢 API 的結果。由於瀏覽器需要不斷的向伺服器發出請求，而 HTTP 的 Header 是非常長的，即使是一個很小的資料也會佔用大量的頻寬和伺服器資源。為了解決這個問題，HTML5 推出了一種在單個 TCP 連線上進行全雙工通訊的協議WebSocket。

WebSocket 可以讓客戶端和伺服器之間存在持久的連線，而且雙方都可以隨時開始傳送資料。

編碼
===

在我們真正開始去寫程式碼之前，我們可能會去考慮一些事情。怎麼去規劃我們的任務，如何去細分這個任務。

1. 如果一件事可以自動化，那麼就儘量去自動化，畢竟你是一個程式設計師。
2. 快捷鍵！快捷鍵！快捷鍵！
3. 使用可以幫助你快速工作的工具——如啟動器。

不過不得不提到的一點是：你需要去考慮這個需求是不是一個坑的問題。如果這是一個坑，那麼你應該儘早的去反饋這個問題。溝通越早，成本越低。

編碼過程
---

整個程式設計的過程如下圖所示：

![編碼過程](assets/article/chapter3/coding.png)

步驟如下所示：

1. Kick Off。在這個步驟中，我們要詳細地瞭解我們所需要做的東西、我們的驗收條件是什麼、我們需要做哪些事情。
2. Tasking。**簡單**的規則一下，我們需要怎麼做。一般來說，如果是結對程式設計的話，還會記錄下來。
3. 最新的程式碼。對於使用 Git 來管理項目的團隊來說，在一個任務剛開始的時候應該保證本地的程式碼是最新的。
4. Test First。測試優先是一個很不錯的實踐，可以保證我們寫的程式碼的健壯，並且函數儘可能小，當然也會有測試。
5. Code。就是實現功能，一般人都知道。
6. 重構。在我們實現了上面兩步之後，我們還需要重構程式碼，使我們的程式碼更容易閱讀、更易懂等等。
7. 提交程式碼。這裡的提交程式碼只是本地的提交程式碼，因此都提倡在本地多次提交程式碼。
8. 執行測試。當我們完成我們的任務後，我們就可以準備 PUSH 程式碼了。在這時，我們需要在本地執行測試——以保證我們不破壞別人的功能。
9. PUSH 程式碼。
10. 等 CI 測試通過。如果這時候 CI 是掛的話，那麼我們就需要再修 CI。這時其他的人就沒有理由 PUSH 程式碼，如果他們的程式碼也是有問題的，這隻會使情況變得愈加複雜。

不過，在最開始的時候我們要了解一下如何去搭建一個項目。

Web 應用的構建系統
---

> 構建系統(build system)是用來從原始碼生成使用者可以使用的目標的自動化工具。目標可以包括庫、可執行檔案、或者生成的指令碼等等。

常用的構建工具包括 GNU Make、GNU autotools、CMake、Apache Ant（主要用於JAVA）。此外，所有的整合開發環境（IDE）比如 Qt Creator、Microsoft Visual Studio 和 Eclipse 都對他們支援的語言新增了自己的構建系統配置工具。通常 IDE 中的構建系統只是基於控制檯的構建系統（比如 Autotool 和 CMake ）的前端。

對比於 Web 應用開發來說，構建系統應該還包括應用打包（如 Java 中的 Jar 包，或者用於部署的 RPM 包）、原始碼分析、測試覆蓋率分析等等。

###Web 應用的構建過程

在剛建立項目的時候，我們都會有一個完整的構建思路。如下圖便是這樣的一個例子：

![構建過程](assets/article/chapter3/build-web-project.png)

這是一個後臺語言用的是 Java，前臺語言用的是 JavaScript 項目的構建流程。

**Compile**。對於那些不是用瀏覽器的前端項目來說，如 ES6、CoffeeScript，他們還需要將程式碼編譯成瀏覽器使用的 JavaScript 版本。對於 Java 語言來說，他需要一個編譯的過程，在這個編譯的過程中，會檢查一些語法問題。

**Check Style**。通常我們會在我們的項目裡定義一些程式碼規範，如 JavaScript 中的使用兩個空格的縮排，Java 的 Checkstyle 中一個函數不能超過30行的限制。

**單元測試**。作為測試中最基礎也是最快的測試，這個測試將集中於測試單個函數的是不是正確的。

**功能測試**。功能測試的意義在於，保證一個功能依賴的幾個函陣列合在一起也是可以工作的。

**Mock Server**。當我們的程式碼依賴於第三方服務的時候，我們就需要一個 Mock Server 來保證我們的功能程式碼可以獨立地測試。

**整合測試**。這一步將整合前臺、後臺，並且執行起最後將上線的應用。接著依據於使用者所需要的功能來編寫相應的測試，來保證一個個的功能是可以工作的。

**打包**。對於部署來說，直接安裝一個 RPM 包，或者 DEB 包是最方便的事。在這個包裡會包含應用程式所需的所有二進位制檔案、資料和配置檔案等等。

**上傳包**。在完成打包後，我們就可以上傳這個軟體包了。

**部署**。最後，我們就可以在我們的線上環境中安裝這個軟體包。

###Web 應用的構建實戰

下面就讓我們來構建一個簡單的 Web 應用，來實踐一下這個過程。在這裡，我們要使用到的一個工具是 Gulp，當然對於 Grunt 也是類似的。

####Gulp 入門指南

> Gulp.js 是一個自動化構建工具，開發者可以使用它在項目開發過程中自動執行常見任務。Gulp.js 是基於 Node.js 構建的，利用 Node.js 流的威力，你可以快速構建項目並減少頻繁的 IO 操作。Gulp.js 原始檔和你用來定義任務的 Gulp 檔案都是通過 JavaScript（或者 CoffeeScript ）源碼來實現的。

1. 全局安裝 gulp：

```bash
$ npm install --global gulp
```

2. 作為項目的開發依賴（devDependencies）安裝：

```bash
$ npm install --save-dev gulp
```

3. 在項目根目錄下建立一個名為 gulpfile.js 的檔案：

```javascript
var gulp = require('gulp');

gulp.task('default', function() {
  // 將你的預設的任務程式碼放在這
});
```

4. 執行 gulp：

```bash
$ gulp
```

預設的名為 default 的任務（task）將會被執行，在這裡，這個任務並未做任何事情。接下來，我們就可以打造我們的應用的構建系統了。

####程式碼質量檢測工具

當 C 還是一門新型的程式語言時，還存在一些未被原始編譯器捕獲的常見錯誤，所以程式設計師們開發了一個被稱作 lint 的配套項目用來掃描原始檔，查詢問題。

對應於不同的語言都會有不同的 lint 工具，在 JavaScript 中就有 JSLint。JavaScript 是一門年輕、語法靈活多變且對格式要求相對鬆散的語言，因此這樣的工具對於這門語言來說比較重要。

2011年，一個叫 Anton Kovalyov 的前端程式設計師藉助開源社羣的力量弄出來了 JSHint，其思想基本上和 JSLint 是一致的，但是其有一下幾項優勢：

 - 可配置規則，每個團隊可以自己定義自己想要的程式碼規範。
 - 對社羣非常友好，社羣支援度高。
 - 可定製的結果報表。

下面就讓我們來安裝這個軟體吧：

**安裝及使用**

```bash
npm install jshint gulp-jshint --save-dev
```

示例程式碼:

```javascript
var jshint = require('gulp-jshint');
var gulp   = require('gulp');

gulp.task('lint', function() {
  return gulp.src('./lib/*.js')
    .pipe(jshint())
    .pipe(jshint.reporter('YOUR_REPORTER_HERE'));
});
```

####自動化測試工具

一般來說，自動測試應該從兩部分考慮：

 - 單元測試
 - 功能測試

Mocha 是一個可以執行在 Node.js 和瀏覽器環境裡的測試框架，

```
var gulp = require('gulp');
var mocha = require('gulp-mocha');

gulp.task('default', function () {
	return gulp.src('test.js', {read: false})
		// gulp-mocha needs filepaths so you can't have any plugins before it
		.pipe(mocha({reporter: 'nyan'}));
});
```

####編譯

對於靜態型語言來說，編譯是一個很重要的步驟。不過，對於動態語言來說也存在這樣的工具。

**動態語言的編譯**

可以說這類型的語言，是以我們常見的 JavaScript 為代表。

1. CoffeeScript 是一套 JavaScript 的轉譯語言，並且它增強了 JavaScript 的簡潔性與可讀性。

2. Webpack 是一款模組載入器兼打包工具，它能把各種資源，例如 JS（含JSX）、coffee、樣式（含less/sass）、圖片等都作為模組來使用和處理。

3. Babel 是一個轉換編譯器，它能將 ES6 轉換成ES5，以便在較低版本的瀏覽器中正確執行。

####打包

在 GNU/Linux 系統的軟體包裡通過包含了已壓縮的軟體檔案集以及該軟體的內容資訊。常見的軟體包有

1. DEB。Debian 軟體包格式，副檔名為 .deb
2. RPM（原 Red Hat Package Manager，現在是一個遞迴縮寫）。該軟體包分為二進位制包（Binary）、原始碼包（Source）和 Delta 包三種。二進位制包可以直接安裝在計算機中，而原始碼包將會由 RPM 自動編譯、安裝。原始碼包經常以 src.rpm 作為字尾名。
3. 壓縮文件 tar.gz。通常是該軟體的源碼，故而在安裝的過程中需要編譯、安裝，並且在編譯時需要自己手動安裝所需要依賴的軟體。在軟體倉庫沒有最新版本的軟體時，tar.gz 往往是最好的選擇。

由於這裡的打包過程比較繁瑣，就不介紹了。有興趣的讀者可以自己瞭解一下。

####上傳及釋出包

上傳包之前我們需要建立一個相應的檔案伺服器，又或者是相應的軟體源。並且對於我們的產品環境的伺服器來說，我們還需要指定好這個軟體源才能安裝這個包。

以 Ubuntu 為例，Ubuntu 裡的許多應用程式軟體包，是放在網路裡的伺服器上，這些伺服器網站，就稱作“源”，從源裡可以很方便地獲取軟體包。

因而在這一步中，我們所需要做的事便是將我們打包完的軟體上傳到相應的伺服器上。

Git 與版本控制
---

###版本控制

> 版本控制是一種記錄一個或若干檔案內容變化，以便將來查閱特定版本修訂情況的系統。

雖然基於 Git 的工作流可能並不是一個非常好的實踐，但是在這裡我們以這個工作流做為實踐來開展我們的項目。如下圖所示是一個基於 Git 的項目流：

![基於 Git 的工作流](assets/article/chapter3/gitflow.png)

我們日常會工作在 "develop" 分支（那條線）上，通常來說每個迭代我們會釋出一個新的版本，而這個新的版本將會直接上線到產品環境。那麼上線到產品環境的這個版本就需要打一個版本號——這樣不僅可以方便跟蹤我們的系統，而且當出錯的時候我們也可以直接回滾到上一個版本。如果在上線的時候有些 Bug 不得不去修復，並且由於上線的新功能很重要，我們就需要一些 Hotfix。而從整個過程來看，版本控制起了一個非常大的作用。

不僅僅如此，版本控制的最大重要是在開發的過程中扮演的角色。通過版本管理系統，我們可以：

1. 將某個檔案回溯到之前的狀態。
2. 將項目回退到過去某個時間點。
3. 在修改 Bug 時，可以檢視修改歷史，查出修改原因
4. 只要版本控制系統還在，你可以任意修改項目中的檔案，並且還可以輕鬆恢復。

常用的版本管理系統有 Git、SVN，但是從近年來看 Git 似乎更受市場歡迎。

###Git

從一般開發者的角度來看，Git 有以下功能：

1. 從伺服器上克隆資料庫（包括程式碼和版本資訊）到單機上。
2. 在自己的機器上建立分支，修改程式碼。
3. 在單機上自己建立的分支上提交程式碼。
4. 在單機上合併分支。
5. 新建一個分支，把伺服器上最新版的程式碼 fetch 下來，然後跟自己的主分支合併。
6. 生成補丁（patch），把補丁傳送給主開發者。
7. 看主開發者的反饋，如果主開發者發現兩個一般開發者之間有衝突（他們之間可以合作解決的衝突），就會要求他們先解決衝突，然後再由其中一個人提交。如果主開發者可以自己解決，或者沒有衝突，就通過。
8. 一般開發者之間解決衝突的方法，開發者之間可以使用 pull 命令解決衝突，解決完衝突之後再向主開發者提交補丁。

從主開發者的角度（假設主開發者不用開發程式碼）看，Git 有以下功能：

1. 檢視郵件或者通過其它方式檢視一般開發者的提交狀態。
2. 打上補丁，解決衝突（可以自己解決，也可以要求開發者之間解決以後再重新提交，如果是開源項目，還要決定哪些補丁有用，哪些不用）。
3. 向公共伺服器提交結果，然後通知所有開發人員。

####Git 初入

如果是第一次使用 Git，你需要設定署名和郵箱：

```
$ git config --global user.name "使用者名稱"
$ git config --global user.email "電子郵箱"
```

你可以在 [GitHub](https://github.com) 新建免費的公開倉庫或在 [Coding.net](https://coding.net) 新建免費的私有倉庫。

按照 [GitHub 的文件](https://help.github.com/articles/generating-an-ssh-key/) 或 [Coding.net 的文件](https://coding.net/help/doc/account/ssh-key.html) 配置 SSH Key，然後將程式碼倉庫 clone 到本地，其實就是將程式碼複製到你的機器裡，並交由 Git 來管理：

```
$ git clone git@github.com:username/repository.git
或
$ git clone git@git.coding.net:username/repository.git
```

或使用 HTTPS 地址進行 clone：

```
$ git clone https://username:password@github.com/username/repository.git
或
$ git clone https://username:password@git.coding.net/username/repository.git
```

你可以修改複製到本地的程式碼了（ symfony-docs-chs 項目裡都是 rst 格式的文件）。當你覺得完成了一定的工作量，想做個階段性的提交：

向這個本地的程式碼倉庫新增當前目錄的所有改動：

```
$ git add .
```

或者只是新增某個檔案：

```
$ git add -p
```

我們可以輸入

```
$ git status
```

來看現在的狀態，如下圖是新增之前的：

![Before add](assets/article/chapter3/before-add.png)

下面是新增之後 的

![After add](assets/article/chapter3/after-add.png)

可以看到狀態的變化是從黃色到綠色，即 unstage 到 add。

在完成新增之後，我們就可以寫入相應的提交資訊——如這次修改新增了什麼內容 、這次修改修復了什麼問題等等。在我們的工作流程裡，我們使用 Jira 這樣的工具來管理我們的項目，也會在我們的 Commit Message 裡寫上作者的名字，如下：

```
$ git commit -m "[GROWTH-001] Phodal: add first commit & example"
```

在這裡的``GROWTH-001``就相當於是我們的任務號，Phodal 則對應於使用者名稱，後面的提交資訊也會寫明這個任務是幹嘛的。

由於有測試的存在，在完成提交之後，我們就需要執行相應的測試來保證我們沒有破壞原來的功能。因此，我們就可以PUSH我們的程式碼到伺服器端：

```
$ git push
```

這樣其他人就可以看到我們修改的程式碼。

Tasking
---

初到 ThoughtWorks 時，Pair 時候總會有人教我如何開始編碼，這應該也是一項基礎的能力。結合日常，重新演繹一下這個過程：

1. 有一個明確的實現目標。
2. 評估目標並將其拆解成任務(TODO)。
3. 規劃任務的步驟(TODO)
4. 學習相關技能
5. 執行 Task，遇到難題就跳到第二步。

###如何 Tasking 一本書

以本文的寫作為例，細分上面的過程就是：

1. 我有了一箇中心思想——在某種意義上來說就是標題。
2. 依據中心思想我將這篇文章分成了四小節。
3. 然後我開始寫四小節的內容。
4. 直到完成。

而如果將其劃分到一個程式設計任務，那麼也是一樣的：

1. 我們想到做一個 xxx 的 idea。
2. 為了這個 idea 我們需要分成幾步，或者幾層設計。
3. 對於每一步，我們應該做點什麼
4. 我們需要學習怎樣的技能
5. 整合每一步的程式碼，就有了我們的系統。

現在讓我們以這本書的寫作過程為例，來看看這個過程是怎麼發生的。

在計劃寫一本書的時候，我們有關於這本書主題的一些想法。正是一些想法慢慢地凝聚成一個穩定的想法，不過這不是我們所要討論的重點。

當我們已經有了一本書的相關話題的時候，我們會打算去怎麼做？先來個頭腦風暴，在上面寫滿我們的一些想法，如這本書最開始劃分了這七步：

 - 從零開始
 - 編碼
 - 上線
 - 資料分析
 - 持續交付
 - 遺留系統
 - 回顧與新架構

接著，依據我們的想法整理出幾個章節。如本書最初的時候只有七個章節，但是我們還需要第一個章節來指引新手，因此變成了八個章節。對應於每一個章節，我們都需要想好每一章裡的內容。如在第一章裡，又可以分成不同的幾部分。隨後，我們再對每一部分的內容進行任務劃分，那麼我們就會得到一個又一個的小的章節。在每個小的章節裡，我們都可以大概策劃一下我們要寫的內容。

然後我們就可以開始寫這樣的一本書——由一節節匯聚成一章，由一章一章匯聚成一本。

###Tasking 開發任務

現在，讓我們簡單地來 Tasking 如何開發一個部落格。作為一個程式設計師，如果我們要去開始一個部落格系統的話，那麼我們會怎麼做？

1. 先規劃一下我們所需要的功能——如後臺、評論、Social 等等，並且我們還應該設計我們部落格的 Mockup。
2. 隨後我們就可以簡單地設計一下系統的架構，如傳統的前後端結合。
3. 我們就可以進行技術選型了——使用哪個後端框架、使用哪個前端框架。
4. 建立我們的 hello,world，然後開始進行一個功能的編碼工作。
5. 編碼時，我們就需要不斷地檢視、新增測試等等。
6. 完成一個個功能的時候，我們就會得到一個子模組。
7. 依據一個個子模組，我們就可以得到我們的部落格系統。

與我們日常開發一致的是：我們需要去劃分任務的優先順序。換句話來說，我們需要先實現我們的核心功能。

對於我們的部落格系統來說，最主要的功能就是發部落格、展示部落格。往簡單地說，一篇部落格應該有這麼基礎的四部分：

1. 標題
2. 內容
3. 作者
4. 時間
5. Slug

然後，我們就需要建立相應的 Model，根據這個 Model，我們就可以建立相應的控制器程式碼。再配置下路由，新增下頁面。對於有些系統來說，我們就可以完成部落格系統的展示了。

寫程式碼只是在碼字
---

程式設計這件事情實際上一點兒也不難，當我們只是在使用一個工具創造一些東西的時候，比如我們拿著電烙鐵、晶片、電線等去焊一個電路板的時候，我們學的是如何運用這些工具。雖然最後我們的電路板可以實現相同的功能，但是我們可以一眼看到差距所在。

換個貼切一點的比喻，比如燒菜做飯，對於一個優秀的廚師和一個像我這樣的門外漢而言，就算給我們相同的食材、廚具，一段時間後也許一份是誘人的美食，一份只能餵豬了——即使我模仿著廚師的步驟一步步地來，也許看上去會差不多，但是一吃便吃出差距了。

我們還做不好飯，還焊不好電路，還寫不好程式碼，很大程度上並不是因為我們比別人笨，而只是別人比我們做了更多。有時候一種機緣巧遇的學習或者 bug 的出現，對於不同的人的程式設計人生都會有不一樣的影響(ps:說的好像是蝴蝶效應)。我們只是在使用工具，使用的好與壞，在某種程式上決定了我們寫出來的質量。

寫字便是如此，給我們同樣的紙和筆(ps:減少無關因素)，不同的人寫出來的字的差距很大，寫得好的相比於寫得不好的 ，只是因為練習得更多。而程式設計難道不也是如此麼，最後寫程式碼這件事就和寫字一樣簡單了。

剛開始寫字的時候，我們需要去了解一個字的筆劃順序、字型結構，而這些因素相當於語法及其結構。熟悉了之後，寫程式碼也和寫字一樣是簡簡單單的事。

####學習程式設計只是在學造句

> ?多麼無聊的一個標題

``計算機語言同人類語言一樣``，有時候我們也許會感慨一些計算機語言是多麼地背離我們的世界，但是他們才是真正的計算機語言。

計算機語言是模仿人類的語言，從 if 到其他，而這些計算機語言又比人類語言簡單。故而一開始學習語言的時候我們只是在學習造句，用一句話來概括一句程式碼的意思，或者可以稱之為函數、方法(method)。

於是我們開始組詞造句，以便最後能拼湊出一整篇文章。

####程式設計是在寫作

> ?程式設計是在寫作，這是一個怎樣的玩笑?這是在諷刺那些寫不好程式碼，又寫不好文章的麼

程式碼如詩，又或者程式碼如散文。總的來說，這是相對於英語而言，對於中文而言可不是如此。**如果用一種所謂的中文語言寫出來的程式碼，不能像中文詩一樣，那麼它就算不上是一種真正的中文語言。**

那些所謂的寫作邏輯對程式設計的影響

 - 早期的程式碼是以行數算的，文章是以字數算的
 - 程式碼是寫給人看的，文章也是寫給人看的
 - 程式設計同寫作一樣，都由想法開始
 - 程式碼同文章一樣都可以堆砌出來(ps:如本文)
 - 寫出好的文章不容易，需要反覆琢磨，寫出好的程式碼不也是如此麼
 - 構造一個類，好比是構造一個人物的性格特點，多一點不行，少一點又不全
 - 程式碼生成，和生成詩一樣，沒有情感，過於機械化
 - 。。。

然而好的作家和一般的寫作者，區別總是很大，對同一個問題的思考程度也是不同的。從一個作者到一個作家的過程，是一個不斷寫作不斷積累的過程。而從一個普通的程式設計師到一個優秀的程式設計師也是如此，需要一個不斷程式設計的過程。

當我們開始真正去程式設計的時候，我們還會糾結於"**僧推月下門**"還是"**僧敲月下門**"的時候，當我們越來越熟練就容易決定究竟用哪一個。而這樣的“推敲”，無論在寫作中還是在程式設計中都是相似的過程。

> 寫作的過程真的就是一次探索之旅，而且它會貫穿人的一生。

因此：

> 程式設計只是在碼字，難道不是麼？

真正的想法都在腦子裡，而不在紙上，或者 IDE 裡。

內建索引與外接引擎
---

###入口網站

讓我們先來看看入口網站。

百科上說：

> 入口網站（英語：Web portal，又稱入口網站，入門網站）指的是將不同來源的資訊以一種整齊劃一的形式整理、儲存並呈現的網站

從某種意義上來說入口網站更適合那些什麼都不知道，從頭開始探索網際網路的人。換句話說，這有點於類似我們在學第一門計算機語言——我們不需要去尋找什麼，我們也不知道一些複雜的概念。

這時候我們只能隨便的看一本別人推薦的書籍，讀一讀別人寫的筆記，開始一點點構建我們的知識體系。

而在我們學習第二門計算機語言的時候，我們有了更多的訣竅——我們知道怎麼去搜尋。在我們的知識體系裡，我們知道如何去搜尋，這時我們就可以通過搜尋引擎來學習。

百科上大致將搜尋引擎分成了四部分：搜尋器、索引器、檢索器、使用者介面。

1. 搜尋器：其功能是在網際網路中漫遊，發現和蒐集資訊。
2. 索引器：其功能是理解搜尋器所搜尋到的資訊，從中抽取出索引項，用於表示文件以及生成文件庫的索引表。
3. 檢索器：其功能是根據使用者的查詢在索引庫中快速檢索文件，進行相關度評價，對將要輸出的結果排序，並能按使用者的查詢需求合理反饋資訊。
4. 使用者介面：其作用是接納使用者查詢、顯示查詢結果、提供個性化查詢項。

我想這部分大家都是有點印象的就不多介紹了(即：Ctrl + C, Ctrl + V)。

對於一個新手來說，使用搜尋引擎的最大障礙就是——你知道問題，但是你不知道怎麼搜尋。這也是為什麼，你會在那麼多的部落格、問答裡，看到如何使用搜尋引擎。

但是這並不能解決根本性問題——你需要知道你的問題是什麼。順便，推薦一本書叫做《你的燈亮著嗎？》

###內建索引與外接引擎

(ps: 為了和搜尋引擎對應起來，這裡就將內建門戶改成內建索引。)

所以，再仔細回到上面的問題裡。要成為一名可以完成任務的程式設計師，你就需要不斷地構建你的入口網站。我們要學習 Web 開發，我們就需要對整個知識體系有一個好的理解。不斷理解的過程中，我們就不斷也新增了新的文件，構建新的索引。每遇到一個新的知識點，我們就開始重新生成新的索引。

然後又會引入一個問題：

> 人的大腦如同一間空空的閣樓，要有選擇地把一些傢俱裝進去。

我們需要不斷地整理一些新的技術，並且想方設法地忘記舊的知識。

有時，不得不說筆記和部落格是這樣一個很好的載體。在未來的某一天，我們可以重新挖掘這些技術，識別技術的舊有缺陷，發展出新的技術——水能載舟，亦能覆舟。

如何編寫測試
---

寫測試相比於寫程式碼來說算是一件簡單的事。多數時候，我們並不需要考慮複雜的邏輯。我們只需要按照我們的程式碼邏輯，對程式碼的行為進行覆蓋。

需要注意的是——在不同的團隊、工作流裡，測試可能是會有不同的工作流程：

 - 開發人員寫單元測試、整合測試等等
 - 測試團隊通過介面來做黑盒測試
 - 測試人員手動測試來測試功能

在允許的情況下，測試應該由開發人員來編寫，並且是由底層開始寫測試。為了更好地去測試程式碼，我們需要了解測試金字塔。

###測試金字塔

測試金字塔是由 Mike Cohn 提出的，主要觀點是：底層單元測試應多於依賴 GUI 的高層端到端測試。其結構圖如下所示：

![測試金字塔](assets/article/chapter3/test-pyramid.png)

從結構上來說，上面的金字塔可以分成三部分：

1. 單元測試。
2. 服務測試
3. UI 測試

從圖中我們可以發現：單元測試應該要是最多的，也是最底層的。其次才是服務測試，最後才是 UI 測試。大量的單元測試可以保證我們的基礎函數是正常、正確工作的。而服務測試則是一門很有學問的測試，不僅僅只在測試我們自己提供的服務，也會測試我們依賴第三方提供的服務。在測試第三方提供的服務時，這就會變成一件有意思的事了。除此還有對功能和 UI 的測試，寫這些測試可以減輕測試人員的工作量——畢竟這些工作量轉向了開發人員來完成。

####單元測試

單元測試是針對程式模組（軟體設計的最小單位）來進行正確性檢驗的測試工作。它是應用的最小可測試部件。舉個例子來說，下面是一個JavaScript 的函數，用於判斷一個變數是否是一個物件：

```
var isObject = function (obj) {
    var type = typeof obj;
    return type === 'function' || type === 'object' && !!obj;
};
```

這是一個很簡單的功能，對應的我們會有一個簡單的 Jasmine 測試來保證這個函數是正常工作的：

```javascript
it("should be a object", function () {
    expect(l.isObject([])).toEqual(true);
    expect(l.isObject([{}])).toEqual(true);
});
```

雖然這個測試看上去很簡單，但是大量的基本的單元測試可以保證我們呼叫的函數都是可以正常工作的。這也相當於是我們在建設金字塔時用的石塊——如果我們的石塊都是經常測試的，那麼我們就不怕金字塔因為石塊的損壞而坍塌。

當單元測試達到一定的覆蓋率，我們的程式碼就會變得更健壯。因為我們都需要保證我們的程式碼都是可測的，也意味著我們程式碼間的耦合度會降低。我們需要去考慮程式碼的長度，越長的程式碼在測試的時間會變得越困難。這也就是為什麼 TDD 會促使我們寫出短的程式碼。如果我們的程式碼都是有測試的，單元測試可以幫助我們在未來重構我們的程式碼。

並且在很多沒有文件或者文件不完整的開源項目中，瞭解這個項目某個函數的用法就是檢視他的測試用例。測試用例（Test Case）是為某個特殊目標而編制的一組測試輸入、執行條件以及預期結果，以便測試某個程式路徑或核實是否滿足某個特定需求。這些測試用例可以讓我們直觀地理解程式程式的 API。

####服務測試

服務測試顧名思義便是對服務進行測試，而服務可以是有不同的類型，不同層次的測試。如第三方的 API 服務、我們程式提供的服務，雖然他們他應該在這一個層級上進行測試，但是對他們的測試會稍有不同。

對於第三方的提供的 API 服務或者其他類似的服務，在這一個層級的測試，我們都不會真實地去測試他們能不能工作——這些依賴性的服務只會在功能測試上進行測試。在這裡的測試，我們只會保證我們的功能程式碼是可以正常工作的，所以我們會使用一些虛假的 API 測試資料來進行測試。這一類提供 API 的 Mock Server 可以模擬被測系統外部依賴模組行為的通用服務。我們只要保證我們的功能程式碼是正常工作的，那麼依賴他的服務也會是正常工作的。

![Mock Server](assets/article/chapter3/mock-server.png)

而對於我們提供的服務來說，這一類的服務不一定是 API 的服務，還有可能是多個函陣列成的功能性服務。當我們在測試這些服務的時候，實際上是在測試這個函數結合在一起是不是正常的。

一個服務可能依賴於多個函數，因而我們會發現服務測試的數量是少於單元測試的。

####UI 測試

在傳統的軟體開發中，UI 測試多數是由人手動來完成的。而在稍後的章節裡，你將會看到這些工作是可以由機器自己來完成的——當然，前提是我們要編寫這些自動化測試的程式碼。需要注意的是 UI 測試並不能完全替代手工的工作，一些測試還是應該由人來進行測試——如對 UI 的佈局，在現階段機器還沒有審美意識呢。

自動化 UI 測試是一個緩慢的過程，在這個過程裡我們需要做這麼幾件事：

1. 執行起我們的網站——這可能需要幾分鐘。
2. 新增一些 Mock 的資料，以使網站看上去正常——這也需要幾分鐘到幾十分鐘的時間。
3. 開始執行測試——在一些依賴於網路的測試中，執行完一個測試可能會需要幾分鐘。儘管可以並行執行測試，但是一個測試幾分鐘算到最後就會累積成很長的時間。

所以，你會發現這是一個很長的測試過程。儘可能地將這個層級的測試往下層級移，就會盡可能的節省時間。一個 UI 測試需要幾分鐘，但是一個單元測試可能不到1秒。這就意味著，這樣的測試下移可以節省上百個數量級的時間。

###如何測試

現在問題來了，我們應該怎麼去寫測試？換句話來說，我要測什麼？這是一個很難的問題，這足夠可以以一本書的幅度來說明這個問題。這個問題也需要依賴於不同的實踐，不同的時候我們可能對問題的看法都有不同。

編寫測試的過程大致可以分成下面的幾個步驟：

1. 瞭解測試目的(Why)？即我們需要測什麼，我們是為了什麼而編寫的測試。
2. 我們要測哪些內容(What)？即測試點，我們即要從功能點上出發來尋找需要我們測試的點，在不同的條件下這個測試點是不一樣的。
3. 我們要如何進行測試(How)？我們要使用怎麼樣的方法進行測試？

####測試目的

我們在上面提到過的測試金字塔，也表明了我們在每個層級要測試的目的是不一樣的。

在單元測試這一層級，因為我們所測試的是每一個函數，這些函數沒有辦法構成完整的功能。這時候我們就只是用於簡簡單單的測試函數本身的功能，沒有太多的業務需求。

而對於服務這一層級，我們所要測試的就是一個完整的功能。對於以 API 為主的項目來說，實際上就是在測返回結果是否是正確的。

最後 UI 這一層級，我們所需要測試的就是一個完整的功能。使用者操作的時候應該是怎樣的，那麼我們就應該模仿使用者的行為來測試。這是一個完整的業務需求，也可以稱之為驗證測試。

####測試點

在瞭解完我們要測試的目的之後，我們要測試的點也變得很清晰。即在單元測試測試我們的函數的功能，在我們的服務測試我們的服務，在我們的 UI測試測試業務。

而這些都理想的情況，當系統由於業務的原因不得不耦合的時候。究竟是單元測試還是功能測試，這是一個特別值得思考的問題。如果一個功能既可以在單元測試裡測，又可以在服務測試裡測，那麼我們要測試哪一個？或者說我們應該把兩個都測一遍？而如果是花費時間更長的 UI 測試呢？這樣做是不是會變得不划算。

####如何寫測試程式碼

先讓來們來簡單地看一下測試用例，然後再讓我們看看一般情況下我們是如何寫測試程式碼的。下面的程式碼是一個用Python寫的測試用例：

```python
class HomepageTestCase(LiveServerTestCase):
    def setUp(self):
        self.selenium = webdriver.Firefox()
        self.selenium.maximize_window()
        super(HomepageTestCase, self).setUp()

    def tearDown(self):
        self.selenium.quit()
        super(HomepageTestCase, self).tearDown()

    def test_can_visit_homepage(self):
        self.selenium.get(
            '%s%s' % (self.live_server_url,  "/")
        )

        self.assertIn("Welcome to my blog", self.selenium.title)
```

在上面的程式碼裡主要有三個方法，setUp()、tearDown()和 test_can_visit_homepage()。在這三個方法中起主要作用的是 test_can_visit_homepage()方法。而 setUp() 和 tearDown() 是特殊的方法，分別在測試方法開始之前執行和之後執行。同時，在這裡我們也用這兩個方法來開啟和關閉瀏覽器。

而在我們的測試方法 test_can_visit_homepage() 裡，主要有兩個步驟：

1. 訪問首頁
2. 驗證首頁的標題是“Welcome to my blog”

大部分的測試程式碼也是以如何的流程來執行著。有一點需要注意的是：一般來說函數名就表示了這個測試所要做測試的事情，如這裡就是測試可以訪問首頁。

如上所示的測試過程稱為“四階段測試”，即這個過程分為如下的四個階段：

1. **Setup**。在這個階段主要是做一些準備工作，如資料準備和初始化等等，在上面的 setup 階段就是用 selenium 啟動了一個 Firefox 瀏覽器，然後把視窗最大化了。
2. **Execute**。在執行階段就是做好驗證結果前的工作，如我們在測試註冊的時候，那麼這裡就是填寫資料，並點選提交按鈕。在上面的程式碼裡，我們只是開啟了首頁。
3. **Verify**。在驗證階段，我們所要做的就是驗證返回的結果是否和我們預期的一致。在這裡我們還是使用和單元測試一樣的 assert 來做斷言，通過判斷這個頁面的標題是"Welcome to my blog"，來說明我們現在就是在首頁裡。
4. **Tear Down**。就是一些收尾工作啦 ，比如關閉瀏覽器、清除測試資料等等。

####Tips

需要注意的幾點是：

1. 從執行測試速度上來看，三種測試的執行速度是呈倒金字塔結構。即，單元測試跑得最快，開發速度也越快。隨後是服務測試，最後是 UI 測試。
2. 即使現在的 UI 測試跑得非常快，但是隨著時間的推移，UI 測試會越來越多。這也意味著測試來跑得越來越久，那麼人們就開始不想測試了。在我們之前的項目裡，執行完所有的測試大概接近一個小時，我們開始在會議會爭論這些測試的必要性，也在想方設法減少這些測試。
3. 如果一個測試可以在最底層寫，那麼就不要在他的上一層寫了，因為他的執行速度更快。

參考書籍:

 - 《優質程式碼——軟體測試的原則、實踐與模式》
 - 《Python Web 開發： 測試驅動開發方法》

測試替身
---

測試替身（Test Double）是一個非常有意思的概念。

> 有時候對被測系統(SUT)進行測試是很困難的，因為它依賴於其他無法在測試環境中使用的元件。這有可能是因為這些元件不可用，它們不會返回測試所需要的結果，或者執行它們會有不良副作用。在其他情況下，我們的測試策略要求對被測系統的內部行為有更多控制或更多可見性。
> 如果在編寫測試時無法使用（或選擇不使用）實際的依賴元件(DOC)，可以用測試替身來代替。測試替身不需要和真正的依賴元件有完全一樣的的行為方式；他只需要提供和真正的元件同樣的 API 即可，這樣被測系統就會以為它是真正的元件！ ——Gerard Meszaros

當我們遇到一些難以測試的方法、行為的時候，我們就一些特別的方式來幫助我們測試。Mock 和 Stub 就是常見的兩種方式：

1. Stub 是一種狀態確認，它用簡單的行為來替換複雜的行為
2. Mock 是一種行為確認，它用於模擬其行為

通俗地來說：Stub 從某種程度上來說，會返回我們一個特定的結果，用程式碼替換來方法；而 Mock 只是確保這個方法被呼叫。

###Stub

Stub 從字面意義上來說是存根，存根可以理解為我們保留了一些預留的結果。這個時候我們相當於構建了這樣一個特殊的測試場景，用於替換諸如網路或者 IO 排程等高度不可預期的測試。如當我們需要去驗證某個 API 被呼叫並返回了一個結果，舉例在最小物聯網系統設計中返回的 json，我們可以在本地構建一個

```javascript
[{"id":1,"temperature":14,"sensors1":15,"sensors2":12,"led1":1}]
```

的結果來當我們預期的資料，也就是所謂的存根。那麼我們所要做的也就是解析 json，並返回預期的結果。當我們依賴於網路時，此時測試容易出現問題。

###Mock

Mock 從字面意義上來說是模仿，也就是說我們要在本地構造一個模仿的環境，而我們只需要驗證我們的方法被呼叫了。

```javascript
var Foo = function(){};
Foo.prototype.callMe = function() {};
var foo = mock( Foo );

foo.callMe();

expect( foo.callMe ).toHaveBeenCalled();
```

測試驅動開發
---

測試驅動開發是一個很"古老"的程式開發方法，然而由於國內開發流程的問題——即開發人員負責功能的測試，導致這麼好的一項技術沒有在國內推廣。

###紅-綠-重構

測試驅動開發的主要過程是: 紅 —> 綠 -> 重構

![TDD](assets/article/chapter3/tdd.jpg)

1. 先寫一個失敗的單元測試。即我們並沒有實現這個方法，但是已經有了這個方法的測試。
2. 讓測試通過。實現簡單的程式碼來保證測試通過，就算我們用一些作弊的方法也是可以的。我們寫的是功能程式碼，那麼我們應該提交程式碼，因為我們已經實現了這個功能。
3. 重構，並改進功能程式碼，讓它變得更加合理。

TDD 有助於我們將問題分解成更小的部分，再一點點的新增我們所需要的業務程式碼。隨著這個過程的不斷進行，我們會發現我們已經接近完成我們的功能程式碼了。並且到了最後，我們會發現我們的程式碼都會被測試到。


雖然說起來很簡單，但是真正實現起來並不是那麼容易。於我而言我只會在我自己造的一些輪子中使用 TDD。因為這個花費大量的時間，通常來說測試程式碼和功能程式碼的比例可能是1:1，或者是2：1等等。在自己建立的一些個人應用，如部落格中，我不需要與其他人 Share 我的 Content。由於我使用的是第三方框架，框架本身的測試已經足夠多，並且沒有複雜的邏輯，我就沒有對我的部落格寫測試。而在我寫的一些框架裡，我就會盡量保證足夠高的測試覆蓋率，並且在適當的時候會去 TDD。

通常來說對於單元測試我會採用 TDD 的方式來進行，但是功能測試仍會選擇在最後新增進去。主要的緣由是：在寫 UI 的過程中，元素會發生變化。這一點和我們在寫 Unit 的時候，有很大的區別。div + class 會使得我們思考問題的方式發生變化，我們需要去點選某個元素，並觀察某個元素髮生的變化。而多數時候，我們很難把握好一個頁面最後的樣子。

不得不說明的一點是，TDD 需要你對測試比較瞭解後，才容易使用它。從個人的感受來說，TDD 在一開始是一件很難的事。

###測試先行

對於寫測試的人來說，測試先行有點難以理解，而對於不寫測試的人來說，就更難以理解。這裡假定你已經開始寫測試了，因為對於不寫測試的人來說，寫測試就是一件難以理解的事。既然我們都要寫測試，那麼為什麼我們就不能先寫測試呢？或者說為什麼後寫測試存在一些問題？

依據 J.Timothy King 所總結的《測試先行的12個好處》：

1. 測試可證明你的程式碼是可以解決問題的
2. 一面寫單元測試，一面寫實現程式碼，這樣感覺更有興趣
3. 單元測試也可以用於演示程式碼
4. 會讓你在寫程式碼之前做好計劃
5. 它降低了 Bug 修復的成本
6. 可以得到一個底層模組的迴歸測試工具
7. 可以在不改變現有功能的基礎上繼續改進你的設計
8. 可以用於展示開發的進度
9. 它真實的為程式設計師消除了工作上的很多障礙
10. 單元測試也可以讓你更好的設計
11. 單元測試比程式碼審查的效果還要好
12. 它比直接寫程式碼的效率更高

但是在我個人的感覺裡，比較喜歡的是： **寫出可以測試的函數**。這是一個一直困擾著我的難題，特別是當我的程式碼裡存在很多條件的時候，在後期我編寫的時候，難度越來越大。當我只有一個簡單的 IF-ELSE 的時候，我的程式碼測試起來也很簡單:

```javascript
if (hour < 18) {
    greeting = "Good day";
} else {
    greeting = "Good evening";
}
```

而當我有複雜的業務邏輯時，後寫測試就會變成一場惡夢：

```javascript
if (EchoesWorks.isObject(words)) {
	var nextTime = that.parser.parseTime(that.data.times)[currentSlide + 1];
	if (that.time < nextTime && words.length > 1) {
		var length = words.length;
		var currentTime = that.parser.parseTime(that.data.times)[currentSlide];
		var time = nextTime - currentTime;
		var average = time / length * 1000;
		var i = 0;
		document.querySelector('words').innerHTML = words[i].word;

		timerWord = setInterval(function () {
			i++;
			if (i - 1 === length) {
				clearInterval(timerWord);
			} else {
				document.querySelector('words').innerHTML = words[i].word;
			}
		}, average);
	}
	return timerWord;
} else {
	document.querySelector('words').innerHTML = words;
}
```

我們需要重新理清業務的邏輯，再依據這些邏輯來編寫測試程式碼。而當我們已經忘記具體的業務邏輯時，我們已然無法寫出測試。

**思考**

通常在我的理解下，TDD 是可有可無的。既然我知道了我要實現的大部分功能，而且我也知道如何實現。與此同時，對 Code Smell 也保持著警惕、要保證功能被測試覆蓋。那麼，總的來說 TDD 帶來的價值並不大。

然而，在當前這種情況下，我知道我想要的功能，但是我並不理解其深層次的功能。我需要花費大量的時候來理解，它為什麼是這樣的，需要先有一些指令碼來知道它是怎麼工作的。TDD 變顯得很有價值，換句話來說，在現有的情況下，TDD 對於我們不瞭解的一些事情，可以驅動出更多的開發。畢竟在我們完成測試指令碼之後，我們也會發現這些測試指令碼成為了程式碼的一部分。

在這種理想的情況下，我們為什麼不 TDD 呢?

參考資料

 J.Timothy King 《Twelve Benefits of Writing Unit Tests First》

可讀的程式碼
---

過去，我有過在不同的場合吐槽別人的程式碼寫得爛。而我寫的僅僅是比別人好一點而已——而不是好很多。

然而這是一件很難的事，人們對於同一件事物未來的考慮都是不一樣的。同樣的程式碼在相同的情景下，不同的人會有不同的設計模式。同樣的程式碼在不同的情景下，同樣的人會有不同的設計模式。在這裡，我們沒有辦法討論設計模式，也不需要討論。

我們所需要做的是，確保我們的程式碼易讀、易測試，看上去這樣就夠了，然而這也是挺複雜的一件事:

 - 確保我們的變數名、函數名是易讀的
 - 沒有複雜的邏輯判斷
 - 沒有多層巢狀 (事不過三)
 - 減少複雜函數的出現（如,不超過三十行）
 - 然後，你要去測試它。這樣你就知道需要什麼，實際上要做到這些也不是一些難事。

只是首先，我們要知道我們要自己需要這些。對於沒有太多程式設計經驗的人，建議先從兩個基本點做起：

 - 命名
 - 函數長度

首先要說的就是程式設計師認為最難的一個話題了——命名。

###命名

命名是一個特別長的，也是特別憂傷的故事。我想作為一個程式設計師的你，也相當恐懼這件事。一個好的函數名、變數名應該包含著這個函數的資訊，如這個函數是幹什麼的，或者這個函數是怎麼來的，這個變數名儲存的是什麼。

正因為取名字是一件很重要的事，所以它也是一件很難的事。一個好的函數名、變數名應該能正確地表達出它的涵義。如你可以猜到下面的程式碼中的i是什麼意思嗎？

```python
fruits = ['banana', 'apple',  'mango']
for i in fruits:        # Second Example
   print 'Current fruit :', i
```

那如果換成下面的程式碼會不會更容易閱讀呢？


```python
fruits = ['banana', 'apple',  'mango']
for fruit in fruits:        # Second Example
   print 'Current fruit :', fruit
```

而命令還存在於對函數的命名上，如我們可能會用 getNumber 來表示去獲取一個數值，但是要知道這樣的命名並不是在所有的語言中都可以這樣用。如在 Java 中存在 getter 和 setter 這種模式，如下的程式碼所示：

```
public String getNumber() {
  return number;
}
public void setNumber(String number) {
  this.number = number;
}
```

如果我們是去取某個東西的數值，那麼我們應該使用 retrieveNumber 這樣的更具代表性的名字。

在《編寫可讀程式碼的藝術》也提到了這幾點：

1. 選擇專業的詞。最好是可以和業務相關的，它應該極具表現力。
2. 避免像 tmp 和 retval 這樣泛泛的名字。不得不提到的一點是，tmp 實在是一個有夠爛的名字，將其變為 timeTemp 或者類似的會更直觀。它只應該是名字中的一部分。
3. 用具體的名字代替抽象的名字。
4. 為名字賦予更多的資訊。
5. 名字應該有多長。
6. 利用名字的格式來傳遞含義。

###函數長度

> 函數是指一段在一起的、可以做某一件事兒的程式。

這就意味著從定義上來說，這段函數應該只做一件事——但是什麼才是真正的一件事呢？實際上還是 TASKING，將一個複雜的過程一步步地分解成一個個的函數，每個函數只做他的名稱對應的事。對於一個任務來說，他有一個穩定的過程，在這個過程中的每一步都可以變成一個函數。

因此，長的程式碼意味著一件事——這個函數可能違反了單一職責原則，即這個類做了太多的事。通常來說，一個類，只有一個引起它變化的原因。當一個類有多個職責的時候，這些程式碼就容易耦合到一起了。

對於函數長度的控制是為了有效控制分支深度。如果我們用一個函數來實現一個複雜的功能，那麼不僅僅在我們下次閱讀的時間會花費大量的時間。而且如果我們的程式碼沒有測試的話，這些程式碼就會變得越來越難以理解。而在我們寫這些函數的時候就沒有測試，那麼這個函數就會變得越來越難以測試，它們就會變成遺留程式碼。

###其他

雖然只想介紹上面的簡單的兩點，但是順便在這裡也提一下重複程式碼~~。

####重複程式碼

在《重構》一書中首先提到的 Code Smell 就是重複程式碼（Duplicate Code）。重複程式碼看上去並不會影響我們的閱讀體驗，但是實際上會發生這樣的事——重複的程式碼閱讀體驗越不好。

DRY(Don't Repeat Yourself)原則是特別值得玩味的。當我們不斷地偏執的去減少重複程式碼的時候，會導致複雜度越來越高。在適當的時候，由於業務發生變更，我們還需要去拆解這些不重複的程式碼。

程式碼重構
---

> 重構，一言以蔽之，就是在不改變外部行為的前提下，有條不紊地改善程式碼。

程式碼重構（英語：Code refactoring）指對軟體程式碼做任何更動以增加可讀性或者簡化結構而不影響輸出結果。在經歷了一年多的工作之後，我平時的主要工作就是修 Bug。剛開始的時候覺得無聊，後來才發現修 Bug 需要更好的技術。有時候你可能要面對著一坨一坨的程式碼，有時候你可能要花幾天的時間去閱讀程式碼。而，你重寫那幾十行程式碼可能只會花上你不到一天的時間。但是如果你沒辦法理解當時為什麼這麼做，你的修改只會帶來更多的 Bug。修 Bug，更多的是維護程式碼。還是前人總結的那句話對:

> 寫程式碼容易，讀程式碼難。

假設我們寫這些程式碼只要半天，而別人讀起來要一天。為什麼不試著用一天的時間去寫這些程式碼，讓別人花半天或者更少的時間來理解。

###重新命名

在上一節中，我們提到了命名的重要性，這裡首先要說到的也就是重新命名~~~。再看看《編寫可讀程式碼的藝術》也提到了這幾點：

1. 選擇專業的詞。最好是可以和業務相關的，它應該極具表現力。
2. 避免像 tmp 和 retval 這樣泛泛的名字。不得不提到的一點是，tmp 實在是一個有夠爛的名字，將其變為 timeTemp 或者類似的會更直觀。它只應該是名字中的一部分。
3. 用具體的名字代替抽象的名字。
4. 為名字賦予更多的資訊。
5. 名字應該有多長。
6. 利用名字的格式來傳遞含義。

###提取變數

先讓我們來看看一個簡單的情況：

```javascript
if ($scope.goodSkills.indexOf('analytics') !== -1) {
  skills.analytics = 5;
}
```

在上面的程式碼裡比較難以看懂的就是數字5，這時候你會怎麼做？寫一行註釋？這裡的5就是一個 Magic Number。

而實際上，最簡單有效的辦法就是把5提取成一個變數：


```javascript
var LEVEL_FIVE = 5;
if ($scope.goodSkills.indexOf('analytics') !== -1) {
  skills.analytics = LEVEL_FIVE;
}
```

###提煉函數

這個簡單有效的方法就是為了對付之前太長的函數，抽取提煉函數出應該抽取出來的部分成為一個新的函數。引自《重構》一書的說法，短的精巧的函數有以下的特點：

1. 如果每個函數的粒度都很小，那麼函數被複用的機會就更大；
2. 是這會讓高層函數讀起來就像一系列註釋一樣，容易理解；
3. 是如果函數都是細粒度，那麼函數的複寫也會更加容易。

在提煉函數中我們所要做的就是——判斷出原有的函數的意圖，再依據我們的新意圖來命名新的函數。然後判斷依賴——變數值，處理這些變數。提取出函數，再對其測試。

這裡只簡單地對重構進行一些介紹，更多詳細資訊請參閱《重構：改善既有程式碼的設計》。

Intellij Idea 重構
---

下面簡單地介紹一下，一些可以直接使用 IDE 就能完成的重構。這種重構可以用在日常的工作中，只需要使用 IDE 上的快捷鍵就可以完成了。

###提煉函數

Intellij IDEA 帶了一些有意思的快捷鍵，或者說自己之前不在意這些快捷鍵的存在。重構作為單獨的一個選單，顯然也突顯了其功能的重要性，說說**提煉函數**，或者說提出方法。

快捷鍵

Mac:  ``alt``+``command``+``M``

Windows/Linux: ``Ctrl``+``Alt``+``M``

滑鼠: Refactor | Extract | Method

**重構之前**

以重構一書程式碼為例，重構之前的程式碼

```java
public class extract {
    private String _name;

    void printOwing(double amount){
        printBanner();

        System.out.println("name:" + _name);
        System.out.println("amount" + amount);
    }

    private void printBanner() {
    }
}
```

**重構**

選中

```java
System.out.println("name:" + _name);
System.out.println("amount" + amount);
```

按下上述的快捷鍵，會彈出下面的對話方塊

![Extrct Method](assets/article/chapter3/extract-method.png)

輸入

     printDetails

那麼重構就完成了。

**重構之後**

IDE 就可以將方法提出來

```java
public class extract {
    private String _name;

    void printOwing(double amount){
        printBanner();
        printDetails(amount);
    }

    private void printDetails(double amount) {
        System.out.println("name:" + _name);
        System.out.println("amount" + amount);
    }

    private void printBanner() {
    }
}
```

**重構**

還有一種就以 Intellij IDEA 的示例為例，這像是在說其的智慧。

```java
public class extract {
    public void method() {
        int one = 1;
        int two = 2;
        int three = one + two;
        int four = one + three;
    }
}
```

只是這次要選中的只有一行，

```
int three = one + two;
```

以便於其的智慧，它便很愉快地告訴你它又找到了一個重複

     IDE has detected 1 code fragments in this file that can be replaced with a call to extracted method...

便返回了這樣一個結果

```java
public class extract {

    public void method() {
        int one = 1;
        int two = 2;
        int three = add(one, two);
        int four = add(one, three);
    }

    private int add(int one, int two) {
        return one + two;
    }

}
```

然而我們就可以很愉快地繼續和它玩耍了。當然這其中還會有一些更復雜的情形，當學會了這一個剩下的也不難了。

###行內函數

繼續走這重構一書的複習之路，接著便是內聯，除了內聯變數，當然還有行內函數。

快捷鍵

Mac:  ``alt``+``command``+``N``

Windows/Linux: ``Ctrl``+``Alt``+``N``

滑鼠: Refactor | Inline

**重構之前**

```java
public class extract {

    public void method() {
        int one = 1;
        int two = 2;
        int three = add(one, two);
        int four = add(one, three);
    }

    private int add(int one, int two) {
        return one + two;
    }

}
```

在``add(one,two)``很愉快地按上個快捷鍵吧，就會彈出

![Inline Method](assets/article/chapter3/inline.jpg)

再輕輕地回車，Refactor 就這麼結束了。。

**Intellij Idea 內聯臨時變數**

以書中的程式碼為例

```java
double basePrice = anOrder.basePrice();
return (basePrice > 1000);
```

同樣的，按下``Command``+``alt``+``N``

```java
return (anOrder.basePrice() > 1000);
```

對於 python 之類的語言也是如此

```python
def inline_method():
    baseprice = anOrder.basePrice()
    return baseprice > 1000
```

###查詢取代臨時變數

快捷鍵

Mac:  木有

Windows/Linux:  木有

或者: ``Shift``+``alt``+``command``+``T`` 再選擇  ``Replace Temp with Query``

滑鼠: **Refactor** | ``Replace Temp with Query``

**重構之前**

過多的臨時變數會讓我們寫出更長的函數，變數不應該太多，以便使功能單一。這也是重構的另外的目的所在，只有函數專注於其功能，才會更容易讀懂。

以書中的程式碼為例

```java
import java.lang.System;

public class replaceTemp {
    public void count() {
        double basePrice = _quantity * _itemPrice;
        if (basePrice > 1000) {
            return basePrice * 0.95;
        } else {
            return basePrice * 0.98;
        }
    }
}
```

**重構**

選中``basePrice``很愉快地拿滑鼠點上面的重構

![Replace Temp With Query](assets/article/chapter3/replace.jpg)

便會返回

```java
import java.lang.System;

public class replaceTemp {
    public void count() {
        if (basePrice() > 1000) {
            return basePrice() * 0.95;
        } else {
            return basePrice() * 0.98;
        }
    }

    private double basePrice() {
        return _quantity * _itemPrice;
    }
}
```

而實際上我們也可以

1. 選中

        _quantity * _itemPrice

2. 對其進行``Extrace Method``

3. 選擇``basePrice``再``Inline Method``

在 Intellij IDEA 的文件中對此是這樣的例子

```java
public class replaceTemp {

    public void method() {
        String str = "str";
        String aString = returnString().concat(str);
        System.out.println(aString);
    }

}
```

接著我們選中``aString``，再開啟重構選單，或者

``Command``+``Alt``+``Shift``+``T`` 再選中 Replace Temp with Query

便會有下面的結果:

```java
import java.lang.String;

public class replaceTemp {

    public void method() {
        String str = "str";
        System.out.println(aString(str));
    }

    private String aString(String str) {
        return returnString().concat(str);
    }

}
```

重構到設計模式
---

> 模式和重構之間存在著天然聯絡，模式是你想到達的目的地，而重構則是從其他地方到達這個目的地的條條道路——Martin Fowler《重構》

###過度設計與設計模式

過度設計和設計模式是兩個很有意思的詞語，這取決於我們是不是預先式設計。通過以往的經驗我們很容易看到一個環境來識別一個模式。遺憾的是使用設計模式依賴於我們整個團隊的水平。對於瞭解設計模式的人來說，設計模式就是一種溝通語言。而對於瞭解一些設計模式的人來說，設計模式就是複雜的程式碼。

並且在軟體迭代的過程中需求總是不斷變化的，這就意味著我們對程式碼設計的越早，在後期失敗的概率也就越大。設計會伴隨著需求而發生變化，在當時看起來合理的設計，在後期就會因此而花費過多的代價。

而如果我們不進行一些設計，就有可能出現設計不足。這種情況可能出現於沒有時間寫出更好的程式碼的項目，在這些項目裡由於一些原因出現加班等等的原因，使得我們沒有辦法寫出更好的程式碼。同時，也有可能是因為參考項目的程式設計師在設計方面出現不足。

我們沒有介紹設計模式的一個原因是——它需要有大量的程式設計經驗，才可以讓我們實現：重構到設計模式。

上線
===

作為一個開發人員，我們也需要去了解如何配置伺服器。不僅僅因為它可以幫助我們更好地理解 Web 開發，而且有時候很多 Bug 都是因為伺服器環境引起的——如臭名昭著地編碼問題。

 - 一些簡單的 Ops 技能。
 - 瞭解伺服器的相關軟體
 - 搭建執行 Web 應用的伺服器
 - 自動化部署應用

為了即時的完成工作，你是不是放棄了很多東西，比如質量? 測試是很重要的一個環節，不僅可以為我們保證程式碼的質量，而且還可以為我們以後的重構提供基礎條件。

作為一個在敏捷團隊裡工作的開發人員，初次意識到在國內大部分的開發人員是不寫測試的時候，我還是有點詫異。

儘管沒有寫測試可以在初期走得很快，但是在後期就會遇到一堆麻煩事。傳統的思維下，我們會認為一個人會在一家公司工作很久。而這件事在最近幾年裡變化得特別快，特別是在資訊科技高速發展的今天。人們可以從不同的地方得到哪裡缺人，從一個地方到另外一個地方也變得異常的快，這就意味著人員流動是常態。

而程式碼儘管還在，但是卻會隨著人員流動而出現更多的問題。這時如果程式碼是有有效的測試，那麼則可以幫助系統更好地被理解。

隔離與執行環境
---

為了將我們的應用部署到伺服器上，我們需要為其配置一個執行環境。從底層到頂層有這樣的執行環境及容器：

1. 隔離硬體：虛擬機器
2. 隔離作業系統：容器虛擬化
3. 隔離底層：Servlet 容器
4. 隔離依賴版本：虛擬環境
5. 隔離執行環境：語言虛擬機器
6. 隔離語言：DSL

實現上這是一個請求的處理過程，一個 HTTP 請求會先到達你的主機。如果你的主機上執行著多個虛擬機器例項，那麼請求就會來到這個虛擬機器上。又或者你是在 Docker 這一類容器裡執行你的程式的話，請求也會先到達 Docker。隨後這個請求就會交由 HTTP 伺服器來處理，如 Apache、Nginx，這些 HTTP 伺服器再將這些請求交由對應的應用或指令碼來處理。隨後將交由語言底層的指令來處理。

![Docker Tomcat](assets/article/chapter4/docker-with-tomcat.png)

不同的環境有不同的選擇，當然也可以結合在一起。不過，從理論上來說在最外層還是應該有一個真機的，但是我想大家都有這個明確的概念，就不多解釋了。

###隔離硬體：虛擬機器

在虛擬機器技術出現之前，為了執行不同使用者的應用程式，人們需要不同的物理機才能實現這樣的需求。對於 Web 應用程式來說，有的使用者的網站訪問量少消耗的系統資源也少，有的使用者的網站訪問量大消耗的系統資源也多。雖然有不同的伺服器類型可以選擇，然而對於多數的訪問少的使用者來說他們需要支付同樣的費用。這聽上去相當的不合理，並且也浪費了大量的資源。並且對於系統管理員來說，管理這些系統也不是一件容易的事。在過去硬體技術革新特別快，讓作業系統執行在不同的機器上也不是一件容易的事。

> 虛擬機器（Virtual Machine）指通過軟體模擬的具有完整硬體系統功能的、執行在一個完全隔離環境中的完整計算機系統。

這是一個很有意思的技術，它可以讓我們在一個主機上同時執行幾個不同的作業系統。我們可以為這幾個作業系統使用不同的硬體，在這之上的應用可以使用不同的技術棧來執行，並且從理論上互相不影響。其架構如下圖所示：

![虛擬機器](assets/article/chapter4/virtual_machine.png)

藉助於虛擬機器技術，當我們需要更多的資源的時候，建立一個新的虛擬機器就行了。同時，由於這些虛擬機器上執行的是同樣的作業系統，並且可以使用相同的配置，我們只需要編寫一些指令碼就可以實現其自動化。當我們的物理機發生問題時，可以很快將虛擬機器遷移或恢復到另外的宿主機。

###隔離作業系統：容器虛擬化

對於大部分開發團隊來說，直接開發基於虛擬機器的自動化工具不是一件容易的事，並且它從使用成本上來說比較高。這時候我們就需要一些更輕量級的工具容器——它可以提供輕量級的虛擬化，以便隔離程序和資源，而且不需要提供指令解釋機制以及全虛擬化的其他複雜性。並且，它從啟動速度上來說更快。

####LXC

在介紹 Docker 之前，我們還是稍微提一下 LXC。因為在過去我有一些使用 LXC 的經歷，讓我覺得 LXC 很贊。

> LXC，其名稱來自 Linux 軟體容器（Linux Containers）的縮寫，一種作業系統層虛擬化（Operating system–level virtualization）技術，為 Linux 核心容器功能的一個使用者空間介面。它將應用軟體系統打包成一個軟體容器（Container），內含應用軟體本身的程式碼，以及所需要的作業系統核心和庫。通過統一的名字空間和共用 API 來分配不同軟體容器的可用硬體資源，創造出應用程式的獨立沙箱執行環境，使得 Linux 使用者可以容易的建立和管理系統或應用容器。

我們可以將之以上面說到的虛擬機器作一個簡單的對比，其架構圖如下所示：

![LXC vs VM](assets/article/chapter4/lxc-vm.jpg)

我們會發現虛擬機器中多了一層 Hypervisor——執行在物理伺服器和作業系統之間，它可以讓多個作業系統和應用共享一套基礎物理硬體。這一層級可以協調訪問伺服器上的所有物理裝置和虛擬機器，然而由於這一層級的存在，它也將消耗更多的能量。據愛立信研究院和阿爾託大學發表的論文表示：Docker、LXC 與 Xen、KVM 在完成相同的工作時要少消耗10%的能耗。

LXC 主要是利用 cgroups 與 namespace 的功能，來向提供應用軟體一個獨立的作業系統執行環境。cgroups（即Control Groups）是 Linux 核心提供的一種限制、記錄、隔離程序組所使用的物理資源的機制。由 namespace 來責任隔離控制。

與虛擬機器相比，LXC 隔離性方面有所不足，這就意味著在實現可移植部署時會遇到一些困難。這時候，我們就需要 Docker 來提供一個抽象層，並提供一個管理機制。

####Docker

> Docker 是一個開源的應用容器引擎，讓開發者可以打包他們的應用以及依賴包到一個可移植的容器中，然後釋出到任何流行的 Linux 機器上，也可以實現虛擬化。Docker 可以自動化打包和部署任何應用、建立一個輕量級私有 PaaS 雲、搭建開發測試環境、部署可擴充套件的 Web 應用等。

構建出 Docker 的 Container 是一個很有意思的過程。在這一個過程中，首先我們需要一個 base images，這個基礎映象不僅包含了一個基礎系統，如 Ubuntu、Debian。他還包含了一系列的模組，如初始化程序、SSH 服務、syslog-ng 等等的一些工具。由上面原內容構建了一個基礎映象，隨後的修改都將基於這個映象，我們可以用它生成新的映象，一層層的往上疊加。而使用者的程序執行在 writeable 的 layer 中。

![Docker Container](assets/article/chapter4/basic-images.png)

從上圖中我們還可以發現一點： Docker 容器是建立在 Aufs 基礎上的。AUFS 是一種 Union File System，它可以把不同的目錄掛載到同一個虛擬檔案系統下。它的目的就是為了實現上圖的增量遞增的過程，同時又不會影響原有的目錄。流程如下：

![AUFS 層](assets/article/chapter4/aufs_layers.jpg)

其增量的過程和我們使用 Git 的過程中有點像，除了在最開始的時候會有一個映象層。隨後我們的修改都可以儲存下來，並且當再次提交修改的時候，我們可以在舊有的提交上執行。

因此，Docker 與 LXC 的差別就如下圖所示：

![LXC 與 Docker](assets/article/chapter4/lxc-vs-docker.png)

LXC 是每個虛擬機器只能是一個虛擬機器，而 Docker 則是一系列的虛擬機器。

###隔離底層：Servlet 容器

在上面的例子裡我們已經隔離開了作業系統的因素，接著我們還需要解決作業系統、開發環境引起的差異。早期開發 Web 應用時，人們使用 CGI 技術，它可以讓一個客戶端，從網頁瀏覽器向執行在網路伺服器上的程式請求資料。並且 CGI 程式可以用任何指令碼語言或者是完全獨立程式語言實現，只要這個語言可以在這個系統上執行。而這樣的指令碼語言在多數情況下是依賴於系統環境的，特別是對於 C++ 這一類的編譯型語言來說，在不同的作業系統中都需要重新編譯。

而 Java 的 Servlet 則是另外一種有趣的存在，它是一種**獨立於平臺和協議**的伺服器端的 Java 應用程式，可以生成動態的 Web 頁面。

####Tomcat

在開發 Java Web 應用的過程中，我們在開發環境使用 Jetty 來執行我們的服務，而在生產環境使用 Tomcat 來執行。他們都是 Servlet 容器，可以執行同一個 Servlet 應用。Servlet 是指由 Java 編寫的伺服器端程式，它們是為響應 Web 應用程式上下文中的 HTTP 請求而設計的。它是應用伺服器中位於元件和平臺之間的介面集合。

Tomcat 伺服器是一個免費的開源 Web 應用伺服器。它執行時佔用的系統資源小，擴充套件性好，支援負載平衡與郵件服務等開發應用系統常用的功能。除此，它還是一個 Servlet 和 JSP 容器，獨立的 Servlet 容器是 Tomcat 的預設模式。其架構如下圖所示：

![Tomcat架構](assets/article/chapter4/tomcat-architecture.png)

Servlet 被部署在應用伺服器中，並由容器來控制其生命週期。在執行時由 Web 伺服器軟體處理一般請求，並把 Servlet 呼叫傳遞給“容器”來處理。並且 Tomcat 也會負責對一些靜態資源的處理。

###隔離依賴版本：虛擬環境

對於 Java 這一類的編譯語言來說，不存在太多語言執行帶來的問題。而對於動態語言來說就存在這樣的問題，如 Ruby、Python、Node.js 等等，這一個問題主要集中於開發環境。當然如果你在一個伺服器上執行著幾個不同的應用，也會存在這樣的問題。這一類的工具在 Python 裡有 VirtualEnv，在 Ruby 裡有 RVM、Rbenv，在 Node.js 裡有 NVM。

下圖是使用 VirtualEnv 時幾個不同應用的架構圖：

![VirtualEnv](assets/article/chapter4/virtualenv.jpg)

如下所示，在不同的虛擬環境裡，我們可以使用不同的依賴庫。在這上面構建不同的應用，也可以使用不同的 Python 版本來構建系統。通常來說，這一類的工具主要用於本地的開發環境。

###隔離執行環境：語言虛擬機器

最後一個要介紹的可能就是更加抽象的，但是也是更加實用的一個，JVM 就是這方面的一個代表。在我們的程式設計生涯裡，我們很容易就會遇到跨平臺問題——即我們在我們的開發機器上開發的軟體，在我們的產品環境的機器上就沒有辦法執行。特別是當我們在使用 Mac OS 或者 Windows 機器上開發了應用，卻需要在 Linux 系統上執行時，就會遇到各種問題。並且當我們使用了一個需要重新編譯的庫時，這種問題就更加麻煩。

如下圖所示的是 JVM 的架構示意圖

![JVM](assets/article/chapter4/java-virtual-machine.jpg)

JVM 是一種用於計算裝置的規範，它是一個虛構出來的計算機，是通過在實際的計算機上模擬模擬各種計算機功能來實現的。它可以實現“編寫一次，到處執行”。

換句話來說，它在底層實現了環境隔離，它遮蔽了與具體作業系統平臺相關的資訊，使得 Java 程式只需生成在 Java 虛擬機器上執行的目的碼（位元組碼），就可以在多種平臺上不加修改地執行。

基於此，只要其他程式語言的編譯器能生成正確的 Java bytecode 檔案，這個語言也能在 JVM 上執行。如下圖所示的是基於 JVM 的 Jython 語言的架構圖：

![Jython](assets/article/chapter4/jython-arch.jpg)

其底層是基於 JVM，而編寫時則使用 Python 語言，並且他可以使用 Java 的模組來程式設計。

常見擁有同樣架構的工具，還有 MySQL，如下圖是所示的是 MySQL 的架構圖：

![MySQL](assets/article/chapter4/mysql-architecture.png)

MySQL 在最頂層提供了一個名為 SQL 的查詢語言，這個查詢語言只能用於查詢資料庫，然而它卻是一種更高階的用法。它不像通用目的語言那樣目標範圍涵蓋一切軟體問題，而是專門針對某一特定問題的計算機語言，即領域特定語言。

###隔離語言：DSL

這是一門特別有意思也特別值得期待的技術，但是實現它並不是一件容易的事。

作為討論隔離環境的一部分，我們只看外部 DSL。內部 DSL 與外部 DSL 最大的區別在於：外部 DSL 近似於建立了一種新的語法和語義的全新語言。如下圖所示是兩中 DSL 的一種對比：

![內部 DSL 和外部 DSL](assets/article/chapter4/internal-vs-external.png)

在這樣的外部 DSL 裡，我們有自己的語法、自己的解析器、類型檢測器等等。最簡單且最常用的 DSL 就是 Markdown，如下圖所示：

![Markdown](assets/article/chapter4/markdown.png)

如果我們可以將業務邏輯寫成 DSL，那麼我們就不需要擔心底層語言的變動過多會影響原有的業務邏輯。換句話說，這相當於建立了我們自己的語言隔離環境，我們不需要思考用何種語言來實用我們的業務。

LNMP 架構
---

> LNMP 是一個基於 CentOS/Debian 編寫的 Nginx、PHP、MySQL、phpMyAdmin、eAccelerator 一鍵安裝包。可以在 VPS、獨立主機上輕鬆的安裝 LNMP 生產環境。

由於在前面我們已經介紹過了資料庫和程式語言，這裡我們就只介紹 LN 兩項

###GNU/Linux

GNU 工程創始於一九八四年，旨在開發一個完整 GNU 系統。GNU這個名字是“GNU's Not Unix!”的遞迴首字母縮寫詞。"GNU" 的發音為 g'noo，只有一個音節，發音很像 “grew”，但需要把其中的 r 音替換為 n 音。類 Unix 作業系統是由一系列應用程式、系統庫和開發工具構成的 軟體集合 , 並加上用於資源分配和硬體管理的核心。

Linux 是一種自由和開放源碼的類 UNIX 作業系統核心。目前存在著許多不同的 Linux 發行版，可安裝在各種各樣的電腦硬體裝置，從手機、平板電腦、路由器和影音遊戲控制檯，到桌上型電腦，大型電腦和超級電腦。Linux 是一個領先的作業系統核心，**世界上運算最快的10臺超級電腦執行的都是基於 Linux 核心的作業系統**。

Linux 作業系統也是自由軟體和開放原始碼發展中最著名的例子。只要遵循 GNU 通用公共許可證,任何人和機構都可以自由地使用 Linux 的所有底層原始碼，也可以自由地修改和再發布。**嚴格來講，Linux 這個詞本身只表示 Linux 核心，但在實際上人們已經習慣了用 Linux 來形容整個基於 Linux 核心，並且使用 GNU 工程各種工具和資料庫的作業系統（也被稱為 GNU/Linux）**。通常情況下，Linux 被打包成供桌上型電腦和伺服器使用的 Linux 發行版本。一些流行的主流 Linux 發行版本，包括 Debian（及其衍生版本 Ubuntu），Fedora 和 openSUSE 等。 Linux 得名於電腦業餘愛好者 Linus Torvalds。

###HTTP 伺服器

>  Web 伺服器一般指網站伺服器，是指駐留於因特網上某種類型計算機的程式，可以向瀏覽器等 Web 客戶端提供文件，也可以放置網站檔案，讓全世界瀏覽；可以放置資料檔案，讓全世界下載。

目前最主流的三個 Web 伺服器是 Apache、Nginx、IIS。

####Apache

Apache 是世界使用排名第一的 Web 伺服器軟體。它可以執行在幾乎所有廣泛使用的計算機平臺上，由於其跨平臺和安全性被廣泛使用，是最流行的Web 伺服器端軟體之一。它快速、可靠並且可通過簡單的 API 擴充，將 Perl/Python 等直譯器編譯到伺服器中。

####Nginx

Nginx 是一款輕量級的 Web 伺服器/反向代理伺服器及電子郵件（IMAP/POP3）代理伺服器，並在一個 BSD-like 協議下發行。由俄羅斯的程式設計師 Igor Sysoev 所開發，供俄國大型的入口網站及搜尋引擎 Rambler（俄文：Рамблер）使用。其特點是佔有記憶體少，併發能力強，事實上 Nginx 的併發能力確實在同類型的網頁伺服器中表現較好，中國大陸使用 Nginx 網站使用者有：百度、新浪、網易、騰訊等。

####IIS

Internet Information Services（IIS，網際網路資訊服務），是由微軟公司提供的基於執行 Microsoft Windows 的網際網路基本服務。最初是Windows NT 版本的可選包，隨後內建在 Windows 2000、Windows XP Professional 和 Windows Server 2003 一起發行，但在 Windows XP Home 版本上並沒有 IIS。

####代理伺服器

> 代理伺服器（Proxy Server）是一種重要的伺服器安全功能，它的工作主要在開放系統互聯(OSI)模型的會話層，從而起到防火牆的作用。代理伺服器大多被用來連線 INTERNET（國際網際網路）和 Local Area Network（區域網）。

Web 快取
---

Web 快取是顯著提高 Web 站點的效能最有效的方法之一。主要有:

- 資料庫端快取
- 應用層快取
- 前端快取
- 客戶端快取

不同的快取類型適用於不同的環境下使用。

###資料庫端快取

這個可以用以“空間換時間”來說。比如建一個表來儲存另外一個表某個類型的資料的總條數，在每次更新資料的時候同時更新資料表和統計條數的表。在需要獲取某個類型的資料的條數的時候，就不需要 select count 去查詢，直接查詢統計表就可以了，這樣可以提高查詢的速度和資料庫的效能。

###應用層快取

應用層快取這塊跟開發人員關係最大，也是平時經常接觸的。

- 快取資料庫的查詢結果，減少資料的壓力。這個是大型網站必須做的。
- 快取磁碟檔案的資料。比如常用的資料可以放到記憶體，不用每次都去讀取磁碟，特別是密集計算的程式，比如中文分詞的詞庫。
- 快取某個耗時的計算操作，比如資料統計。

應用層快取的架構也可以分幾種：

- 嵌入式，也就是快取和應用在同一個機器。比如單機的檔案快取，java 中用 hashMap 來快取資料等等。這種快取速度快，沒有網路消耗。
- 分散式快取，把快取的資料獨立到不同的機器，通過網路來請求資料，比如常用的 memcache 就是這一類。

分散式快取一般可以分為幾種：

- 按應用切分資料到不同的快取伺服器，這是一種比較簡單和實用的方式。
- 按照某種規則（hash，路由等等）把資料儲存到不同的快取伺服器
- 代理模式，應用在獲取資料的時候都由代理透明的處理，快取機制有代理伺服器來處理

###前端快取

我們這裡說的前端快取可以理解為一般使用的 cdn 技術，利用 squid 等做前端緩衝技術，主要還是針對靜態檔案類型，比如圖片、css、js、html 等靜態檔案。

###客戶端快取

瀏覽器端的快取，可以讓使用者請求一次之後，下一次不在從伺服器端請求資料，直接從本地快取讀取，可以減輕伺服器負擔也可以加快使用者的訪問速度。

###HTML5 離線快取

application cahce 是將大部分圖片資源、js、css 等靜態資源放在 manifest 檔案配置中。當頁面開啟時通過 manifest 檔案來讀取本地檔案或是請求伺服器檔案。

離線訪問對基於網路的應用而言越來越重要。雖然所有瀏覽器都有快取機制，但它們並不可靠，也不一定總能起到預期的作用。HTML5 使用 ApplicationCache 介面可以解決由離線帶來的部分難題。前提是你需要訪問的 Web 頁面至少被線上訪問過一次。

可配置
---

讓我們寫的 Web 應用可配置是一項很有挑戰性，也很實用的技能。

起先，我們在本地開發的時候為本地建立了一套環境，也建立了本地的配置。接著我們需要將我們的包部署到測試環境，也生成了測試環境的相應配置。這其中如果有其他的環境，我們也需要建立相應的環境。最後，我們還需要為產品環境建立全新的配置。

下圖是 Druapl 框架的部署流:

![Drupal Deployment Flow](assets/article/chapter4/deployment-flow.png)

在不同的環境下，他們使用不同的 Content。這些 Content 的內容不僅僅可以是一些系統相當的配置，也可以是一些不同環境下的 UI 等等。而在這其中也會涉及到一些比較複雜的知識，下面只是做一些簡單的介紹。

###環境配置

最常見的例子就是我們需要在不同的環境有不同的配置。大原則就是我們不能直接使用產品的環境測試，因此我們就需要為不同的環境配置不同的資料庫：

 - 開發環境。即開發者用於開發的環境，大部分的資料都是由我們自己注入的，在開發的過程中我們也會新增一些資料。
 - 整合測試環境/測試環境。和開發環境一樣，這些資料也是由我們注入的，而這些資料主要用於測試目的。當應用出現Bug時，我們可能就需要新增新的測試及其測試資料。
 - 模擬環境（Staging)。在軟體最終釋出前，開發或者設計人員對軟體進行調整後可以及時預覽改變的測試環境，這個環境更接近於產品最終釋出後的執行環境。因此，這個環境的資料一般來說就是產品環境的一些舊資料——可能是幾個月前，幾年前的資料。
 - 產品環境。即線上環境，都是真實的使用者資料。

因此從理論上來說，我們就需要4~5個不同的資料庫配置。而這些不同的資料庫配置並不代表著他們使用的是相同的資料庫。我們可以在本地環境使用 SQLite，而在我們的產品環境使用 MySQL。不過，最好的情況是我們應該使用同一個配置。這樣當出現問題的時候，我們也很容易排查、

而除了資料庫配置之外，我們還有一些其他配置。因此針對於不同的環境的配置最好獨立地寫在不同的檔案裡。並且這些配置最好可以以檔名來區分，如針對於開發環境，就是 ``dev.config.js``，針對於測試環境就是 ``test.config.js``。

因此，為了實現不同的環境使用不同的配置，我們就需要有一個變更控制。如果我們只有相應的配置，而沒有對應的執行機制那就有問題了。

###執行機制

當我們的應用程式在伺服器上執行得好好的時候，我們可能就不想因為修改配置而去重啟機器，這時候我們就需要配置熱載入。即我們修改配置後，不需要重啟服務即可以使用新的配置。對應的還有一種，便是我們需要重啟機器才能實現配置。

無論是哪種方式都需要修改配置來實現。而在我們使用的過程中熱載入可能需要消耗一些系統資源，因為我們的系統需要不斷地讀取配置的狀態並對其進行判斷。並且如果我們的應用執行在多個機器上的時候，我們可能需要一個個的上支個性。而如果是冷啟動的話，就可以考慮使用自動部署的方式來完成。

對應的，我們也需要在我們的程式碼中實現判斷這些配置的邏輯。

###功能開關

當我們上線了新功能之後，這時候如果有個 Bug，那麼我們是下線麼？要知道這個版本里麵包含了很多的 Bug 修復。如果在設計這個新功能的時候，有一個可配置的 Toogle，那麼我們就不需要下線了。只需要切換這個toggle，就可以解決問題了。

對於有多套環境的開發來說，如果我們針對不同的環境都有不同的配置，那麼這個靈活的開發會幫助我們更好的開發。

####Feature Toggle

它是一種允許控制線上功能開啟或者關閉的方式，通常會採取配置檔案的方式來控制。其過程如下圖所示：

![Feature Toggle](assets/article/chapter4/feature-toggle.png)

當我們需要 A 功能的時候，我們就只需要把 A 功能的開關開啟。當我們需要 B 功能，而不需要 A 功能的時候，我們就可以把相應的功能關掉。像在 Java 裡的 Spring 框架，就可以用 PropertyPlaceHolder 來做相似的事。使用 bean 檔案建立一個 properties

```xml
<util:properties id="myProps" location="WEB-INF/config/prop.properties"/>
```

然後注入這個值：

```
@Value("#{myProps['message']}")
```

我們可以直接判斷這個值是否是真，從而顯示這個內容。

```
<spring:eval expression="@myProps.message" var="messageToggle"/>

<c:if test="${messageToggle eq true}">
    message
</c:if>
```

這是一種很實用，而且很有趣的技術。

參考書籍：**《配置管理最佳實踐》**

自動化部署
---

優化開發流程有一個很重要的步驟就是：讓部署自動化。通過部署自動化，我們可以大大縮減開發週期，加快軟體交付流程。下圖是一個自動化部署的流程圖：

![自動化部署](assets/article/chapter4/auto-deployment.png)

從下圖中我們可以得到下面的五個步驟：

 - 獲取源碼
 - 獲取依賴
 - 構建軟體包
 - 生成/上傳安裝包
 - 目標平臺安裝/配置

這個過程可能和之前的 Web 項目構建過程差不多，然而卻多了好幾步。

在前面的章節裡，我們已經使用了版本管理系統來管理我們的源碼。因此，在這裡對於獲取源碼的介紹就比較簡單了——我們只需要在我們的 CI（持續整合）伺服器上使用 ``git clone`` 這一類的方法來獲取我們的源碼即可。

###依賴與包倉庫

獲取完源碼後，我們就需要開始下載軟體包依賴。無論是 Python、Ruby、Java，還是 JavaScript 都需要這樣的一個過程。軟體開發已經從大教堂式的開發走向了集市——開源軟體改變了這一切。

![大教堂與集市](assets/article/chapter4/hierarchy-vs-graph.png)

過去我們需要在大系統的內部構建所使用的依賴，現在我們更多地藉助於外部的庫來實現這些功能。這也意味著，如果在這一個節點裡出現了意外——軟體被刪除，那麼這個系統將陷入癱瘓的狀態。如之前在 NPM 圈發生了“一個 17 行的模組引發的血案”——即 left-pad 工具模組被作者從 NPM 上撤下，所有直接或者間接依賴這個模組的 NPM 的軟體包都掛掉了。因為我們依賴於公有的包服務，所以系統便嚴重依賴於外部條件。

這時候一種簡單、有效的方案就是搭建自己的包服務。如使用 Java 技術棧的項目，就會使用 Nexus 搭建自己的 Maven 私有服務。我們的軟體依賴包將會依賴於我們自己的服務，此時會產生的主要問題可能就是：我們的軟體包不是最新的。但是對於追求穩定的項目來說，這個並不是必須的需求，反而是個優勢。

###構建軟體包

在一些編譯型語言裡，在我們執行包測試後，將會得到一個軟體包。如 Jar 包，它是 Java 所特有的一種壓縮文件。Jar 包無法直接安裝使用，雖然我們可以直接執行這個 Jar 包，但是我們需要通過一些手段將這個 Jar 包拷貝到我們的伺服器上，然後執行。在特定的時候，我們還需要修改配置才能完成我們的工作。

因此，使用 RPM 或者 DEB 包會是一種更好的選擇。RPM 全稱是 Red Hat Package Manager（Red Hat包管理器），它工作於 Red Hat Linux 以及其它 Linux 和 UNIX 系統，可被任何人使用。如下圖是 RPM 包的構建過程：

![RPM Build Process](assets/article/chapter4/rpm-deploy.jpg)

要構建一個標準的 RPM 包，我們需要建立 .spec檔案，這個檔案包含軟體打包的全部資訊——如包的 Summary、Name、Version、Copyright、Vendor 等等。在產生完這一個配置檔案後，執行 rpmbuild 命令，系統會按照步驟生成目標 RPM 包。

###上傳和安裝軟體包

生成對應的軟體包後，我們就可以將其上傳到 Koji 上，它是 Fedora 社羣的編譯系統。如下圖所示：

![RPM Build Process](assets/article/chapter4/rpm-koji.jpg)

如果我們已經對我們的所有目標作業系統配置過，即配置好了軟體源，那麼我們就可以直接在我們的伺服器上使用包管理工具安裝，如``yum install``。

資料分析
===

有時候，對於我們的決定只要有一點點的資料支援就夠了。一點點的變化，可能就決定了我們產品的好壞。我們可能會因此而作出一些些改變，這些改變可能會讓我們打敗巨頭。

這一點和 Growth 的構建過程也很相像，在最開始的時候我只是想制定一個成長路線。而後，我發現這好像是一個不錯的 idea，我就開始去構建這個 idea。於是它變成了 Growth，這時候我需要依靠什麼去分析使用者喜歡的功能呢？我沒有那麼多的精力去和那麼多的人溝通，也不能去和那麼多的人溝通。

我只能借助 Google Analytics 來收集使用者的資料。從這些資料裡去學習一些東西，而這些就會變成一個新的想法。新的想法在適當的時候就會變成一個產品，接著我們就開始收集使用者資料，然後迴圈。

構建-衡量-學習
---

構建-衡量-學習是在《精益創業》中的一個核心概念，這結合了客戶開發、敏捷軟體開發方法和精益生產實踐。它們是非常重要的一個迴圈：

![資料分析過程](assets/article/chapter5/lean-analytics.png)

這一過程不僅可以改進我們的產品，也可以用於初創企業。它並不是獨立的一個環節，實現上它應該是一整個環節：我們根據我們的想法去建立產品，在使用產品的過程中收集一些資料，再依據這些資料來改進我們的產品。

###想法-構建

想法實際上便是解決一個痛點的解決方案。如果你和我一樣也經常記錄自己的想法，就會發現每個月裡，你總會跳出一個又一個的想法。正如，我在那篇《[如何去管理你的 Idea](https://www.phodal.com/blog/use-github-manage-idea/)》中說的一樣：

> 我們經常說的是我們缺少一個 Idea。過去我也一直覺得我缺少一些 Idea，今天發現並非如此，我們只是缺少記錄的手段。

我們並不缺少 Idea，只是一直沒有去記錄。隨著時間的增長，我發現我的 GitHub 上的 Idea 牆([ideas](https://github.com/phodal/ideas/issues))一直在不斷地增加。以至於，我有一個新的 Idea 就是整理這個 Idea 牆。

而作為一個程式設計師，我們本身就可以具備構建一個系統的能力，只是對於大多數人來說需要多加的練習。有意思的一點是，這裡的構建系統與一般的構建系統有一點不太一樣，我們需要快速地構建出一個 MVP 產品。MVP 簡單地來說，就是最小可用的產品。如下圖的右邊所示：

![MVP](assets/article/chapter5/mvp.png)

在每一層級上都實現一定的功能，使得這個系統可用，而非構建一個非常完整的系統。隨後，我們就可以尋找一些種子使用者來改進我們的產品。

###產品-衡量

按照上面的步驟，到了這裡應該就是客戶開發。而如《精益客開發》一書所說，客戶開發可以分成五個步驟：

 - 形成假設。即我們覺得用
 - 找到可以交談的潛在客戶
 - 提出恰當的問題
 - 從答案中找到有用的資訊
 - 弄明白現階段需要構建什麼樣的產品來保持下一個學習迴圈

在整個過程中，我們其實就是在瞭解我們的客戶是誰，以及他們的需求。並且在這個過程中，我們可以為開發確認出清晰的假設，一點點地打造出使用者喜愛的產品。

###資料-學習

當我們收集到一定的使用者資料，如網站、應用的資料，就可以開始分析資料。如《精益創業》所說，在分析資料之前，我們需要確定我們的增長模型，即：

 - 黏著式增長引擎——其重點是讓使用者成為回頭客，即讓客戶持續使用我們的產品。這就意味著，我們在分析資料和學習的過程中，要側重於關注流失率和使用頻率。
 - 病毒式增長引擎——其只做一件事：讓名聲傳播出去。即通過使用者間的不斷傳播來擴散產品，我們需要考慮所謂的**病毒式傳播係數**，還有使用者之間的特定行為。
 - 付費式增長引擎——賺錢與否是識別商業模式是否可持續的指標。

 針對不同的增長引擎有不同的學習過程，如媒體網站，我們通過不同的方式來匯入流量，這些流量最終會有一些會轉化成價值。這些價值會以不同的形式出現，如訂閱率、線上參與度、廣告營收等等。

 而從這些資料中學習就需要一些特殊的技巧，詳情請見下面的參考書籍。

 參考書籍：

  - 《精益資料分析》
  - 《精益客戶開發》
  - 《精益創業》

資料分析
---

資料分析是一個很有意思的過程，我們可以簡單地將這個過程分成四個步驟：

 - 識別需求
 - 收集資料
 - 分析資料
 - 展示資料

值得注意的是：在分析資料的過程中，需要不同的人員來參與，需要跨域多個領域的知識點——分析、設計、開發、商業和研究等領域。因此，在這樣的領域裡，迴歸敏捷也是一種不錯的選擇（源於：《敏捷資料科學》）：

 - 通才高於專長
 - 小團隊高於大團隊
 - 使用高階工具和平臺：雲端計算、分散式系統、PaaS
 - 持續、迭代地分享工作成果，即使這些工作未完成

###識別需求

在我們開始分析資料之前，我們需要明確一下，我們的問題是什麼？即，我們到底要幹嘛，我們想要的內容是什麼。

> 識別資訊需求是確保資料分析過程有效性的首要條件，可以為收集資料、分析資料提供清晰的目標。

當我們想要提到我們的網站在不同地區的速度時，就需要去探索我們的使用者主要是在哪些地區。即，現在這是我們的需求。我們已經有了這樣的一個明確的目標，下面要做起來就很輕鬆了。

###收集資料

那麼現在新的問題來了，我們的資料要從哪裡來？

對於大部分的網站來說，都會有訪問日誌。但是這些訪問日誌只能顯示某個 IP 進入了某個頁面，並不能詳細地介紹這個使用者在這個頁面待了多久，做了什麼事。這時候，就需要依賴於類似 Google Analytics 這樣的工具來統計網站的流量。還有類似於New Relic這樣的工具來統計使用者的一些行為。

在一些以科學研究為目的的資料收集中，我們可以從一些公開的資料中獲取這些資料。

而在一些特殊的情況裡，我們就需要通過爬蟲來完成這樣的工作。

###分析資料

現在，我們終於可以真正的去分析資料了——我的意思是，我們要開始寫程式碼了。從海量的資料中過濾出我們想要的資料，並通過演算法來對其進行分析。

一般來說，我們都利用現有的工具來完成大部分的工作。要使用哪一類工具，取決於我們要分析的資料的數量級了。如果只是一般的數量級，我們可以考慮用 R 語言、Python、Octave 等單機工具來完成。如果是大量的資料，那麼我們就需要考慮用 Hadoop、Spark 來完成這個級別的工作。

而一般來說，這個過程可能是要經過一系列的工具才能完成。如在之前我在分析我的部落格的日誌時(1G左右)，我用 Hadoop + Apache Pig + Jython 來將日誌中的 IP 轉換為 GEO 資訊，再將 GEO 資訊儲存到 ElasticSearch 中。隨後，我們就可以用 AMap、leaflet 這一類 GEO 庫將這些點放置到地圖上。

###展示資料

現在，終於來到我最喜歡的環節了，也是最有意思，但是卻又最難的環節。

我們過濾資料，得到想要的內容後，就要去考慮如何視覺化這些資料。在我熟悉的 Web GIS領域裡，我可以視覺化出我過濾後的那些資料。但是對於我不熟悉的領域，要視覺化這些資料不是一件容易的事。在少數情況下，可以使用現有的工具完成需求，多數情況下，我們也需要寫相當的程式碼才能將資料最後視覺化出來。

而在以什麼形式來展示我們的資料時，又是一個問題。如一般的資料結果，到底是使用柱形圖、條形圖、折線圖還是面積圖？這要求我們有一些 UX 方面的經驗。

參考來源: **精益資料分析**。

使用者資料分析：Google Analytics
---

Google Analytics 是一個非常讚的分析工具，它不僅可以用於 Web 應用，也可以用於移動應用。

###受眾群體

如下圖是 Growth 應用最近兩星期的資料：

![Growth GA](assets/article/chapter5/growth-ga.png)

這是 Google Analytics 中的“受眾群體”的概覽，在這個檢視中：

1. 折線圖就是每天的使用者數。
2. 下面會有使用者數、會話、螢幕瀏覽量等等的一些資訊。
3. 右角的餅圖則是回訪問使用者和新使用者的對比。
4. 最下方便是受眾的資訊——國家、版本等等。

從圖中，我們可以讀取一些重要的資訊，如使用者的停留時間、主要面向的使用者等等。在瀏覽器版本會有：

1. 瀏覽器與作業系統
2. 移動裝置

這樣的重要資料，如下表是我網站 20160104-20160120 的訪問資料：

瀏覽器|會話|新會話百分比
-----|----|----
Chrome|5048|75.99%
Firefox|694|78.39%
Safari|666|78.68%
Internet Explorer|284|87.68%
Safari (in-app)|92|86.96%
Android Browser|72|87.50%
Edge|63|79.37%
Maxthon|51|68.63%
UC Browser|41|80.49%
Opera|34|64.71%

可以從上表中看到訪問我網站的使用者中，IE 只佔很小的一部分——大概4%，而 Chrome + Safari + Firefox 加起來則近90%。這也意味著，我可以完全不考慮 IE 使用者的感受。

類似於這樣的資料在我們決定對某個瀏覽器的支援情況時是非常有幫助的。也會加快開發，我們可以工作於主要的瀏覽器上。

###流量獲取

除此，不得不說的一點就是流量獲取，如下圖所示是我部落格的熱門渠道：

![Phodal.com Traffic](assets/article/chapter5/phodal-traffic.png)

可以直接得到一個不錯的結論是我的部落格的主要流量來源是搜尋引擎，再細細一看資料：

來源/媒介 | 會話
----------|---------
baidu / organic | 2031
google / organic | 1314
(direct) / (none) | 1311
bing / organic | 349
github.com / referral | 281

主要流量來源就是 Baidu 和 Google，看來國人還是用百度比較多。那我們就可以針對 SEO 進行更多的優化：

1. 加快訪問速度
2. 更表意的 URL
3. 更好的標題
4. 更好的內容

等等等。

除此，我們可以分析使用者的行為，如他們訪問的主要網站、URL 等等。

###移動應用

除此，我們還可以使用它來分析移動應用，不過這受限於 Google 在國內的訪問程度。如下圖是 GA 收到的應用的使用資料：

![Growth 應用資料](assets/article/chapter5/ga-app.jpg)

我們也可以從上面看到 APP 的安裝來源等等。

網站效能
---

網站效能直接影響到了網站的響應時間、吞吐量等等，也是運維、開發一系列技術的體現。

###網站效能監測

網站效能監測

> 網站可用性是網站效能監測的重要指標之一，表示在一段時間內，網站處於“正常狀態”的機率。

 - DNS 解析
 - 記憶體、硬碟等等
 - 網頁開啟速度

####應用效能指數

> Apdex 聯盟，一個由眾多網路分析技術公司和測量工業組成的聯盟組織，它們聯合起來開發了“應用效能指數”即“Apdex”(Application Performance Index)，用一句話來概括，Apdex 是使用者對應用效能滿意度的量化值。它提供了一個統一的測量和報告使用者體驗的方法，第一次把終端使用者的體驗和應用效能聯絡在了一起。

任務響應時間定義為：當使用者操作（滑鼠點選、輸入、回車）開始到系統（客戶機、網路、伺服器）響應從而使用者能繼續這個過程所經過的時間。這些等待時間定義了應用程式的“響應度”。該指數是基於應用程式響應度的三個方面：

 - 滿意:使用者充分工作。這就是目標時間（T秒），即在此時間裡使用者的工作沒有因應用程式的響應時間而受阻，如3秒。
 - 容忍:使用者感覺到響應滯後，響應時間大於 T，但能繼續這個過程，如3～12秒。
 - 挫折:響應時間大於 F 秒的效能是不能接受的，使用者可能放棄這個過程。F 等於 T×4，在本例子中為12秒。


###網站效能

針對網站效能優化領域，網上已經有相當多的總結，這裡只羅列一些常見（我用過）的策略。

#####減少 HTTP 請求

從網上查詢的情況分類來看，有下面的一些情況：

 - 合併 JavaScript 和 CSS。只是這種方式需要好好評估，因為合併過多的 JavaScript，可能會導致 JavaScript 檔案過大。一個大的檔案將增加 Load時間，導致不好的使用者體驗。
 - CSS Sprites。即將一個頁面涉及到的所有零星圖片都包含到一張大圖中去。值得注意的是，像 Logo 這一類檔案將不要加到裡面去了。
 - 拆分初始化負載。將頁面載入時需要的一堆 JavaScript 檔案，分成兩部分：渲染頁面所必需的和其他的。頁面初始化時，只載入必須的，其餘的等會載入。
 - 劃分主域。將資源劃分的請求劃分到幾個不同的域上，來加速資源請求。

對於我這樣的懶人來說，我使用 Google 出品的 [PageSpeed](https://developers.google.com/speed/pagespeed/?hl=zh-CN)。它主要的功能是針對前端頁面而進行伺服器端的優化，對前端設計人員來說，可以省去優化 css、js 以及圖片的過程。它可以對 CSS 和 JavaScript 壓縮、合併、級聯、內聯，生成一個新的 Script 和 CSS 檔案 。還有影象優化：剝離後設資料、動態調整，重新壓縮，如針對 Chrome 瀏覽器生成 WebP 檔案。還可以推遲影象和 JavaScript 載入。

####頁面內部優化

HTML 頁面內的優化的目的便是：**儘快渲染出頁面**。常見的優化策略便是：

 - 將 CSS 放在頂部，即早點渲染出頁面及其樣式。
 - 將 JavaScript 放在底部。如果有後臺渲染機制，那麼就應該將 JS 放到頁面底部來加速頁面載入。如果是單頁面應用，那麼這個 JS 就應該在頁面頂部。
 - 壓縮 HTML。在我們寫模板的過程中，一些判斷可能會導致頁面有過多的空格。壓縮這些 HTML，可以稍微提高一下頁面速度。

這裡的大部分內容都應該通過修改程式碼來完成。

####啟用快取

前面的快取一節裡，我們說過了一些快取的策略，我們再稍微提一下。

 - 後臺優化，如資料庫端快取
 - 啟用頁面快取，即應用層快取

####減少下載量

簡單地來說，就是減少對伺服器的請求：

 - 使用 CDN
 - 使用外部 JavaScript 和 CSS
 - 快取：使用 gzip 壓縮、新增 Expires 頭、配置 ETag、使 AjaX 可快取

####網路連線上的優化

主要就是對域名到伺服器進行優化，因此從方法上有：

 - DNS 域名解析加速
 - 減少 DNS 查詢

SEO
---

> 這是一個老的，有些過時確非常普遍，甚至每一個程式設計師都知道的關於搜尋引擎優化的技術，所以，我只一筆帶過。

**搜尋時發生什麼了?**

 - 使用者輸入查詢內容
 - 查詢處理以及分詞技術
 - 確定搜尋意圖及返回相關、新鮮的內容

![search-engine-arch](assets/article/chapter5/search-engine-arch.jpg)

**為什麼需要 SEO?**

這是一個有趣的問題，答案是``為網站帶來更多的流量``。

###爬蟲與索引

我們先看看來自谷歌的爬蟲工作的一點內容

> 抓取是 Googlebot 發現新網頁並更新這些網頁以將網頁新增到 Google 索引中的過程。

> 我們使用許多計算機來獲取（或"抓取"）網站上的大量網頁。執行獲取任務的程式叫做 Googlebot（也被稱為漫遊器或資訊採集軟體）。Googlebot 使用演算法來進行抓取：計算機程式會確定要抓取的網站、抓取頻率以及從每個網站中獲取的網頁數量。

> Google 的抓取過程是根據網頁網址的列表進行的，該列表是在之前進行的抓取過程中形成的，且隨著網站管理員所提供的站點地圖資料不斷進行擴充。Googlebot 在訪問每個網站時，會檢測每個網頁上的連結，並將這些連結新增到它要抓取的網頁列表中。新建立的網站、對現有網站所進行的更改以及無效連結都會被記錄下來，並用於更新 Google 索引。

也就是如原文所說:

> 谷歌的爬蟲(又或者說蜘蛛)能夠抓取你整個網站索引的所有頁。

**為什麼谷歌上可以搜尋整個網際網路的內容**？因為，他解析並儲存了。而更有意思的是，他會為同樣的內容建立一個索引或者說分類，按照一定的相關性，針對於某個關鍵詞的內容。

PageRank 對於一個網站來說是相當重要的，只是這個相比也比較複雜。包括其他網站連結向你的網站，以及流量，當然還有域名等等。

###什麼樣的網站需要 SEO？

下圖是我的部落格的流量來源

![What Site Need SEO](assets/article/chapter5/my-website-seo.jpg)

正常情況下除了像``騰訊``這類的``QQ空間``自我封閉的網站外都需要 SEO，或者不希望洩露一些使用者隱私如``Facebook``、``人人``等等。


 - 如果你和我的網站一樣需要靠搜尋帶來流量
 - 如果你的網站只有很少的使用者訪問，卻有很多的內容。
 - 如果你的網站為一個公司、企業工作以帶來業務。
 - 。。。


**SEO 與程式設計的不同之處?**

SEO 與程式設計的最大不同之處在於: **程式設計的核心是技術，SEO 的核心是內容**。

內容才是 SEO 最重要的組成部分，這也就是騰訊複製不了的東西。

###SEO 基礎知識

**確保網站是可以被索引的**

一些常見的頁面不能被訪問的原因

 - 隱藏在需要提交的表格中的連結
 - 不能解析的 JavaScript 指令碼中的連結
 - Flash、Java 和其他外掛中的連結
 - PowerPoint 和 PDF 檔案中的連結
 - 指向被 meta Robtots 標籤、rel="NoFollow" 和 robots.txt 遮蔽的頁面的連結
 - 頁面上有上幾百個連結
 - frame（框架結構）和 iframe 裡的連結

對於現在的網站來還有下面的原因，通過來說是因為內容是動態生成的，而不是靜態的

 - 網站通過 WebSocket 的方法渲染內容
 - 使用諸如 Mustache 之類的 JS 模板引擎

**什麼樣的網頁可以被索引**

 - 確保頁面可以在沒有 JavaScript 下能被渲染。對於現在 JavaScript 語言的使用越來越多的情況下，在使用 JS 模板引擎的時候也應該注意這樣的問題。
 - 在使用者禁用了 JavaScript 的情況下，保證所有的連結和頁面是可以訪問的。
 - 確保爬蟲可以看到所有的內容。那些用 JS 動態載入出來的對於爬蟲來說是不友好的
 - 使用描述性的錨文字的網頁
 - 限制的頁面上的連結數量。除去一些分類網站、導航網站之類有固定流量，要不容易被認為垃圾網站。
 - 確保頁面能被索引。有一指向它的 URL
 - URL 應該遵循最佳實踐。如 blog/how-to-driver 有更好的可讀性

**在正確的地方使用正確的關鍵詞**

 - 把關鍵詞放 URL 中
 - 關鍵詞應該是頁面的標籤
 - 帶有 H1 標籤
 - 圖片檔名、ALT 屬性帶有關鍵詞。
 - 頁面文字
 - 加粗文字
 - Descripiton 標籤


###內容

對於技術部落格而言，內容才是最需要考慮的因素。

可以考慮一下這篇文章，雖然其主題是以 SEO 為主
[使用者體驗與網站內容](http://www.phodal.com/blog/user-experience-writing-web-content/)

不可忽略的一些因素是內容才是最優質的部分，沒有內容一切 SEO 都是無意義的。

####複製內容問題

一個以使用者角度考慮的問題: **使用者需要看到多元化的搜尋結果**

所以對於搜尋引擎來說，複製帶來的結果：

 - 搜尋引擎爬蟲對每個網站都有設定的爬行預算，每一次爬行都只能爬行 trpgr 頁面數
 - 連向複製內容頁面的連結也浪費了它們的連結權重。
 - 沒有一個搜尋引擎詳細解釋他們的演算法怎樣選擇顯示頁面的哪個版本。

於是上文說到的作者給了下面的這些建議:

 > 避免從網上覆制的內容（除非你有很多其他的內容彙總，以使它看起來不同 - 我們做頭條，對我們的產品頁面的新聞片段的方式） 。這當然強烈適用於在自己的網站頁面以及。內容重複可以混淆搜尋引擎哪些頁面是權威（它也可能會導致罰款，如果你只是複製貼上別人的內容也行） ，然後你可以有你自己的網頁互相競爭排名！

 > 如果你必須有重複的內容，利用相對=規範，讓搜尋引擎知道哪個 URL 是一個他們應該被視為權威。但是，如果你的頁面是另一個在網路上找到一個副本？那麼開始想出一些策略來增加更多的文字和資訊來區分你的網頁，因為這樣重複的內容是決不可能得到好的排名。

——待續。

####保持更新

谷歌對於一個一直在更新的部落格來說會有一個好的排名，當然只是相對的。

對於一個技術部落格作者來說，一直更新的好處不僅可以讓我們不斷地學習更多的內容。也可以保持一個良好的習慣，而對於企業來說更是如此。如果我們每天去更新我們的部落格，那麼搜尋引擎對於我們網站的收錄也會變得越來越加頻繁。那麼，對於我們的排名及點選量來說也算是一個好事，當我們可以獲得足夠的排名靠前時，我們的 PR 值也在不斷地提高。

更多內容可以參考:[Google Fresh Factor](http://www.seomoz.org/blog/google-fresh-factor)

####網站速度

> 谷歌曾表示在他們的演算法頁面載入速度問題，所以一定要確保你已經調整您的網站，都服從最佳做法，以使事情迅速

過去的一個月裡，我試著提高自己的網站的速度，有一個相對好的速度，但是受限於``域名解析速度``以及 ``VPS``。

[網站速度分析與 traceroute
](http://www.phodal.com/blog/use-traceroute-analyse-person-homepage-speed/)

[UX 與網站速度優化——部落格速度優化小記
](http://www.phodal.com/blog/ux-and-improve-website-load-speed/)

[Nginx ngx_pagespeed nginx 前端優化模組編譯](http://www.phodal.com/blog/nginx-with-ngx-pagespeed-module-improve-website-cache/)

####保持耐心

> 這是有道理的，如果你需要考慮谷歌機器人抓取最新的頁面並處理和更新與新內容對應的索引的時間因素。

> 而這可能是相當長一段時間，尤其是當你正在處理 PB 級的內容時。

SEO 是一個長期的過程，很少有網站可以在短期內有一個很好的位置，除非是一個熱門的網站，然而在它被發現之前也會經歷這個過程。

####流量

在某種意義上，這個是提高 PR 值，及網站流量的另外一個核心，除了內容以外的核心。

 - 流量引導是 SEO 的基礎部分。除非你有一個異常強大的品牌，不需要幹什麼就能吸引到流量。
 - 流量引導永不停止。這是不間斷營銷網站的過程。

關於流量的內容有太多，而且當前沒有一個好的方法獲取流量，雖然在我的網站已經有了。

Links to Your Site

Total links

``5,880``

> 同時引導更多的流量和更有利更相關的流量的帶來的幫助一樣多。如果你有你的內容的分銷合作伙伴，或者你建立一個小工具，或其他任何人都會把流量引導回你的網站上 - 你可以通過確保各個環節都有最佳的關鍵字錨文字從而大大提高搜尋的相關性。您還應該確保所有流量到您的網站指向你的主域名（ http://www.yourdomain.com ，像 http://widget.yourdomain.com 不是一個主域名） 。另外，你要儘可能多的聯絡，以包含適當的替代文字。你的想法。

> 另外，也許不太明顯的方式，建立連結（或者至少流量）是使用社交媒體 - 所以設定你的 Facebook ，Twitter 和谷歌，每當你有新的連結一定要分享。這些通道也可以作為一個有效的渠道，推動更多的流量到您的網站。

由社交渠道帶來的流量在現在已經越來越重要了，對於一些以內容為主導而且處於發展初期的網站，可以迅速帶來流量。一些更簡單的辦法就是交換連結，總之這個話題有些沉重，可能會帶來一些負面的影響，如黑帽 SEO。。。。

**參考來源**:

《SEO 藝術》(The Art of SEO)

UX 入門
---

使用者體驗設計（英語：User Experience Design），是以使用者為中心的一種設計手段，以使用者需求為目標而進行的設計。設計過程注重以使用者為中心，使用者體驗的概念從開發的最早期就開始進入整個流程，並貫穿始終。其目的就是保證：

- 對使用者體驗有正確的預估
- 認識使用者的真實期望和目的
- 在核心功能還能夠以低廉成本加以修改的時候對設計進行修正
- 保證核心功能同人機介面之間的協調工作，減少 BUG。

關於 UX 的定義我覺得在知乎上的回答似乎太簡單了，於是在網上尋尋覓覓終於找到了一個比較接近於答案的回答。原文是在: [Defining UX](http://deviseconsulting.com/defining-ux/)，這又是一篇不是翻譯的翻譯。

###什麼是 UX

使用者體驗設計（英語：User Experience Design），是以使用者為中心的一種設計手段，以使用者需求為目標而進行的設計。設計過程注重以使用者為中心，使用者體驗的概念從開發的最早期就開始進入整個流程，並貫穿始終。其目的就是保證：

 - 對使用者體驗有正確的預估
 - 認識使用者的真實期望和目的
 - 在核心功能還能夠以低廉成本加以修改的時候對設計進行修正
 - 保證核心功能同人機介面之間的協調工作，減少BUG。

**UX 需要什麼**

從下圖中我們可以看到一些 UX 所需要的知識體系：

![UX](assets/article/chapter5/ux_design.jpg)

即

 - 資訊構架
 - 構架
 - 工業設計
 - 人為因素  (人因學)
 - 聲音設計 (網頁設計中比較少)
 - 人機互動
 - 視覺化設計
 - 內容 (文字,視訊,聲音)

互動設計便是``使用者體驗設計的重點``。我們再來看看另外的這張圖片

![Fields Of User Experience Design](assets/article/chapter5/ux-field.jpg)

###什麼是簡單？

一個好的軟體應該是簡單的，並且是令人愉快的。

在不同的 UX 書籍裡，似乎就會說到【簡約至上】。簡單就是“單純清楚、不復雜”。而這裡的簡單並不僅僅只是不復雜那麼簡單。對於一個軟體來說，簡單實際上是你一下子就能找到你想要的東西，如：

![Search Phodal](assets/article/chapter5/search-phodal.jpg)

而我們並不可能在一開始就得到這樣的結果，這需要一個複雜的過程。而在這個過程開始之前，我們一定要知道的一點是：我們的使用者到底需要什麼?

如果我們無法知道這一點，而只是一直在假想客戶需要什麼，那麼這會變成一條死路。

接著在找尋的過程中，發現了一個有意思的圖，即精益畫布：

![Lean](assets/article/chapter5/lean.jpg)

首先，我們需要知道幾個使用者而存在的問題——即客戶最需要解決的三個問題。並且針對三個問題提出對應的解決方案，這也就是產品的主要功能。

那麼，這兩點結合起來對於使用者來說就是簡單——這個軟體能解決客戶存在的主要問題。

如果我們可以完成這部分功能的話，那麼這就算得上是一個有用的軟體。

###進階

而實際上“實用”則是位於使用者體驗的最底層，如下圖所示：

![UX](assets/article/chapter5/layer.jpg)

這時候就需要儘量往可用靠攏。怎樣對兩者進行一個簡單的劃分？

下圖就是實用的軟體：

![IE Alert](assets/article/chapter5/ie-alert.jpg)

而下圖就便好一點了：

![jQuery Popup](assets/article/chapter5/popup.jpg)

要達到可用的級別，並不是一件困難的事：**遵循現有軟體的模式**。

換句話說，這時候你需要的是一本 **Cookbook**。這本 **Cookbook** 上面就會列出諸多現有的設計模式，只需要參考便使用就差不多了。

同樣的，我便嘗試用《移動應用 UI 設計模式》一本書對我原有的軟體進行了一些設計，發現它真的可以達到這樣的地步。

而這也類似於在程式設計中的設計模式，遵循模式可以創造出不錯的軟體。

###使用者體驗要素

儘管對於這方面沒有非常好的認識，但是還是讓我們來看看我們現在可以到哪種程度。如在一開始所說的，我們需要滿足使用者的需求，這就是我們的目標：

![使用者體驗要素](assets/article/chapter5/ux-elements.png)

而在最上面的視覺設計則需要更專業的人來設計。

**參考目錄**

 - 《怦然心動——情感化設計互動指南》
 - 《使用者體驗要素》
 - 《移動應用UI設計模式》

認知設計
---

第一次意識到這本書很有用的時候，是我在策劃一個視訊。第二次，則是我在計劃寫一本書的時候。

###流

在《認知設計》一書中，提到了下面的學習體驗，即"流" (Flow)。而在我們學習的過程中，我們也會有類似的學習過程。

![Learn Design](assets/article/chapter5/learn-design.png)

如在早期我學習 Emacs 和 GNU/Linux 的時候，也曾經放棄過，雖然在當時我已經讀過 Linux 核心。然而，在應用之前進行理論學習並沒有卵用。

通常我們會有類似於下面的學習體驗，對於一本書來說有下面的體驗似乎也是一件很不錯的事:

1. 在最開始學習的時候，我們需要一點理論基礎，以及我們需要學點什麼。
2. 然後，我們需要構建一個簡單可用的系統，以獲取信心。如果這一步沒有想象中那麼簡單，那麼我們可能會放棄學習。或者等到某個時期成熟的時刻，如在我開始學習《設計模式》的時候，那麼本書的高度太高了。直到有一天，我瞭解到了一本叫《Head First 設計模式》的書，才重新把 GoF 的書看了一遍，發現其實也沒有想象中的難。
3. 接著在完成了某個功能之後，我可能繼續學習某個理論，用於支撐下一步計劃。
4. 在那之後，我覺得這一步可能也不是那麼難，因為已經有了前面的基礎。如果某一步失敗的時候，那麼我們可能會繼續尋找某些可靠的方案，又或者是理論支撐。
5. 。。。
6. 直到有一天，我們來到了一個瓶頸的前面，現有的方案已經不滿足我們的需求。對於這個問題，我們可能已經沒有一個更好的解決方案。於是，我們可能就需要建立一個輪子，只是在這時，我們不知道怎樣去造輪子。
7. 於是我們開始學習造輪子。
8. ....

只有保持一個學習的過程，才會讓我們在這一步步的計劃中不會退縮，也不能退縮。

持續交付
===

> 交付管道的建立和自動化是持續交付的基礎

持續整合
---

更關注程式碼質量。持續整合是為了確保隨著需求變化而變化的程式碼，在實現功能的同時，質量不受影響。因此，在每一次構建後會執行單元測試，保證程式碼級的質量。單元測試會針對每一個特定的輸入去判斷和觀察輸出的結果，而單元測試的粒度則用來平衡持續整合的質量和速度。

持續整合的核心價值在於[^CI]：

1. 持續整合中的任何一個環節都是自動完成的，無需太多的人工干預，有利於減少重複過程以節省時間、費用和工作量；
2. 持續整合保障了每個時間點上團隊成員提交的程式碼是能成功整合的。換言之，任何時間點都能第一時間發現軟體的整合問題，使任意時間釋出可部署的軟體成為了可能；
3. 持續整合還能利於軟體本身的發展趨勢，這點在需求不明確或是頻繁性變更的情景中尤其重要，持續整合的質量能幫助團隊進行有效決策，同時建立團隊對開發產品的信心。

###持續整合系統

在前面的內容裡，我們已經介紹了持續整合的各項基礎設施——如使用版本管理、編寫測試、自動化部署。要構建這樣的一個持續整合系統需要下面的內容：

 - 支援自動構建
 - 源碼伺服器
 - 持續整合伺服器

我們已經實現了前兩點，針對於第三點——持續整合伺服器，我們可以以 Jenkins 為例做一些簡單的說明。它是一種基於 Java 開發的持續整合工具，並提供了用於監控持續重複工作的軟體平臺。

它可以讓整個開發流程到部署都實現自動化。由於每個功能可以一點點的加在 build 中，那麼這樣就能保證每次的新 build 可以交付新的功能。同時，我們可以根據使用者的反饋情況及時調整開發方向，降低項目風險。

###持續整合流程

我們就可以對這個工作流展開深入介紹。持續整合主要就是要保證整個過程是**可持續**的。如下圖是一個持續整合的工作流：

![CI Workflow](assets/article/chapter6/ci.jpg)

不同的開發者在自己的機器上開發功能程式碼。在完成一定的本地提交後，這些程式碼將會提交給原始碼控制伺服器。不過，在那之前我們應該在本地跑測試來減少持續整合失敗的情況。接著，我們的CI會定時去獲取源碼伺服器是否有程式碼修改。如果有程式碼修改，那麼我們的整合伺服器將會獲取這些程式碼。然後，構建這個項目，執行測試，再輸出返回結果。最後，我們可以開發一些小工具來提醒使用者 CI 是否執行成功。

如果這個過程中 CI 執行失敗的話，那麼我們就不能再提交新的程式碼——除了修復 CI 的程式碼外。持續整合變紅不能過夜，要麼快速解決，要麼回退。

在這個過程中，有兩點值得注意，一個是小步前進，一個是遲早反饋。

####小步前進

小步前進是一系列步驟的集合，其目的是：整合越早問題越小。即當我們的程式碼越早的提交到源碼伺服器，那麼其他人就可以儘可能早的和我們的程式碼整合到一起。這也意味著，每天結束時，我們在本地的修改要儘可能小，並且這些修改還要保證不會破壞持續整合。

我們需要頻繁地在本地提交我們的程式碼，編寫獨立的測試——如果我們在最後才編寫測試，就會拖慢整個流程，它使得我們不能儘可能早的提交程式碼。

####儘早反饋

> 反饋越早，那麼問題越小。

無論是精益還是敏捷都在強調一點——儘早反饋，反饋對於提高敏捷開發流程效力非常重要。從日常的：

 - Code Review
 - 靜態程式碼分析
 - 自動整合測試
 - 自動驗收測試
 - 高頻率釋出

我們都在做盡可能小的反饋，這些實踐對於我們完成一個好的持續整合來說是非常重要的基礎。

參考資料：

 -《持續交付：釋出可靠軟體的系統方法》

[^CI]: [基於 Jenkins 快速搭建持續整合環境](https://www.ibm.com/developerworks/cn/java/j-lo-jenkins/)

持續交付
---

持續交付依賴於一系列的工具和實踐，下圖是一個持續交付的工作流：

![CD Workflow](assets/article/chapter6/continuous-delivery.jpg)

還有一系列與開發無關的技能：

1. 自動化
2. DevOps
3. 雲基礎設施
4. 以軟體為中心的哲學

###基礎設施

在我們使我們的項目可以持續交付軟體包的時候，我們需要

####本地開發環境

在本地編寫程式碼時，我們需要設定本地的開發環境。假設我們要開始一個 Java Web 項目，在我們的開發機器上，我們需要安裝：

 - 版本管理工具，如 git，用於管理原始碼。
 - IDE，如Intellij IDEA，用於搭建開發環境。
 - 構建工具，如 gradle，用於安裝依賴、執行測試、構建工程等等。
 - 語法檢測工具，如 checkstyle，用於檢查程式碼語法。
 - 單元測試框架，如 JUnit，用於進行單元測試。
 - 整合測試框架，如 Cucumber、Selenium，用於做行為測試。

除此，在我們的項目程式碼裡，我們還需要：

 - ``CI執行指令碼``，用於在 CI 上執行指定的測試。
 - ``上傳包指令碼``，用於上傳 build 完的軟體包。
 - ``部署指令碼``，用於在本地部署包到測試環境。
 - ``監控程式碼``，用於監測網站效能和使用者行為。

當然我們還需要輔助一些測試工具來測試網站，如效能測試、網路測試等等。

####持續整合環境

為什麼在這裡會出現一個持續整合環境？我也不知道，只是想到了這裡。由於我們需要持續整合，所以我們也需要一個執行持續整合伺服器的機器。

持續整合伺服器是由兩部分組成的：Master 和 Agent。即一個用於控制其他執行持續整合服務的機器，以及執行指令的機器。因此，我們需要在一臺機器上安裝 Master 軟體，在另外一臺機器上作為 Agent。在我們的 Agent上，我們需要安裝相對應的執行服務的軟體，如

 - 指定版本的語言環境 ，如Java、Python。
 - 構建工具。
 - 版本管理工具，及對應的金鑰。
 - 打包工具，如 RPM。
 - 虛擬桌面，即可以模擬桌面瀏覽器的軟體。

同時，我們還需要有一個地方放置我們的RPM包。

####測試環境

相比於上面兩個環境來說，測試環境就比較簡單了。我們只需要建立幾個不同的環境，即開發者的測試環境、QA 環境、模擬線上環境，在這幾個不同的環境上有不同的配置。

###持續部署

在持續交付之外的，還有持續部署——這個就更依賴於團隊的組織結構了。其與持續交付的對比如下圖所示：

![持續部署](assets/article/chapter6/continuous-delivery-continuous-deployment.jpg)

我們可以從圖中看到，兩者的最大不同之處在於：持續部署會直接將構建生成的部署到產品環境。這就意味著，我們不僅要有強大的技術實力，也要有足夠的組織支援才能做到。而這部分已經超出了軟體開發的內容了~~。

持續學習
---

如果說``持續交付則是一種對卓越的追求``,那麼``持續學習應該就是追求軟體卓越``。
如果說``持續整合是一種軟體開發實踐``,那麼對於技術人員來說——``持續寫作應該就是持續學習的實踐``

生活總會遇到壓力，來自工作上的也好，來自對於技術上的興趣也罷，我們需要持續來斷地學習。沒有一直能立於不敗的方法，在傳說中的武林上也是如此。

對於持續學習來說，通常會有以下的

 - 閱讀
 - 程式設計
 - 寫作

有意思的是持續學習有額外的好處便是

 - 持續學習可以降低危機感

###持續閱讀

看過如此多的金庸、古龍小說我們都會發現有那麼多的人都在追求武功上的卓越，有的走火入魔了，有的鋌而走險殺人放火，暫且不討論這些。我們簡單的以大部分的主角為例，大部分的主角自小就練得一手好武藝，少部分除外，而他們通過會比前輩厲害，只是因為我們看了前人的說，現在也是如此。

**20 年前要建一個淘寶怕是沒有兩三個月十幾個人是不行的，但是今天要建出原來淘寶的模樣，也許一個人單槍匹馬一兩天就能搞定了，還能上線。**

有意思的是武林小說的武林祕籍少之又少，正常情況下能學到的或許就是教科書上的種種。而現在，如果我們要學習 ``UX`` 的話，我們很容易可以從亞馬遜上拿到一個書單，又或者是某個部落格裡面列舉出來的:《使用者體驗要素》、《互動設計沉思錄》、《怦然心動——情感化互動設計指南》等等。

我們可以更加方便快捷地獲取我們所需要的知識從書上、網上等等。

``閱讀更多的書籍是持續學習的基礎。``

總會聽到有些人在工作之餘看了更多的書，在某種情況下來說是有意義的。我們需要不斷地去閱讀。

###持續程式設計

程式設計算是一個開發人員工作時一直在做的，而對於工作之後來說，到底還會有多少人繼續程式設計就是一個有意思的問題。

對於一個有興趣的程式設計師來說，工作和興趣都是分開的，可以將工作視之為無味的東西，但是休息時間呢？可以用來創造自己覺得有意義的東西，可以用來認識更多志同道合的人，對於不滿現狀的人更是如此，或許為自己創造了更多的機會。

工作之後程式設計，不應該是為了工作而程式設計，應該為了興趣而程式設計，或者其他。如果沒有時間，是不是因為加班了，對於剛開始養家餬口來說加班是沒有辦法的，但是如果不是的話，又沒時間，是不是……

###持續寫作

對於一個技術人員來說，寫作可能不是一件有意思的事，但是也不是一件很難的事，沒有必要將大量的文字用文字表示。寫給其他技術人員看的，有時候更多的是程式碼、思路、圖。寫作對於學習的意思怕是有一大把，寫作是最好的輸入，也是最好的輸出。你需要為你的這篇文章

 - 去參考更多的資料
 - 更深入的學習
 - 更多的時間付出

然而這些都是有價值的，你也許可以從中得到

 - 一份工作
 - 一些志同道合的朋友
 - 一個部落格
 - 一種習慣
 - 還有人生
 - 或許還能寫書。

對於我來說，更多的是對於``讀者``和 ``SEO`` 的興趣，SEO 是一門藝術。

遺留系統與修改程式碼
===

儘管維基百科上對遺留系統的定義是:

> 一種舊的方法、舊的技術、舊的計算機系統或應用程式。

但是實際上，當你看到某個網站宣稱用新的框架來替換舊的框架的時候，你應該知曉他們原有的系統是遺留系統。人們已經不想在上面工作了，很多程式碼也不知道是幹什麼的，也沒有人想去深究——畢竟不是自己的程式碼。判斷是否是遺留程式碼的條件很簡單，維護成本是否比開發成本高很多。

 - 幾乎無法維護
 - 程式碼遺失
 - 邏輯不清
 - 沒有文件或者不夠詳細、看不懂
 - 關鍵點遺失

在維護這一類系統的過程中，我們可能會遇到一些原因來修改程式碼。如《修改程式碼的藝術》的一書中所說，修改軟體有四大原因：

 - 增加特性
 - 修復 Bug
 - 改善設計
 - 優化

當我們修改程式碼之後，我們將繼續引進新的 Bug。


參考閱讀

 -《修改程式碼的藝術》

遺留程式碼
---

與我們生活息息相關的很多軟體裡滿是錯誤、脆弱的程式碼，並且難以擴充套件。這就是我們說的“遺留程式碼”。

相信你也經常看到某某網站的架構之路，會發現其中一個很有趣的過程就是他們會把之前的架構拋棄掉。接著，他們又做了一個這樣的系統，然後過些年這個系統又被重做了。究其原因，會發現這個架構是在幾年前設計的。在幾年前，他是非常好的架構。但是隨著時間的演變，他還是幾年前的架構。這是為什麼呢？

###遺留程式碼

什麼是遺留程式碼？

> 沒有自動化測試的程式碼就是遺留程式碼，不管它是十年前寫的，還是昨天寫的。

從一個新手程式設計師到一個老鳥，我們的程式設計水平都在不斷增加。但是我們過去寫的程式碼一直都在那裡，我們一直都沒有足夠的勇氣去動它們。因為我們知道如果一不小心改錯了什麼，就會導致一些意外的 Bug。這些 Bug 可能會對我們的程式設計生涯造成一些影響。

我們不知道這樣做的後果，是因為我們沒有對原來的程式碼進行測試。如果程式碼都是經過測試的，那麼我們在修改中出的錯，都會在測試中加以體現。長此以往，沒有人敢去修改這些程式碼。

既然它在舊的系統中工作得很好，那麼我們就沒有理由去修改它們。當有新的需求出現時，我們就可以重新設計一個新的系統。

如何修改遺留程式碼
---

> 即使是最訓練有素的開發團隊，也不能保證始終編寫出清晰高效的程式碼。

然而，如果我們不去嘗試做一些改變，這些程式碼就會遺留下去——成為遺留程式碼，再次重構掉。即使說，重構系統是不可避免的一個過程，但是在這個過程中要是能抽象中領域特定的程式碼、語言也是件不錯的事。

###修改遺留程式碼

So，如何開始修改程式碼？如《修改程式碼的藝術》一書所說，應該是下面的五個步驟：

1. 程式碼修改點
2. 找到測試點
3. 打破依賴
4. 編寫測試
5. 修改並重構

在有測試的情況下重構現有的程式碼才是安全的。而這些測試用例也是功能的體現，功能首先要得到保證了，然後才能保證一切都可以正常。不過，我更喜歡以下面三點概括他們：

 - 守: 找到測試點。守，即保證原有的功能是正確的。在這基礎上，我們需要新增測試
 - 破: 打破依賴。會導致遺留程式碼的一個原因還有，原有程式碼的耦合度比較高。因此，我們需要去打破這些耦合，重新構建依賴。
 - 離: 修改並重構。

不過，我想你只要有前面的那些步驟。你為什麼還需要看這一章的內容呢？

參考書籍：

 - **《修改程式碼的藝術》**
 - **《持續交付指南：修改程式碼的9條最佳實踐》**

網站重構
----

> 網站重構應包含結構、行為、表現三層次的分離以及優化，行內分工優化，以及以技術與資料、人文為主導的互動優化等。

從我所瞭解到的網站重構，它大概可以分為下面的幾類：

1. 速度優化
2. 功能加強
3. 模組重構

下面就我們來看這三類的網站重構

###速度優化

通常來說對於速度的優化也包含在重構中

 - 壓縮 JS、CSS、image 等前端資源
 - 程式的效能優化(如資料讀寫)
 - 採用 CDN 來加速資源載入
 - 對於 JS DOM 的優化
 - HTTP 伺服器的檔案快取

如對於壓縮前端資源這一類的重構，不僅可以從程式碼層級來解決問題，也可以藉由伺服器快取來解決問題。這時候就需要去判斷應該由哪個層級來做這樣的事情——如果一件事可以簡單地由機器來解決，但是由人來解決需要花費大量的時間，這時就應該交由機器來解決。而如果由人來解決是一個長期受益，並且成本比較低的事，那麼就應該由人來解決。如我們只需要在我們的構建指令碼中引入 minify 庫就可以解決的事，那麼應該交由人來做。

如，採用 CDN、HTTP 伺服器的檔案快取這一類應該交由機器來做。

同時像程式效能優化、JS DOM 優化都是應交由人來解決的事。特別是像程式效能優化，從長期來看可能是一件長期受益的事。當且僅當，我們遇到效能問題時，重構這部分程式碼才可能帶來優勢。如果我們的網站訪問量不是特別大，那麼優化可能就是徒勞的。但是這種優化對於個人的成長還是挺有幫助的。

###功能加強

一般來說功能加強，應該是由於需求的變動才引起對系統的重構需求：

 - 解耦複雜的模組 -> 微服務
 - 對快取進行優化
 - 針對內容建立或預留 API
 - 新增新的 API
 - 用新的語言、框架代替舊的框架(如 Scala, Node.js, React)

###模組重構

深層次的網站重構應該考慮的方面

 - 減少程式碼間的耦合
 - 讓程式碼保持彈性
 - 嚴格按規範編寫程式碼
 - 設計可擴充套件的 API
 - 代替舊有的框架、語言
 - 增強使用者體驗

回顧與架構設計
===

在剛開始接觸架構設計的時候，對於這個知識點我覺得很奇怪。因為架構設計看上去是一個很複雜的話題，然而他是屬於設計的一部分。如果你懂得什麼是美、什麼是醜，那麼我想你也是懂得設計的。而設計是一件很有意思的事——剛開始寫字時，我們被要求去臨摹別人的字型，到了一定的時候，我們就可以真正的去設計。

自我總結
---

總結在某種意義上相當於自己對自己的反饋：

![Output is Input](assets/article/chapter8/output-input.png)

當我們向自己輸入更多反饋的時候，我們就可以更好地調整我們的方向。它屬於輸出的一部分，而我們也在不斷調整我們的輸入的時候，我們也在導向更好地輸出。

###吾日三省吾身

> 為什麼你不看不到自己的方向？

Retro
---

Retro，又可以稱為回顧，它的目的是對團隊的激勵、改進。它的模式的特點就是讓我們更關注於 Less Well，即不好的地方。當我們無法變得更好的時候，它可以幫助我們反觀團隊自身，即不要讓現狀變得更差，避免讓破窗效應[^破窗]難以發生。

在敏捷團隊裡，Retro 通常會發生一個迭代的結束與下一個迭代的開始之間，這看上去就是我們的除舊迎新。相信很多人都會對自我進行總結，隨後改進。而 Retro 便是對團隊進行改進，即發生了一些什麼不好的事，而這些事可以變好，那麼我們就應該對此進行改進。

Retro 是以整個團隊為核心去考慮問題的，通常來說沒有理由以個人為物件。因為敏捷回顧有一個最高指導原則，即：

> 無論我們發現了什麼，考慮到當時的已知情況、個人的技術水平和能力、可用的資源，以及手上的狀況，我們理解並堅信：每個人對自己的工作都已全力以赴。

下面就讓我們來看看在一個團隊裡是如何 Retro 的。

###Retro 的過程

它不僅僅可以幫助我們發現團隊裡的問題，也可以集思廣益的尋找出一些合適的解決方案。Retro 的過程和我們之前說的資料分析是差不多的，如下圖所示：

![Retro 流程](assets/article/chapter8/retro-feature.jpg)

即：

1. 設定會議目標。在會議最開始的時候我們就應該對會議的內容達成一種共識，我們要回顧的主題是啥，我們要回顧哪些內容。如果是一般性的迭代 Retro，那麼我們的會議主題就很明顯了。如果是針對某一個特定項目的 Retro，那麼主題也很明顯。
2. Retro 的回顧。即回顧上一個 Retro 會議的 Action 情況，並進行一個簡單的小結。
3. 收集資料。收集資料需要依賴於我們收集資料的模式，要下面將會說到的四種基本維度，或者是雷達圖等等。不同的收集資料的形式有不同的特別，團隊裡的每個人都應該好好去參與。
4. 激發靈感。當我們尋找到團隊中一個值得去慶祝的事，或者一個出了問題的事，我們就應該對這個問題進行討論。並且對其展開了解、調查，讓大家進一步看到問題，看到問題的根源。
5. 決定做什麼。現在我們已經做了一系列的事，最重要的來了，就是決定我們去做什麼。我們應該對之前的問題做出怎樣的改進。
6. 總結和收尾。記錄會議成果，更新文件等等。

###三個維度

以我們為例，我們以下面的三個維度去進行 Retro:

1. Well.
2. Less Well.
3. Suggestion

當然最後還會有一個Action：

1. Action

該模式的特點是會讓我們更多的關注 Less Well，關注我們做的不好的那些。

![Retro](assets/article/chapter8/happy-retro.jpg)

**Well**。我們在 Well 裡記錄一些讓我們開心的事，如最近天氣好、迭代及時完成、沒有加班等等，這些事從理論上來說應該繼續保持（KEEP）下去。

**Less Well**。關注於在這個迭代的過程中，發生了一些什麼不愉快的事。一般來說，我們就會對 Less Well 加以細緻的討論，找出問題的根源，並試圖找到一個解決方案。換句話來說，就是改變（CHANGE)。

**Suggestion/Puzzle**。如果我們可以直接找到一些建議，那麼我們就可以直接提出來。並且如果我們對當前團隊裡的一些事情，有一些困惑那麼也應該及早的提出來。

**Action**。當我們對一些事情有定論的時候，我們就會提出相應的 Action。這些 Action 應該有相應的人去執行，並且由團隊來追蹤。

[^破窗]: 以一幢有少許破窗的建築為例，如果那些窗不被修理好，可能將會有破壞者破壞更多的窗戶。最終他們甚至會闖入建築內，如果發現無人居住，也許就在那裡定居或者縱火。又或想像一條人行道有些許紙屑，如果無人清理，不久後就會有更多垃圾，最終人們會視為理所當然地將垃圾順手丟棄在地上。因此破窗理論強調著力打擊輕微罪行有助減少更嚴重罪案，應該以零容忍的態度面對罪案。

架構模式
---

> 模式就是最好的架構。

####架構的產生

在剛開始接觸架構設計的時候，我買了幾本書然後就開始學習了。我發現在這些書中都出現了一些相似的東西，如基本的分層設計、Pipe and Filters 模式、MVC 模式。然後，我開始意料到這些模式本身就是最好的架構。

MVC 模式本身也是基於分層而設計的，如下圖是 Spring MVC 的請求處理過程：

![Spring MVC](assets/article/chapter8/spring-mvc.png)

而這只是框架本身的架構，這一類也是我們預先設計好的框架。

在框架之上，我們會有自己本身的業務所帶來的模式。如下圖是我在網上搜羅到的一個簡單的傳送郵件的架構：

![傳送郵件中的 Pipe and Filters 模式](assets/article/chapter8/basic-paf.png)

這樣的模式則是在業務發展的過程中演進出來的。

###預設計式架構

日常使用的框架多數是預先設計的構架，因為這些架構本身的目標是明確的。系統會圍繞一定的架構去構建，並且在這個過程中架構會幫助我們更好地理解系統。如下圖所示的是 Emacs 的架構：

![Emacs 架構](assets/article/chapter8/emacs-architecture.png)

它採用的是互動式應用程式設計師應用廣泛的模型-檢視-控制器模式。

無論是瀑布式開發——設計好系統的框架，然後對系統的每個部分進行獨立的完善和設計，最後系統再整合到一起。還是敏捷式開發——先做出 MVP，再一步步完善。它們都需要一定的預先式設計，只是傳統的開發模式讓兩者看上去是等同的。

在過去由於 IT 技術變革小，新技術產生的速率也比較低，預先設計系統的架構是一種很不錯的選擇。然而，技術的發展趨勢是越來越快，現有的設計往往在很短的一段時間裡就需要推倒重來。

###演進式架構：擁抱變化

演進式架構則是我們日常工作的業務程式碼庫演進出來的。由於業務本身在不斷髮展，我們不斷地演進系統的架構。在這樣的模式下產生的架構系統會更加穩定，也更加優美。僅僅依賴於事先的設計，而不考慮架構在後期業務中的變化是一種不可取的設計模式。

這不併意味著不採用預先式設計，而是不一味去依靠原先系統的架構。

浮現式設計
---

設計模式不是一開始就有的，好的軟體也不是一開始就設計成現在這樣的，好的設計亦是如此。

導致我們重構現有系統的原因有很多，但是多數是因為原來的程式碼變得越來越不可讀，並且重構的風險太大了。在實現業務邏輯的時候，我們快速地用程式碼實現，沒有測試，沒有好的設計。

而下圖算是最近兩年來想要的一個答案：

![浮現式設計](assets/article/chapter8/emergent-design.jpg)

浮現式設計是一種敏捷技術，強調在開發過程中不斷演進。軟體本身就不應該是一開始就設計好的，它需要經歷一個演化的過程。

###意圖導向

和 Growth 一樣，在最開始的時候，我不知道我想要的是怎樣的——我只有一個想法以及一些相對應的實踐。接著我便動手開始做了，這是我的風格。不得不說這是結果導向程式設計，也是大部分軟體開發採用的方法。

所以在一開始的時候，我們就有了下面的程式碼：

```javascript
if (rating) {
    $scope.showSkillMap = true;
    skillFlareChild[skill.text] = [rating];

    $scope.ratings = $scope.ratings + rating;
    if (rating >= 0) {
      $scope.learnedSkills.push({
        skill: skill.text,
        rating: rating
      });
    }

    if ($scope.ratings > 250) {
      $scope.isInfinite = true;
    }
  }
```

程式碼在不經意間充斥著各種 Code Smell:

1. Magic Number
2. 超長的類
3. 等等

###重構

還好我們在一開始的時候寫了一些測試，這讓我們可以有足夠的可能性來重構程式碼，而使其不至於變成遺留程式碼。這也是我們推崇的一些基本實踐：

> 紅 -> 綠 -> 重構

測試是系統不至於腐爛的一個後勤保障，除此我們還需要保持對於 Code Smell 的嗅覺。如上程式碼：

```javascript
if ($scope.ratings > 250) {
  $scope.isInfinite = true;
}
```

上面程式碼中的“250”指的到底是？這樣的數字怎麼能保證別人一看程式碼就知道250到底是什麼？

如下的程式碼就好一些：

```javascript
var MAX_SKILL_POINTS = 250;
if ($scope.ratings > MAX_SKILL_POINTS) {
  $scope.isInfinite = true;
}
```

而在最開始的時候我們想不到這樣的結果。最初我們的第一直覺都是一樣的，然而只要我們保持著對 Code Smell 的警惕，情況就會發生更多的變化。

重構是區分普通程式設計師和專業程式設計師的一個門檻，也是練習得來的一個結果。

###模式與演進

如果你還懂得一些設計模式，那麼想來，軟體開發這件事就變得非常簡單——我們只需要理解好需求即可。

從一開始就使用模式，要麼你是專家，要麼你是在自尋苦惱。模式更多的是一些實現的總結，對於多數的實現來說，它們有著諸多的相似之處，可以使用相同的模式。

而在需求變化的過程中，一個設計的模式本身也是在不斷的改變。如果我們還固執於原有的模式，那麼我們就會犯下一個又一個的錯誤。

在適當的時候改變原有的模式，進行一些演進變顯得更有意義一些。如果我們不能在適當的時候引進一些新的技術，那麼舊有的技術就會不斷累積。這些技術債就會不斷往下疊加，這個系統將會接近於崩塌。而我們在一開始所設定的一些業務邏輯，也會隨著系統而逝去，這個公司似乎也要到盡頭了。

而如果我們可以不斷地演進系統——抽象服務、拆分模組等等。業務就可以在技術不斷演進地過程中得以保留。

每個人都是架構師
---

每一個程式設計師都是架構師。平時在我們工作的時候，架構師這個 Title 都被那些非常有經歷的開發人員佔據著。然而，如果你喜歡刷刷 Github，喜歡做一些有意思的東西，那麼你也將是一個架構師。

###如何構建一個部落格系統

####如果你需要幫人搭建一個部落格你先會想到什麼？

先問一個問題，如果要讓你搭建一個部落格你會想到什麼技術解決方案？

1. 靜態部落格（類似於 GitHub Page）
2. 動態部落格（可以線上更新，如 WordPress）
3. 半動態的靜態部落格（可以動態更新，但是依賴於後臺構建系統）
4. 使用第三方部落格

這只是基本的骨架。因此如果只有這點需求，我們無法規劃出整體的方案。現在我們又多了一點需求，我們要求是獨立的部落格，這樣我們就把第4個方案去掉了。但是就現在的過程來說，我們還是有三個方案。

接著，我們就需要看看 Ta 需要怎樣的部落格，以及他有怎樣的更新頻率？以及他所能接受的價格？

先說說價格——從價格上來說，靜態部落格是最便宜的，可以使用 AWS S3 或者國內的雲端儲存等等。從費用上來說，一個月只需要幾塊錢，並且快速穩定，可以接受大量的流量訪問。而動態部落格就貴了很多倍——我們需要一直開著這個伺服器，並且如果使用者的數量比較大，我們就需要考慮使用快取。使用者數量再增加，我們就需要更多地伺服器了。而對於半動態的靜態部落格來說，需要有一個 Hook 檢測文章的修改，這樣的 Hook 可以是一個客戶端。當修改發生的時候，執行伺服器，隨後生成靜態網頁。最後，這個網頁接部署到靜態伺服器上。

從操作難度上來說，動態部落格是最簡單的，靜態部落格緊隨其後，半動態的靜態部落格是最難的。

整的價效比考慮如下：

 x  |動態部落格  | 靜態部落格 | 半動態的靜態部落格
------|--------|---------|-------
價格 | 幾十到幾百元 | 幾元 | 依賴於更新頻率 幾元~幾十元
難度 | 容易   | 稍有難度 | 難度稍大
運維 | 不容易 |容易  | 容易
資料儲存 | 資料庫 | 無 | 基於 git 的資料庫

現在，我們已經達成了一定的共識，有了幾個方案可以供使用者選擇。而這時，我們並不瞭解進一步的需求，只能等下面的結果。

客戶需要可以看到文章的修改變化，這時就去除了靜態部落格。現在還有第1和第3種方案可以選，考慮到第3種方案實現難度比較大，不易短期內實現。並且第3種方案可以依賴於第1種方案，就採取了動態部落格的方案。

但是，問題實現上才剛剛開始。

####我們使用怎樣的技術？

作為一個團隊，我們需要優先考慮這個問題。使用怎樣的技術解決方案？而這是一個更復雜的問題，這取決於我們團隊的技術組成，以及未來的團隊組成。

如果在現有的系統中，我們使用的是 Java 語言。並不意味著，每個人都喜歡使用 Java 語言。因為隨著團隊的變動，做這個技術決定的那些人有可能已經不在這個團隊裡。即使那些人還在，也並不意味著我們喜歡在未來使用這個語言。當時的技術決策都是在當時的環境下產生的，在現在看來很扯的技術決策，有可能在當時是最好的技術決策。

對於一個優秀的團隊來說，不存在一個人對所有的技術棧都擅長的情況——除非這個團隊所從事的業務範圍比較小。在一個複雜的系統裡，每個人都負責系統的相應的一部分。儘管到目前為止並沒有好的機會去構建自己的團隊，但是也希望總有一天有這樣的機會。在這樣的團隊裡，只需要有一個人負責整個系統的架構。其餘的人可以在自己擅長的層級裡構建自己的架構。因此，讓我們再回到我們的部落格中去，現在我們已經決定使用動態的部落格。然後呢？

作為一個部落格我們至少有前後臺，這樣我們可能就需要兩個開發人員。

![前後臺](assets/article/chapter8/blog-basic.png)

（PS：當然，我們也可以使用 React，但是在這裡先讓我們忽略掉這個框架，緊耦合會削弱系統的健壯性。）

接著，作為一個前端開發人員，我們還需要考慮的兩個問題是：

1. **我們的部落格系統是否是單頁面應用？**。
2. **要不要做成響應式設計**。

第二個問題不需要和後臺開發人員做溝通就可以做決定了。而第一個問題，我們則需要和後臺開發人員做決定。單頁面應用的天然優勢就是：由於系統本身是解耦的，他與後臺模板系統脫離。這樣在我們更換前端或者後臺的時候，不需要去考慮使用何種技術——因為我們使用 API 作為介面。現在，我們決定做成單頁面應用，那麼我們就需要定義一個 API。之後，我們就可以決定在前臺使用何種框架： AngularJS、Backbone、Vue.js、jQuery，接著我們的架構可以進一步完善：

![含前端的架構](assets/article/chapter8/blog-with-frontend.png)

在這時，後臺人員也可以自由地選擇自己的框架、語言。後臺開發人員只需要關注於生成一個 RESTful API 即可，而他也需要一個好的 Model 層來與資料庫交付。

![含前端後臺的架構](assets/article/chapter8/blog-with-fe-be.png)

現在，我們似乎已經完成了大部分的工作？我們還需要：

1. 部署到何處作業系統
2. 使用何處資料庫
3. 如何部署
4. 如何分析資料
5. 如何測試
6. 。。。

相信看完之前的章節，你也有了一定的經驗了，也可以成為一個架構師了。

###相關閱讀資料

 -《程式設計師必讀之軟體架構》

架構解耦
---

解耦是一件很有意思的過程，它也能反應架構的變遷。

###從 MVC 到微服務

在我初識架構是什麼的時候，我看到了 MVC 模式架構。這種模式是基於分層的結構，要理解起邏輯也很簡單。這個模式如下圖所示：

![Spring MVC](assets/article/chapter8/spring-mvc.png)

由我們的 Front controller 來處理由客戶端（瀏覽器）發過來的請求，實際上這裡的 Front controller 是 DispatcherServlet。 DispatcherServlet 負責將請求派發到特定的 handler，接著交由對應的Controller來處理這個請求。依據請求的內容，Controller 將建立相應 model。隨後這個 model 將傳到前端框架中渲染，最後再返回給瀏覽器。

但是這樣的架構充滿了太多的問題，如 view 與 controller 的緊密耦合、controller 粒度難以把控的問題等等。

####Django MTV

我使用 Django 差不多有四年了，主要是用在我的部落格上。與 MVC 模式一對比，我發現 Django 在分層上還是很有鮮明特性的：

![Django MTV架構](assets/article/chapter8/django-mtv.png)

在 Django 中沒有 Controller 的概念，Controller 做的事都交由 URL Dispatcher，而這是一個高階的 URL Dispatcher。它使用正規表示式匹配 URL，然後呼叫合適的 Python 函數。然後這個函數就交由相應的 View 層來處理，而這個 View 層則是處理業務邏輯的地方。處理完後，Model 將傳到 Template 層來處理。

對比如下圖如示：

傳統的MVC架構 | Django 架構
----------------------|-----------
Model      | Model(Data Access Logic)
View       |Template(Presentation Logic)
View       | View(Business Logic)
Controller | Django itself

從上面的對比中，我們可以發現 Django 把 View 分層了。以 Django 對於 MVC 的解釋來說，檢視用來描述要展現給使用者的資料。 而在 ROR 等其他的 MVC 框架中，控制器負責決定向使用者展現哪些資料，而檢視決定如何展現資料。

聯想起我最近在學的 Scala 中的 Play 框架，我發現了其中諸多的相似之處：

![Play 框架非同步請求](assets/article/chapter8/playarchtectureasyncrequest.png)

雖然在 Play 中，也有 Controller 的概念。但是對於 URL 的處理先交給了 Routes 來處理，隨後再交給 Controller 中的函數來處理。

不過與一般 MVC 架構的最大不同之處，怕是在於 Django 的 APP 架構。Django 中有一個名為 APP 的概念，它是實現某種功能的Web 應用程式。如果我們要設計一個部落格系統的話，那麼在這個項目中，Blogpost 是一個 APP、評論是一個 APP、使用者管理是一個 APP等等。每個 APP 之中，都會有自己的 Model、View 和 Controller。其架構如下圖所示：

![Django APP 架構](assets/article/chapter8/django_app_arch.jpg)

當我們需要建立一個新的功能的時候，我們只需要建立一個新的 APP 即可——為這個 APP 配置新的 URL、建立新的 Model 以及新的 View。如果功能上沒有與原來的程式碼重複的話，那麼這就是一個獨立的 APP，並且我們可以將這個 APP 的程式碼 Copy/Paste 到一個新的項目中，並且不需要做修改。

與一般的 MVC 架構相比，我們會發現我們細化了這些業務邏輯原來的三層結構，會隨著 APP 的數量發生變化。如果我們有三個 APP 的話，那麼我們相當於有3*三層，但是他不是等於九層。這樣做可以從程式碼上直接減少邏輯的思考，讓我們可以更加集中注意力於業務實現，同時也利於我們後期維護。

雖是如此，後來我意識到了這樣的架構並沒有太多的先進之處。而這實際上是一個美好但是不現實的東西，因為我們還是使用同一個資料庫。

####微服務與 Reactive

在微服務架構中，提倡將單一應用程式劃分成一組小的服務，這些服務之間互相協調、互相配合。每個服務執行在其獨立的程序中，服務與服務間採用輕量級的通訊機制互相溝通。每個服務都應該有自己獨立的資料庫來儲存資料。

![分散資料](assets/article/chapter8/decentralised-data.png)

Django 從某種意義上有點接近微服務的概念，只是實際上並沒有完全實現。因為它沒有實現 Play 框架的非同步請求機制。抱句話來說，應用很容易就會在呼叫 JDBC、Streaming API、HTTP 請求等一系列的請求中發生阻塞。

這些服務都是獨立的，對於服務的請求也是獨立的。使用微服務來構建的應用，不會因為一個服務的癱瘓讓整個系統癱瘓。最後，這一個個的微服務將合併成整個系統。

![Combined List](assets/article/chapter8/combinedlist.png)

我們將後臺的服務變成微服務的架構，在前臺使用 Reactive 程式設計，這樣就可以結合兩者的優勢，解耦出更好的架構模式。然而，這其中還有一個讓人不爽的問題，即資料庫。如果我們使用多個資料庫，那麼維護成本也隨著上升。而如果我們可以在後臺使用類似於微服務的 Django MTV 架構，並且它可以支援非同步請求的話，並在前臺使用 Reactive 來程式設計，是不是就會更爽一點？

###CQRS

對於複雜的系統來說，上面的做法做確實很不錯。但是對於一個簡單地系統來說，這樣做是不是玩過火了？如果我們要設計一個部落格系統的話，是不是可以考慮將 Write/Read 分離就可以了？

> 命令和查詢責任分離 Command Query Responsibility Segregation（CQRS）是一種將系統的讀寫操作分離為兩種獨立模型的架構模式。

####CQS

對於這個架構的深入思考是起源於之前在理解 DDD。據說在 DDD 領域中被廣泛使用。理解 CQRS 可以從分離 Model 和 API 集合來處理讀取和寫入請求開始，即 CQS（Command Query Separation，命令查詢分離）模式。CQS 模式最早由軟體大師Bertrand Meyer（Eiffel語言之父，物件導向開-閉原則 OCP 提出者）提出。他認為，物件的行為僅有兩種：命令和查詢。

這個類型的架構如下圖所示：

![CQS Basic](assets/article/chapter8/cqrs-2.png)

> 除了編寫優化的查詢類型，它可以讓我們輕鬆換 API 的一部分讀一些快取機制，甚至移動讀取 API 的請求到另一臺伺服器。

對於讀取和寫入相差不多的應用來說，這種架構看起來還是不錯的。而這種架構還存在一個瓶頸問題，使用同一個 RDBMS。對於寫入多、讀取少的應用來說，這種架構還是存在著不合理性。

為了解決這個問題，人們自然是使用快取來解決這個問題了。我們在我們的應用服務外有一個 HTTP 伺服器，而在 HTTP 伺服器之外有一個快取伺服器，用於快取使用者常駐的一些資源。如下圖所示：

![帶快取的 Web 架構](assets/article/chapter8/cache-website-blog.png)

而實際上這樣的伺服器可能是多餘的——我們為什麼不直接生成HTML就好了？

####編輯-釋出分離

或許你聽過 Martin Folwer 提出的編輯-釋出分享式架構：即文章在編輯時是一個形式，而發表時是另一個形式，比如用 Markdown 編輯，而用 HTML 發表。

![編輯-釋出分離](assets/article/chapter8/edit-pub.jpg)

而最典型的應用就是流行於 GitHub 的 Hexo、Jekyll 框架之類的靜態網站。如下圖所示的是 Hexo 的工作流：

![Hexo 站點工作流](assets/article/chapter8/hexo-workflow.png)

我們在本地生成我們的項目，然後可以建立一個新的部落格、開始編寫內容等等。接著，我們可以在本地執行起這個服務，除了檢視部落格的內容，還可以修改樣式等等。完成上面的工作後，我們就可以生成靜態內容，然後部署我們的應用到GitHub Page上。這一切看上去都完美，我們有兩個不同的資料來源——一個是 md 格式的文字，一個是最後生成的 HTML。它們已經實現了讀寫/分離：

![CQRS 進階](assets/article/chapter8/cqrs-separate-storage.png)

但是作為一個前端開發人員，沒有 JSON，用不了 Ajax 請求，我怎麼把部落格做成一個單頁面應用？

####編輯-釋出-開發分離

我們需要將部落格轉為 JSON，而不是一個 hexo 之類的格式。有了這些 JSON 檔案的存在，我們就可以把 Git 當成一個 NoSQL 資料庫。同時這些 JSON 檔案也可以直接被當成 API 響應來使用。

![Git As NoSQL DB](assets/article/chapter8/git-internals-commits.png)

其次，這些部落格還需要像 hexo 一樣生成 HTML。

並且，開發人員在開發的時候不會影響到編輯的使用，於是就有了下面的架構：

![基於 Git 的編輯-釋出分離](assets/article/chapter8/travis-edit-publish-code.png)

在這其中我們有兩種不同的資料形式，即儲存著 Markdown 資料的 JSON 檔案和最後生成的 HTML。

對部落格數量不是很大的網站，或者說一般的網站來說，用上面的技術都不是問題。然而有大量資料的網站怎麼辦？使用 EventBus：

![CQRS 和 EventBus](assets/article/chapter8/cqrs-arch.png)

在我之前玩的一個 Demo 中，使用 Python 中的 Scrapy 爬蟲來抓取現有的動態網站，並將其變成靜態網站部署到 AWS S3上。

但是上面僅僅只是實現了文章的顯示，我們還存在一些問題：

1. 搜尋功能
2. AutoComplete

等等的這些服務是沒有用靜態 API 來實現的。

###CQRS 結合微服務

既然可以有這麼多分法，並且我們都已經準備好分它們了。那麼分了之後，我們就可以把他們都合到一起了。

####Nginx as Dispatcher

最常見的解耦應用的方式中，就有一種是基於 Nginx 來分發 URL 請求。在這種情況下，對於 API 的使用者，或者終端使用者來說，他們都是同一個 API。只是在後臺裡，這個 API 已經是不同的幾個 API 組成，如下圖所示：

![Nginx 解耦微服務](assets/article/chapter8/nginx-microservices.png)

客戶端的請求來到 API Gateway，根據不同的請求類型，這些 URL 被分發到不同的 Service，如 Review Service、Order Service 等等。

對於我們想要設計的系統來說也是如此，我們可以通過這個 Dispatcher 來解耦我們的服務。

####CQRS 結合微服務

現在，我們想要的系統的雛形已經出現了。

從源頭上來說，我們把能快取的內容變成了靜態的 HTML，通過 CDN 來分發。並且，我們還可以將不同的服務獨立出來。

從實現上來說，我們將部落格的資料變成了兩部分： 一個以 Git + JSON 格式存在的 API，它除了可以用於生成 HTML，另外一部分作為 API 來使用。

![CQRS 結合微服務](assets/article/chapter8/dispatcher-services.png)

最後，我們可以通過上面說到的 Nginx 或者 Apache 來當這裡的 Request Dispatcher。
