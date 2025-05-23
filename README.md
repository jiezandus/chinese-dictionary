# 汉语拼音辞典

本词典主要收录了常用字基本信息，多音字，汉字基本解释，常用词汇、常用成语读音。

## 缘起

中华传统文化，源远流长，博大精深！从古至今，上下五千年，在这历史的长河中先辈们创造出了无数的历史奇迹。
在中国两千多年的漫长帝制社会里，汉字一直是我们中华民族文化传承的重要工具。
从甲骨文到秦始皇统一文字，再到近代简化字，汉字一直在经历演变过程。
汉字总数超过8万，但常用字仅2500个，次常用字1000多个，共3500个。

根据《通用规范汉字表》中收录的8105个汉字，汉字分为三级：一级字为常用字集3500个，主要满足基础教育和文化普及的基本用字需要。
二级字收录3000个，使用度仅次于一级字。一、二级字共6500个，主要满足出版印刷、辞书编纂和信息处理等方面的一般用字需要。
三级字收录 1605 个，是姓氏人名、地名、科学技术术语和中小学语文教材文言文用字中未进入一、二级字表的较通用字，主要满足信息化时代与大众生活密切相关的专门领域的用字需要。

**汉语拼音词典** 就属于一个便于用户查询汉字拼音与笔画的电子词典工具。

## 字库

字库的准确性和完整性对于 辞典 工具来说至关重要。
在校对过程中，关于数据准确性没有做严格的把控，特别是很多汉字非常罕见，其中大量古文文献资料的引用更是难以考证。
本词典收集了如下字、词库：

```text
|---- chinese-dictionary
|----|---- character
|----|----|---- char_base.json             总收录汉字超 20000 拼音与笔画
|----|----|---- char_detail.json           总收录汉字超 20000 解释
|----|----|---- polyphone.json             多音字 2495
|----|----|---- related.json               相关字 1677 近义、反义、形近字
|----|----|---- common
|----|----|----|----  char_common.json           常用字 3500 仅汉字
|----|----|----|----  char_common_base.json      常用字 3500 拼音与笔画
|----|----|----|----  char_common_detail.json    常用字 3500 解释
|----|---- idiom
|----|----|---- idiom.json                 总收录成语 近5万 条
|----|---- word
|----|----|---- word.json                  总收录词语 超过32万 条（包含成语）
```

### 汉字

#### 为何数据是 JSON 格式？

JSON 格式可以方便快捷地转为各种编程语言内部可使用的结构。

此外某些工具支持将 JSON 文件导入后直接显示出来。

#### char_base.json 基础汉字

```json
[
  {"index": 52, "char": "反", "strokes": 4, "pinyin": ["fǎn"], "radicals": "又", "frequency": 0, "structure": "R2"}, 
  {"index": 18, "char": "干", "strokes": 3, "pinyin": ["gān", "gàn"], "radicals": "干", "frequency": 0, "structure": "D0", "traditional": "乾幹", "variant": "乹亁榦"},
  {"index": 372, "char": "面", "traditional": "麵", "strokes": 9, "pinyin": ["miàn"], "radicals": "面", "frequency": 0, "structure": "D0", "variant": "靣"},
  {"index": 7467, "char": "砭", "strokes": 9, "pinyin": ["biān"], "radicals": "石", "frequency": 3}
]
```

- `index` 表示从 1 开始的自然增长序列，唯一不重复，前8000按照《通用规范汉字表》给的顺序。
- `char` 表示一个汉字，唯一不重复。
- `strokes` 汉字的笔画数。
- `pinyin` 汉字的读音列表，数组表示，多音字会有多个读音。
- `radicals` 汉字的读音偏旁部首。
- `frequency` 表示使用频率，0 为最常用，1 为较常用，2 为次常用，3 为二级字，4 为三级字， 5 为不在《通用规范汉字》的生僻字。
- `structure` 汉字结构，结构表示的含义见下表。
- `traditional` 表示繁体字写法，可能会有多个。
- `variant` 表示异体字，可能会有多个。

