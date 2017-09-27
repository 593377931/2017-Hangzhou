# The Absolute Minimum Every Software Developer Absolutely, Positively Must Know About Unicode and Character Sets (No Excuses!)

对每个软件开发者的基本要求——绝对要了解Unicode和字符集（没有借口！）

by JOEL SPOLSKY

---

* Ever wonder about that mysterious Content-Type tag? You know, the one you’re supposed to put in HTML and you never quite know what it should be?
  * 曾经想搞清楚那个陌生的Content-Type标签？你知道的，就是那个你应当放进HTML中的，你从来不想知道它是什么吗？
* Did you ever get an email from your friends in Bulgaria with the subject line “???? ?????? ??? ????”?
  * 你曾经有没有收到一封来自保加利亚朋友的邮件，邮件的主题是“？？？？？？”？

* I’ve been dismayed to discover just how many software developers aren’t really completely up to speed on the mysterious world of character sets, encodings, Unicode, all that stuff. A couple of years ago, a beta tester for FogBUGZ was wondering whether it could handle incoming email in Japanese. Japanese? They have email in Japanese? I had no idea. When I looked closely at the commercial ActiveX control we were using to parse MIME email messages, we discovered it was doing exactly the wrong thing with character sets, so we actually had to write heroic code to undo the wrong conversion it had done and redo it correctly. When I looked into another commercial library, it, too, had a completely broken character code implementation. I corresponded with the developer of that package and he sort of thought they “couldn’t do anything about it.” Like many programmers, he just wished it would all blow over somehow.
  * 我曾对这个问题感到很诧异，很多软件开发者并没有真正的了解最新的关于字符集，编码和Unicode等等问题的情况。几年以前，一个关于FogBUGZ的β测试，考虑到是否能够处理收到的用日语书写的邮件。日语？他们有收到日语邮件？我不知道。当我仔细查看我们用来分析MIME邮件的商业ActiveX控件时，我们发现它在处理字符集时完全是错误的，我们事实上必须写一大堆代码去撤销这个错误的解析，并重新正确的解析它。当我在查看另一个商业库时，存在同样的问题，一个完全残破的字符代码处理。我联系了那个软件包开发者，他整理了一下思路说到，他对此无能为力。和很多程序员一样，他只想让问题以某种方式平息下来。
* But it won’t. When I discovered that the popular web development tool PHP has almost complete ignorance of character encoding issues, blithely using 8 bits for characters, making it darn near impossible to develop good international web applications, I thought, enough is enough.
  * 但是，那是不可能的。当我发现流行的WEB开发工具PHP几乎对字符编码的问题完全不了解，简单粗暴的对字符使用8位的处理方式，让开发出质量上乘的WEB程序变得极其困难，我想说，你们真是够了。。。
* So I have an announcement to make: if you are a programmer working in 2003 and you don’t know the basics of characters, character sets, encodings, and Unicode, and I catch you, I’m going to punish you by making you peel onions for 6 months in a submarine. I swear I will.

  * 所以我有句MMP要讲：如果你是一位工作在2003年的程序员，却对基本的字符、字符集、编码和万国码知识不了解的话，那么我抓到你了，我要狠狠地惩罚你，让你在潜艇里剥六个月洋葱。我说到做到！

* And one more thing:

* **IT’S NOT THAT HARD.**

* In this article I’ll fill you in on exactly what every working programmer should know. All that stuff about “plain text = ascii = characters are 8 bits” is not only wrong, it’s hopelessly wrong, and if you’re still programming that way, you’re not much better than a medical doctor who doesn’t believe in germs. Please do not write another line of code until you finish reading this article.
  * 在这篇文章中我将明确的告诉每个正在工作的程序员应该知道的事情。所有那些关于“纯文本 = ascii = 8位字符”的言论不仅是错的，而且是糟糕透顶的错误，如果你依旧以这种方式写程序，那么你比一个不相信细菌学说的内科医生强不到哪里去。在你完成本文阅读之前，请一行代码也不要写。
* Before I get started, I should warn you that if you are one of those rare people who knows about internationalization, you are going to find my entire discussion a little bit oversimplified. I’m really just trying to set a minimum bar here so that everyone can understand what’s going on and can write code that has a hope of working with text in any language other than the subset of English that doesn’t include words with accents. And I should warn you that character handling is only a tiny portion of what it takes to create software that works internationally, but I can only write about one thing at a time so today it’s character sets.
  * 在开始之前，我需要说明的是，如果你是那些极其稀少的理解国际化的人，你将发现我整个讨论有些过于简单了。我仅仅只是想在这里设定一个底线，这样每个人都知道是怎么回事，并且希望写出能与任何语言协同工作的代码，那些带重音符号的英语的子集除外。并且我要提醒你的是，在那些国际性的软件开发中，字符处理仅仅是很小的一部分，但是我一次只能写一件事情，那么今天就是字符集。

