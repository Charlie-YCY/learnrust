## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/Charlie-YCY/learnrust/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown
1.	Rust 程序设计语⾔
2.	title-page.md
3.	commit a2bd349f8654f5c45ad1f07394225f946954b8ef
4.	Steve Klabnik 和 Carol N  ichols，以及来⾃ Rust 社区的贡献（Rust
5.	中⽂社区翻译）
6.	本书假设你使⽤ Rust 1.41.0 或更新的版本，且在所有的项⽬中的
7.	Cargo.toml⽂件中通过 edition="2018"采⽤ Rust 2018 Edition 规
8.	范。请查看第⼀章的 “安装” 部分了解如何安装和升级 Rust，并查看新的
9.	附录 E了解版本相关的信息。
10.	Rust 程序设计语⾔的 2018 Edition 包含许多的改进使得 Rust 更为⼯程
11.	化并更为容易学习。本书的此次迭代包括了很多反映这些改进的修改：
12.	第七章 “使⽤包、Crate 和模块管理不断增⻓的项⽬” 基本上被重写
13.	了。模块系统和路径（path）的⼯作⽅式变得更为⼀致。
14.	第十章新增了名为 “trait 作为参数” 和 “返回实现了 trait 的类型” 部
15.	分来解释新的 impl Trait语法。
16.	第十⼀章新增了⼀个名为 “在测试中使⽤ Result<T, E> ” 的部分来
17.	展⽰如何使⽤ ?运算符来编写测试
18.	第十九章的 “⾼级⽣命周期” 部分被移除了，因为编译器的改进使得
19.	其内容变得更为少见。
20.	之前的附录 D “宏” 得到了补充，包括了过程宏并移动到了第十九章
21.	的 “宏” 部分。
22.	附录 A “关键字” 也介绍了新的原始标识符（raw identiﬁers）功
23.	能，这使得采⽤ 2015 Edition 编写的 Rust 代码可以与 2018
24.	Edition 互通。
25.	现在的附录 D 名为 “实⽤开发⼯具”，它介绍了最近发布的可以帮助
26.	你编写 Rust 代码的⼯具。
27.	我们还修复了全书中许多错误和不准确的描述。感谢报告了这些问
28.	题的读者们！
29.	注意任何 “Rust 程序设计语⾔ ” 早期迭代中的代码在项⽬的 Cargo.toml中
30.	不包含 edition="2018"时仍可以继续编译，哪怕你更新了 Rust 编译器
31.	的版本。Rust 的后向兼容性保证了这⼀切可以正常运⾏！
32.	本书的 HTML 版本可以在 https://doc.rust-lang.org/stable/book/（简
33.	体中⽂译本）在线阅读，离线版则包含在通过 rustup安装的 Rust 中；
34.	运⾏ rustup docs --book可以打开。
35.	本书的纸质版和电⼦书由 No Starch Press发⾏。
36.	前⾔
37.	foreword.md
38.	commit 1fedfc4b96c2017f64ecfcf41a0a07e2e815f24f
39.	虽然不是那么明显，但 Rust 程序设计语⾔的本质在于赋能
40.	（empowerment）：⽆论你现在编写的是何种代码，Rust 能让你在更为
41.	⼴泛的编程领域⾛得更远，写出⾃信。
42.	⽐如，“系统层⾯”（“systems-level”）的⼯作，涉及内存管理、数据表⽰
43.	和并发等底层细节。从传统⻆度来看，这是⼀个神秘的编程领域，只为浸
44.	淫多年的极少数⼈所触及，也只有他们能避开那些臭名昭著的陷阱。即使
45.	谨慎的实践者，亦唯恐代码出现漏洞、崩溃或损坏。
46.	Rust 破除了这些障碍，其消除了旧的陷阱并提供了伴你⼀路同⾏的友
47.	好、精良的⼯具。想要 “深⼊” 底层控制的程序员可以使⽤ Rust，⽆需冒
48.	着常见的崩溃或安全漏洞的风险，也⽆需学习时常改变的⼯具链的最新知
49.	识。其语⾔本⾝更是被设计为⾃然⽽然的引导你编写出在运⾏速度和内存
50.	使⽤上都十分⾼效的可靠代码。
51.	已经在从事编写底层代码的程序员可以使⽤ Rust 来提升抱负。例如，在
52.	Rust 中引⼊并⾏是相对低风险的操作：编译器会为你捕获经典的错误。
53.	同时你可以⾃信的采取更为积极的优化，⽽不会意外引⼊崩溃或漏洞。
54.	但 Rust 并不局限于底层系统编程。其表现力和⼯效⾜以令⼈愉悦的编写
55.	出 CLI 应⽤、web server 和很多其他类型的代码 —— 在本书中你会看到
56.	两个简单⽰例。使⽤ Rust 能将你在⼀个领域中学习的技能延伸到另⼀个
57.	领域；你可以学习 Rust 来编写 web 应⽤，接着将同样的技能应⽤到你的
58.	Raspberry Pi（树莓派）上。
59.	本书全⾯介绍了 Rust 为⽤⼾赋予的能力。其内容平易近⼈，致力于帮助
60.	你提升 Rust 的知识，并且提升你作为程序员整体的理解与⾃信。那么让
61.	我们准备深⼊学习 Rust 吧（打开新世界的⼤门 :)） —— 欢迎加⼊ Rust
62.	社区！
—	Nicholas Matsakis 和 Aaron Turon
63.	介绍
64.	ch00-00-introduction.md
65.	commit 0aa307c7d79d2cbf83cdf5d47780b2904e9cb03f
66.	注意：本书的版本与出版的 The Rust Programming Language和
67.	电⼦版的 No Starch Press⼀致
68.	欢迎阅读 “Rust 程序设计语⾔ ”，⼀本介绍 Rust 的书。Rust 程序设计语
69.	⾔能帮助你编写更快、更可靠的软件。在编程语⾔设计中，⾼层⼯程学和
70.	底层控制往往不能兼得；Rust 则试图挑战这⼀⽭盾。通过权衡强⼤的技
71.	术能力与优秀的开发体验，Rust 允许你控制底层细节（⽐如内存使
72.	⽤），并免受以往进⾏此类控制所经受的所有烦恼。
73.	谁会使⽤ Rust
74.	Rust 因多种原因适⽤于很多开发者。让我们讨论⼏个最重要的群体。
75.	开发者团队
76.	Rust 被证明是可⽤于⼤型的、拥有不同层次系统编程知识的开发者团队
77.	间协作的⾼效⼯具。底层代码中容易出现种种隐晦的 bug，在其他编程语
78.	⾔中，只能通过⼤量的测试和经验丰富的开发者细心的代码评审来捕获它
79.	们。在 Rust 中，编译器充当了守门员的⻆⾊，它拒绝编译存在这些难以
80.	捕获的 bug 的代码，这其中包括并发 bug。通过与编译器合作，团队将
81.	更多的时间聚焦在程序逻辑上，⽽不是追踪 bug。
82.	Rust 也为系统编程世界带来了现代化的开发⼯具：
83.	Cargo，内置的依赖管理器和构建⼯具，它能轻松增加、编译和管
84.	理依赖，并使其在 Rust ⽣态系统中保持⼀致。
85.	Rustfmt 确保开发者遵循⼀致的代码风格。
86.	Rust Language Server 为集成开发环境（IDE）提供了强⼤的代码
87.	补全和内联错误信息功能。
88.	通过使⽤ Rust ⽣态系统中的这些和其他⼯具，开发者可以在编写系统层
89.	⾯代码时保持⾼⽣产力。
90.	学⽣
91.	Rust 适⽤于学⽣和有兴趣学习系统概念的⼈。通过 Rust，很多⼈已经了
92.	解了操作系统开发等主题。社区⾮常欢迎和乐于解答学⽣们的问题。通过
93.	本书的努力，Rust 团队希望系统概念能被更多⼈了解，特别是编程新
94.	⼿。
95.	公司
96.	数以百计的公司，⽆论规模⼤⼩，都在⽣产中使⽤Rust来完成各种任务。
97.	这些任务包括命令⾏⼯具、web 服务、DevOps ⼯具、嵌⼊式设备、⾳
98.	视频分析与转码、加密货币（cryptocurrencies）、⽣物信息学
99.	（bioinformatics）、搜索引擎、物联⽹（internet of things, IOT）程
100.	序、机器学习，甚⾄还包括 Firefox 浏览器的⼤部分内容。

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/Charlie-YCY/learnrust/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