> 常用字（3500） = 最常用字 0（500）+ 较常用字 1（2000）+ 次常用字 2（1000） 

> 通用规范汉字（8105）= 一级字 0/1/2（3500）+ 3 二级字（3000）+ 4 三级字（1605） 

##### 汉字结构

《汉字结构表》统计了汉字的八种结构类型：

|结 构 方 式					|例 字|间 架 比 例	| 代码 |
|		---		| -- | --| -- 					|
|独 体 结 构		|米、不			|　方正			|D0
品 字 形 结 构	|晶、众			|各部分相同		|A0
上 下 结 构		|			| 					|B0
| - |录、华			|　上下相等					|B1
| - |它、花				|上小下大				|B2
| - |基、想				|上大下小				|B3
上 中 下 结 构		|			| 				|E0
| - |意、翼		|上中下相等		 				|E1
| - | 量、裹				|上中下不等				|E2
左 右 结 构		|			| 				    |H0
| - |羽、联			|左右相等 					|H1
| - |伟、搞				|左窄右宽				|H2
| - |刚、郭				|左宽右窄				|H3
左 中 右 结 构		|			| 				|M0
| - |街、掰				|左中右相等				|M1
| - |辩、傲				|左中右不等				|M2
全 包 围 结 构		|圆、国		|全包围			|Q0
半 包 围 结 构		|			| 				|R0
| - |匠、区		        |左包右			 		|R1
| - |历、尾				|左上包右下				|R2
| - |勾、句				|右上包左下				|R3
| - |遍、廷				|左下包右上				|R4
| - |冈、闲				|上包下					|R5
| - |函、凶				|下包上					|R6

一般认为上面的分类可以覆盖所有的汉字，但是，还有一些分法更细一些：

在独体结构中分出了镶嵌结构，在上下结构中分出了田字结构：

|结 构 方 式					|例 字|间 架 比 例	| 代码 |
|		---		| -- | --| -- 					|
|独 体 结 构		|			|　			        |D0
|镶嵌结构		|爽			|　方正			    |D1
上 下 结 构		|			| 					|B0
| 田字结构 |叕、茻			|　四部分相同			|B4

#### char_detail.json 汉字解释

```json
[
   {
       "char": "车",
       "pronunciations": [
           {
               "pinyin": "chē",
               "explanations": [
                   {
                       "content": "(象形。甲骨文有多种写法。象车形。本义:车子,陆地上有轮子的运输工具)。"
                   },
                   {
                       "content": "同本义。",
                       "detail": [
                           {
                               "text": "車,舆论之总名。夏后时奚仲所造。象形。",
                               "book": "《说文》。按,横视之肖,或云车少昊时驾牛,奚仲始驾马。"
                           },
                           {
                               "text": "为车。大车、柏车、羊车,皆两辕,驾牛;田车、兵车、乘车,皆一辀,驾马。大车,平地任载车,柏车、山车,羊车、善车也;田车、兵车,乘车,通谓之小车。",
                               "book": "《考工记·舆人》"
                           },
                           {
                               "text": "车从马。",
                               "book": "《左传·闵公元年》"
                           }
                       ],
                       "words": [
                           {
                               "word": "开车;安步当车;杯水车薪;闭门造车;螳臂当车;车两 ",
                               "text": "古谓车一乘为一两"
                           },
                           {
                               "word": "车盖",
                               "text": "古代车上的伞形车篷。亦指具有此种车篷的车辆"
                           }
                       ]
                   },
                   {
                       "content": "特指战车,兵车。",
                       "detail": [
                           {
                               "text": "比至陈,车六七百乘,骑千余,卒数万人。",
                               "book": "《史记·陈涉世家》"
                           },
                           {
                               "text": "车辚辚,马萧萧,行人弓箭各在腰。",
                               "book": "唐·杜甫《兵车行》"
                           }
                       ]
                   },
                   {
                       "content": "乘车。",
                       "detail": [
                           {
                               "text": "济济群英,车的车,步的步,陆续来了。",
                               "book": "清·心青《女界文明灯弹词》"
                           }
                       ]
                   },
                   {
                       "content": "姓。"
                   }
               ]
           },
           {
               "pinyin": "jū",
               "explanations": [
                   {
                       "content": "国际象棋中的一种棋子,它可以顺着平行于棋盘边的路随便走多少方格,假如没有其它棋子阻挡的话。"
                   }
               ]
           }
       ]
   },
   {
       "char": "這",
       "pronunciations": [
           {
               "pinyin": "zhè",
               "explanations": [
                   {
                       "content": "代词。指近处的人、事、物等。",
                       "simplified": "这"
                   }
               ]
           }
       ]
  }
]
```