## A Historical Perspective   一些传统观点
* The easiest way to understand this stuff is to go chronologically.
  * 理解这些问题最简单的方式就是顺着时间线。
* You probably think I’m going to talk about very old character sets like EBCDIC here. Well, I won’t. EBCDIC is not relevant to your life. We don’t have to go that far back in time.
  * 你可能想着我将要讨论非常古老的字符集，例如EBCDIC。然而，不会。EBCDIC对你的生活没有什么意义。我们并不需要在时间上走的那么远。
* Back in the semi-olden days, when Unix was being invented and K&R were writing The C Programming Language, everything was very simple. EBCDIC was on its way out. The only characters that mattered were good old unaccented English letters, and we had a code for them called ASCII which was able to represent every character using a number between 32 and 127. Space was 32, the letter “A” was 65, etc. This could conveniently be stored in 7 bits. Most computers in those days were using 8-bit bytes, so not only could you store every possible ASCII character, but you had a whole bit to spare, which, if you were wicked, you could use for your own devious purposes: the dim bulbs at WordStar actually turned on the high bit to indicate the last letter in a word, condemning WordStar to English text only. Codes below 32 were called unprintable and were used for cussing. Just kidding. They were used for control characters, like 7 which made your computer beep and 12 which caused the current page of paper to go flying out of the printer and a new one to be fed in.
  * 半古老时期，彼时Unix系统正在被发明，Brian Kernighan 和 Dennis Ritchie正在编写《C程序设计语言》，一切都非常简单。EBCDIC正走在自己的下坡路。要紧的字符仅仅是标准的老的非重读的英文字母，并且我们有一个叫做 ASCII 的代码，它能用32到127之间的数字代表每一个字符。32代表空格，65代表字母“A”，等等。这种编码方式可以被很方便的使用7位来存储。那是大多数电脑都使用8位，所以你不仅能存储每个ASCII字符，并且还有一整位被闲置，如果你是个捣蛋鬼，你可以将它用在你自己不光明的目的上：WordStar 中昏暗的灯泡，实际上开启了最高位来标明单词的最后一个字母，仅可用在WordStar的英语当中。32以下代表的字符被称作不可打印的，是用来骂人的。开玩笑啦，他们被用做控制字符，例如7使你的电脑发出哔哔声，12将会让一张新的纸张替换掉目前打字机上的纸张。
* And all was good, assuming you were an English speaker.
  * 假如你说英语，一切都没有问题。
* Because bytes have room for up to eight bits, lots of people got to thinking, “gosh, we can use the codes 128-255 for our own purposes.” The trouble was, lots of people had this idea at the same time, and they had their own ideas of what should go where in the space from 128 to 255. The IBM-PC had something that came to be known as the OEM character set which provided some accented characters for European languages and a bunch of line drawing characters… horizontal bars, vertical bars, horizontal bars with little dingle-dangles dangling off the right side, etc., and you could use these line drawing characters to make spiffy boxes and lines on the screen, which you can still see running on the 8088 computer at your dry cleaners’. In fact  as soon as people started buying PCs outside of America all kinds of different OEM character sets were dreamed up, which all used the top 128 characters for their own purposes. For example on some PCs the character code 130 would display as é, but on computers sold in Israel it was the Hebrew letter Gimel (ג), so when Americans would send their résumés to Israel they would arrive as rגsumגs. In many cases, such as Russian, there were lots of different ideas of what to do with the upper-128 characters, so you couldn’t even reliably interchange Russian documents.
  * 由于一个字节有8位空间，很多人想到，“天啦噜，我们可以将128-255位作为我们自己的用途”。问题是，很多人在同一时间有了这个想法，他们在128-255这段空间上应该放什么东西都各自有各自的想法。IBM-PC有一堆很出名的被称作OEM字符集的东西，它为欧洲语言提供了一些带重音符的字符和一大堆划线用字符，垂直线，水平线，右边悬挂着一堆小点的垂直线，等等。你可以使用这些划线字符绘制出一些漂亮的盒子，在屏幕上绘制出一些线条，这些你仍旧能在运行8088电脑的干洗机上看见。事实上，随着人们开始在美国以外的各个地方购买PC机，各种各样不同的OEM字符集被幻想出来，他们都将高128为用作自己的用途。例如，在一些PC上，130号字符代码会显示é，但是在以色列出售的电脑，显示的却是希伯来语字母ג，所以，当美国人发送他们的“résumés”给以色列人，以色列人将会收到“rגsumגs”。在很多情况下，例如俄语，他们对高128位如何使用有很多不同的想法，你甚至不能可靠的交换俄语文档。