其中包含 2 个部分：

1. `char` 表示当前汉字
2. `pronunciations` 表示汉字在各个读音下的不同含义
    - `pinyin` 汉字拼音
    - `explanations` 汉字对应读音的解释
        - `content` 汉字具体解释
        - `speech` 汉字属于名词、动词等十二种词性
        - `example` 对应上述解释的例句
        - `detail` 对 content 的例证
        - `word` 汉字该解释下的词组
        - `modern` 说明当前汉字在古代使用，同现在的某个汉字
        - `same` 汉字与某个字含义相同，可以混用
        - `simplified` 表示该汉字是某个汉字的繁体字，含义可以参考简体字
        - `variant` 表示该汉字是某个汉字的异体字，含义可参考源字
        - `refer` 为一个词组，表示汉字含义需要参考某个词组。
        - `typo` 当前汉字为某个汉字的讹字（错误形式）。
        - `unknown` 义未详，部分汉字查询不到具体含义，暂时标注为 true。

基本的数据格式如下：

```json
[
  {
    "char": "一",
    "pronunciations": [
      {
        "pinyin": "yī",
        "explanations": [
          {
             "content": "最小的正整数。", 
             "speech": "数",
             "example": "这里有一个苹果。", 
             "detail": [{"text": "一也者,万物之本也。", "book": "《淮南子·诠言》"}], 
             "words": [{"word": "一丝", "text": "一根蚕丝", "example": "要时刻谨记一丝一缕当思来之不易。"}], 
             "same": "壹", 
             "modern": "丨", 
             "refer": "一样", 
             "simplified": "二", 
             "typo": "弌"
          }
        ]
      }
    ]
  }
]
```
**数据规范**

- 整体为列表（数组）
- 每个列表项为一个汉字，不重复
- 每个汉字一定会出现 2 个属性：汉字char、相关解释pronunciations
- 汉字 char 不可省略，**不能为空**，且长度为 1
- 读音 pronunciations 为列表，如果是多音字会有多个，**不能为空**，其中每一项包含 pinyin 和 explanations 。
- pinyin 在同一个汉字中数据**不会重复**，且个数等于该汉字的读音个数。
- explanations 为列表，可能有多个，**不可为空**。其中每一项包含 content 和 detail ，除非为特殊汉字，否则一定存在 content 字段。
- content 中是字符串，一般表示独立的含义，其个数基本代表该汉字有多少种解释。
- speech 词性分类，选自下面的十二种词性，省略后缀'词'。
- detail 中是字符串列表，一般表示一组有关联的汉字解释，是对 content 的进一步例证。其中 text 是文献内容，book 是文献例证出处。
- words 是一个列表，是当前解释下的词组。其中 word 是词组，text 是词组的简单解释，example 是包含词组的例句。
- same 为单个汉字，表示当前汉字与 same 含义相同，表示 同‘X’，通‘X’，见‘X’。
- modern 为单个汉字，表示当前汉字如今的写法，存在该字段一般说明该汉字已经不使用了。
- refer 为一个词组，表示汉字含义需要参考某个词组。某些汉字单独出现时没有含义，必须和另外的汉字组词。
- simplified 为单个汉字，表示当前汉字是某个汉字的繁体字，含义可以参考简体字。
- typo 为单个汉字，表示当前汉字的讹字。

> 目前结果集文件中数据不满足上述规范，是因为解析过程中，某些数据有缺失或者格式错乱，在持续改进后，最终会完全满足上述要求。

**词性分类**

> 实词:1.名词;2.动词;3.形容词;4.数词;5.量词;6.代词。
> 虚词:1.副词;2.介词;3.连词;4.助词;5.叹词;6.拟声词。

#### polyphone.json 多音字

polyphone.json 文件中的多音字包含常用字里多音字的 600 余个和其它非常用字的 1900 余个，共 2495 条数据。

```json
[
  {"index": 1, "char": "了", "pinyin": ["liǎo", "le"], "frequency": 0, "strokes": 2},
  {"index": 506, "char": "咖", "pinyin": ["kā", "gā"], "frequency": 2, "strokes": 8}
]
```

其中：

- `index` 表示汉字索引值，从 1 开始
- `char` 表示该汉字
- `pinyin` 为汉字读音的数组
- `frequency` 表示使用频率，0 为最常用，1 为较常用，2 为次常用，3 为不常用
- `strokes` 表示汉字笔画数

#### related.json 相关字

```json
[
   {"index": 2946, "char": "矮", "synonyms": ["低", "矬"], "antonyms": ["高"], "likeness": ["婑"]}
]
```
其中：

- `char` 表示该汉字
- `synonyms` 表示同义字
- `antonyms` 表示反义字
- `likeness` 表示形近字

#### char_common.json 常用字

> 考虑到某些场景下，只需要关注 3500 常用字，因此特意建了 common 文件，在其中仅包含常用字 3500 的相关数据。

```json
[
  {"index": 4, "char": "十", "frequency": 0},
  {"index": 278, "char": "乐", "frequency": 1},
  {"index": 3405, "char": "瞪", "frequency": 2}
]
```

- `id` 表示从 1 开始的自然增长序列，默认按照汉字笔画数排序。
- `char` 表示一个汉字。
- `frequency` 表示使用频率，0 为最常用，1 为较常用，2 为次常用。

#### char_common_base.json 常用字

文件中数据与 char_base 结构完全一致。

```json
[
  {"index": 1, "char": "一", "strokes": 1, "pinyin": ["yī"], "radicals": "一", "frequency": 0},
  {"index": 16, "char": "大", "strokes": 3, "pinyin": ["dà", "dài", "tài"], "radicals": "大", "frequency": 0}
]
```

#### char_common_detail.json 常用字

文件中数据与 char_detail 结构完全一致。

### 词语

#### idiom.json 成语

```json
[
   {
      "word": "一帆风顺",
      "abbr": "yffs",
      "pinyin": "yī fán fēng shùn",
      "source": {"text": "定知一日帆，使得千里风。", "book": "唐·孟郊《送崔爽之湖南》"},
      "quote": {"text": "栉霜沐露多劳顿，喜借得～。", "book": "清·李渔《怜香伴·蹴居》"},
      "explanation": "船上的帆挂起来顺着风行驶。比喻事情非常顺利，没有任何阻碍。",
      "story": ["从前有个....", "后来在田野中..."],
      "example": "①朋友，在分别之际，我祝你一帆风顺，事业有成。②小明一家要到海南旅游，祝他们一帆风顺，旅途平安。",
      "similar": ["万事亨通", "无往不利"],
      "opposite": ["寸步难行", "一波三折"],
      "usage": "常用来祝愿他人旅途顺利。作祝词时，前面常有“祝你”“祝你们”“祝大家”等词语。多用于褒义。",
      "notice": "“一帆风顺”和“无往不利”都含有非常顺利的意思。区别在于：①“一帆风顺”指做事毫无挫折，着眼于顺利的程度；“无往不利”指事事顺利，着眼于顺利的范围。②“一帆风顺”用作祝词；“无往不利”无此用法。",
      "spelling": {"right": "锱铢必较", "wrong": "锱珠必较", "text": "锱、铢：都是古代很小的重量单位。"}
   }
]
```

- 整体为列表（数组），每个列表项为一个词语，不重复

其中：