* Eventually this OEM free-for-all got codified in the ANSI standard. In the ANSI standard, everybody agreed on what to do below 128, which was pretty much the same as ASCII, but there were lots of different ways to handle the characters from 128 and on up, depending on where you lived. These different systems were called code pages. So for example in Israel DOS used a code page called 862, while Greek users used 737. They were the same below 128 but different from 128 up, where all the funny letters resided. The national versions of MS-DOS had dozens of these code pages, handling everything from English to Icelandic and they even had a few “multilingual” code pages that could do Esperanto and Galician on the same computer! Wow! But getting, say, Hebrew and Greek on the same computer was a complete impossibility unless you wrote your own custom program that displayed everything using bitmapped graphics, because Hebrew and Greek required different code pages with different interpretations of the high numbers.
  * 最终，这个对所有人开放的OEM在ANSI标准中被确定。在ANSI标准中，每个人对低128位用来做什么持相同意见，基本和ASCII保持一致，不过对于128位智商的字符如何处理就有了很多不同，取决于你所在的地区。这个不同的系统被称为代码页。如在以色列的DOS系统中使用862号代码页，希腊用户使用737号。这些不同的代码页在128位以下都是相同的，从128位开始都是不同的，存放着那些滑稽的字符。MS-DOS的国际化版本有许多这种代码页，将所有字符由英语转为冰岛语，他们甚至还有一些 “多语言” 代码页，可以在同一台电脑上处理世界语和加利西亚语！哇！但是进一步来说希伯来语和希腊语是绝不可能同时出现在一台电脑上，除非你写一个自己定制的程序，用位元图像显示一切，因为希伯来语和希腊语在高为数字的理解上需要不同的代码页。
* Meanwhile, in Asia, even more crazy things were going on to take into account the fact that Asian alphabets have thousands of letters, which were never going to fit into 8 bits. This was usually solved by the messy system called DBCS, the “double byte character set” in which some letters were stored in one byte and others took two. It was easy to move forward in a string, but dang near impossible to move backwards. Programmers were encouraged not to use s++ and s– to move backwards and forwards, but instead to call functions such as Windows’ AnsiNext and AnsiPrev which knew how to deal with the whole mess.
  * 与此同时，在亚洲，更为疯狂的问题是，在亚洲有成千上万的文字，他们根本不可能被编码进8位中。通常由一个叫做DBCS的凌乱系统来解，这个双位元字符集中，一些字符是以一字节存储的，一些是以两个字节存储的。在一串字符中向后移动很容易，向前移动几乎是不可能的。程序员被建议不要使用S++和S-来向后和向前移动，替代他们使用叫做Window'Ansinext 和 Windows'AnsiPrev的函数来处理整个混乱的情况。
* But still, most people just pretended that a byte was a character and a character was 8 bits and as long as you never moved a string from one computer to another, or spoke more than one language, it would sort of always work. But of course, as soon as the Internet happened, it became quite commonplace to move strings from one computer to another, and the whole mess came tumbling down. Luckily, Unicode had been invented.
  * 但是问题依旧，很多人自认为一字节就是一个字符，一个字符是8位，只要你从不将一段字符从一台电脑传输至另一台电脑，或者只说一种语言，这样可以说是一直正常工作的。然而，随着更多的互联网行为，将一段字符从一台电脑传说至另一台电脑将变得非常普通，整个混乱的系统轰然倒塌。幸运的是，这时Unicode被发明了。

## Unicode 万国码

* Unicode was a brave effort to create a single character set that included every reasonable writing system on the planet and some make-believe ones like Klingon, too. Some people are under the misconception that Unicode is simply a 16-bit code where each character takes 16 bits and therefore there are 65,536 possible characters. This is not, actually, correct. It is the single most common myth about Unicode, so if you thought that, don’t feel bad.
  * 万国码在建立一个单一的字符集上是一个勇敢的尝试，其包含每个在地球上合乎情理的书写系统，甚至一些虚拟的语言如克林贡语。一些人错误的认为Unicode是一个简单的16位编码，每个字符占16位空间，因此包含有65536个字符。事实上，不是这样的。这仅仅是关于Unicode各种荒诞说法中的一个，因此如果你也这样想，别难受。
* In fact, Unicode has a different way of thinking about characters, and you have to understand the Unicode way of thinking of things or nothing will make sense.
  * 事实上，Unicode处理字符上有着不同的构思，你需要理解Unicode的处理方式，否则任何都讲解释不通。
* Until now, we’ve assumed that a letter maps to some bits which you can store on disk or in memory:
  * 现在，我们将字符表假设成一些你可以存储在硬盘和内存中的位元。
* A -> 0100 0001
* In Unicode, a letter maps to something called a code point which is still just a theoretical concept. How that code point is represented in memory or on disk is a whole nuther story.
  * 在Unicode中，一个字母表被转换成一个叫代码特征，其仍旧是一个理论观点。代码特征在内存和硬盘中怎样表示，仍旧是一个问题。
* In Unicode, the letter A is a platonic ideal. It’s just floating in heaven:
  * Unicode中，字母A是柏拉图式的理想，天堂中的想法。