- `word` 表示该成语，**唯一且不为空**，长度大于等于 3
- `pinyin` 为成语读音，**不为空**
- `abbr` 拼音的简写，一般在搜索时使用到，**不为空**
- `explanation` 表示该成语解释。**不为空**
- `source` 表示该成语出处。不必须
- `quote` 表示哪些出名的著作中使用到了该成语。不必须
- `story` 表示该成语故事，格式为数组，因为一般内容较长，便于分段。不必须
- `similar` 表示该成语近义词。不必须
- `opposite` 表示该成语反义词。不必须
- `example` 表示该成语的例句。不必须
- `usage` 表示该成语的用法。不必须
- `structure` 词语结构，结构表示的含义见下表。不必须，仅特殊结构包含该字段
- `notice` 表示该成语使用时应该注意的地方。不必须
- `spelling` 容易出现错误写法的成语，会在 `right`中体现正确的，`wrong`中体现错误的，`text`是补充说明。不必须

##### 词语结构

|结 构 方 式					|例 字|	 代码 |
|		---		| -- | --|
|ABB		|懒洋洋					|ABB
|AAB		|偷偷地					|AAB
|ABAB		|乐呵乐呵				|ABAB
|AABB		|堂堂正正				|AABB
|ABAC		|一心一意				|ABAC
|AABC		|振振有词				|AABC
|ABCC		|千里迢迢				|ABCC

#### word.json 词语

```json
[
    {
      "word": "动脉", 
      "pinyin": "dòng mài", 
      "abbr": "dm", 
      "explanation": "把心脏中压出来的血液输送到全身各部分的血管； 比喻重要的交通干线。"
    }
]
```

- `word` 表示该词语，**唯一且不为空**，长度大于等于 2
- `pinyin` 为词语读音，**不为空**
- `abbr` 拼音的简写，**不为空**
- `explanation` 表示该词语解释，超过 99% 的词语含有释义

词语和成语的所有属性完全相同，且词语库包含成语库。

> 所有的成语数据 idiom.json 都包含在 word.json 文件中。

## 线上应用

目前 **汉语拼音词典** 已经在多端上线小程序。

微信小程序：汉语拼音词典

<img alt="微信小程序" src="https://cdn.mapull.com/char/qrcode/character_wechat.jpg"></img>

图片显示不出来的话，可以[点击这里](https://cdn.mapull.com/char/qrcode/character_wechat.jpg)

百度小程序：码谱汉语拼音词典

<img alt="百度小程序" src="https://cdn.mapull.com/char/qrcode/baidu_character.png"></img>

抖音、字节跳动小程序：汉语拼音辞典

<img alt="字节跳动小程序" src="https://cdn.mapull.com/char/qrcode/toutiao_character.png"></img>

## 参考资料

字库的基础数据大都来自 Github 及其他开源组织，本项目字库参考但不限于如下资源：

- [Github] [funNLP](https://github.com/fighting41love/funNLP)
- [Github] [pinyin-data](https://github.com/mozillazg/pinyin-data)
- [Github] [chinese-xinhua](https://github.com/pwxcoo/chinese-xinhua)
- [Github] [phrase-pinyin-data](https://github.com/mozillazg/phrase-pinyin-data)
- [开源] [CC-CEDICT](https://www.mdbg.net/chinese/dictionary?page=cc-cedict)
- [官方] [中国语言文字网](http://www.china-language.edu.cn/)
- [商用] [汉典](https://www.zdic.net/)
- [商用] [字海，叶典网](http://zisea.com/)

> 参考商用数据是为了人工校对数据的准确性，并没有对其数据进行爬取。

## 版权

该项目是为了支持 **汉语拼音辞典** 的线上数据。在使用小程序的过程中，发现有些汉字读音有误，如果人工校对将是一个庞大的工程，于是对现有的开源语料库进行了多维分析。如果不确定的读音，还参考了部分商业应用如汉典网的数据进行人工比对。

本项目汇总得到的数据结果采用 MIT License 开源。

因为某些收集来的数据，无法确认数据的最初来源，使用它们可能存在风险。