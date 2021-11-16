## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/Charlie-YCY/learnrust/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Rust 程序设计语⾔
title-page.md
commit a2bd349f8654f5c45ad1f07394225f946954b8ef
Steve Klabnik 和 Carol N  ichols，以及来⾃ Rust 社区的贡献（Rust
中⽂社区翻译）
本书假设你使⽤ Rust 1.41.0 或更新的版本，且在所有的项⽬中的
Cargo.toml⽂件中通过 edition="2018"采⽤ Rust 2018 Edition 规
范。请查看第⼀章的 “安装” 部分了解如何安装和升级 Rust，并查看新的
附录 E了解版本相关的信息。
Rust 程序设计语⾔的 2018 Edition 包含许多的改进使得 Rust 更为⼯程
化并更为容易学习。本书的此次迭代包括了很多反映这些改进的修改：
第七章 “使⽤包、Crate 和模块管理不断增⻓的项⽬” 基本上被重写
了。模块系统和路径（path）的⼯作⽅式变得更为⼀致。
第十章新增了名为 “trait 作为参数” 和 “返回实现了 trait 的类型” 部
分来解释新的 impl Trait语法。
第十⼀章新增了⼀个名为 “在测试中使⽤ Result<T, E> ” 的部分来
展⽰如何使⽤ ?运算符来编写测试
第十九章的 “⾼级⽣命周期” 部分被移除了，因为编译器的改进使得
其内容变得更为少见。
之前的附录 D “宏” 得到了补充，包括了过程宏并移动到了第十九章
的 “宏” 部分。
附录 A “关键字” 也介绍了新的原始标识符（raw identiﬁers）功
能，这使得采⽤ 2015 Edition 编写的 Rust 代码可以与 2018
Edition 互通。
现在的附录 D 名为 “实⽤开发⼯具”，它介绍了最近发布的可以帮助
你编写 Rust 代码的⼯具。
我们还修复了全书中许多错误和不准确的描述。感谢报告了这些问
题的读者们！
注意任何 “Rust 程序设计语⾔ ” 早期迭代中的代码在项⽬的 Cargo.toml中
不包含 edition="2018"时仍可以继续编译，哪怕你更新了 Rust 编译器
的版本。Rust 的后向兼容性保证了这⼀切可以正常运⾏！
本书的 HTML 版本可以在 https://doc.rust-lang.org/stable/book/（简
体中⽂译本）在线阅读，离线版则包含在通过 rustup安装的 Rust 中；
运⾏ rustup docs --book可以打开。
本书的纸质版和电⼦书由 No Starch Press发⾏。
前⾔
foreword.md
commit 1fedfc4b96c2017f64ecfcf41a0a07e2e815f24f
虽然不是那么明显，但 Rust 程序设计语⾔的本质在于赋能
（empowerment）：⽆论你现在编写的是何种代码，Rust 能让你在更为
⼴泛的编程领域⾛得更远，写出⾃信。
⽐如，“系统层⾯”（“systems-level”）的⼯作，涉及内存管理、数据表⽰
和并发等底层细节。从传统⻆度来看，这是⼀个神秘的编程领域，只为浸
淫多年的极少数⼈所触及，也只有他们能避开那些臭名昭著的陷阱。即使
谨慎的实践者，亦唯恐代码出现漏洞、崩溃或损坏。
Rust 破除了这些障碍，其消除了旧的陷阱并提供了伴你⼀路同⾏的友
好、精良的⼯具。想要 “深⼊” 底层控制的程序员可以使⽤ Rust，⽆需冒
着常见的崩溃或安全漏洞的风险，也⽆需学习时常改变的⼯具链的最新知
识。其语⾔本⾝更是被设计为⾃然⽽然的引导你编写出在运⾏速度和内存
使⽤上都十分⾼效的可靠代码。
已经在从事编写底层代码的程序员可以使⽤ Rust 来提升抱负。例如，在
Rust 中引⼊并⾏是相对低风险的操作：编译器会为你捕获经典的错误。
同时你可以⾃信的采取更为积极的优化，⽽不会意外引⼊崩溃或漏洞。
但 Rust 并不局限于底层系统编程。其表现力和⼯效⾜以令⼈愉悦的编写
出 CLI 应⽤、web server 和很多其他类型的代码 —— 在本书中你会看到
两个简单⽰例。使⽤ Rust 能将你在⼀个领域中学习的技能延伸到另⼀个
领域；你可以学习 Rust 来编写 web 应⽤，接着将同样的技能应⽤到你的
Raspberry Pi（树莓派）上。
本书全⾯介绍了 Rust 为⽤⼾赋予的能力。其内容平易近⼈，致力于帮助
你提升 Rust 的知识，并且提升你作为程序员整体的理解与⾃信。那么让
我们准备深⼊学习 Rust 吧（打开新世界的⼤门 :)） —— 欢迎加⼊ Rust
社区！
— Nicholas Matsakis 和 Aaron Turon
介绍
ch00-00-introduction.md
commit 0aa307c7d79d2cbf83cdf5d47780b2904e9cb03f
注意：本书的版本与出版的 The Rust Programming Language和
电⼦版的 No Starch Press⼀致
欢迎阅读 “Rust 程序设计语⾔ ”，⼀本介绍 Rust 的书。Rust 程序设计语
⾔能帮助你编写更快、更可靠的软件。在编程语⾔设计中，⾼层⼯程学和
底层控制往往不能兼得；Rust 则试图挑战这⼀⽭盾。通过权衡强⼤的技
术能力与优秀的开发体验，Rust 允许你控制底层细节（⽐如内存使
⽤），并免受以往进⾏此类控制所经受的所有烦恼。
谁会使⽤ Rust
Rust 因多种原因适⽤于很多开发者。让我们讨论⼏个最重要的群体。
开发者团队
Rust 被证明是可⽤于⼤型的、拥有不同层次系统编程知识的开发者团队
间协作的⾼效⼯具。底层代码中容易出现种种隐晦的 bug，在其他编程语
⾔中，只能通过⼤量的测试和经验丰富的开发者细心的代码评审来捕获它
们。在 Rust 中，编译器充当了守门员的⻆⾊，它拒绝编译存在这些难以
捕获的 bug 的代码，这其中包括并发 bug。通过与编译器合作，团队将
更多的时间聚焦在程序逻辑上，⽽不是追踪 bug。
Rust 也为系统编程世界带来了现代化的开发⼯具：
Cargo，内置的依赖管理器和构建⼯具，它能轻松增加、编译和管
理依赖，并使其在 Rust ⽣态系统中保持⼀致。
Rustfmt 确保开发者遵循⼀致的代码风格。
Rust Language Server 为集成开发环境（IDE）提供了强⼤的代码
补全和内联错误信息功能。
通过使⽤ Rust ⽣态系统中的这些和其他⼯具，开发者可以在编写系统层
⾯代码时保持⾼⽣产力。
学⽣
Rust 适⽤于学⽣和有兴趣学习系统概念的⼈。通过 Rust，很多⼈已经了
解了操作系统开发等主题。社区⾮常欢迎和乐于解答学⽣们的问题。通过
本书的努力，Rust 团队希望系统概念能被更多⼈了解，特别是编程新
⼿。
公司
数以百计的公司，⽆论规模⼤⼩，都在⽣产中使⽤Rust来完成各种任务。
这些任务包括命令⾏⼯具、web 服务、DevOps ⼯具、嵌⼊式设备、⾳
视频分析与转码、加密货币（cryptocurrencies）、⽣物信息学
（bioinformatics）、搜索引擎、物联⽹（internet of things, IOT）程
序、机器学习，甚⾄还包括 Firefox 浏览器的⼤部分内容。
开源开发者
Rust 适⽤于希望构建 Rust 编程语⾔、社区、开发⼯具和库的开发者。我
们很乐意您为 Rust 语⾔做贡献。
重视速度和稳定性的开发者
Rust 适⽤于追求编程语⾔的速度与稳定性的开发者。所谓速度，是指你
⽤ Rust 开发出的程序运⾏速度，以及 Rust 提供的程序开发速度。Rust
的编译器检查确保了增加功能和重构代码时的稳定性。这与缺少这些检查
的语⾔形成鲜明对⽐，开发者通常害怕修改那些脆弱的遗留代码。力求零
开销抽象（zero-cost abstractions），把⾼级的特性编译成底层的代
码，这样写起来很快，运⾏起来也很快，Rust 致力于使安全的代码也同
样快速。
Rust 语⾔也希望能⽀持很多其他⽤⼾，这⾥提及的只是最⼤的利益相关
者。总的来讲，Rust 最重要的⽬标是消除数十年来程序员不得不做的权
衡：安全与⽣产力，速度与⼈机交互的顺畅度(ergonomics)。请尝试
Rust，看看这个选择是否适合你。
本书是写给谁的
本书假设你已经使⽤其他编程语⾔编写过代码，但并不假设你使⽤的是何
种语⾔。我们尝试使这些参考资料能⼴泛的适⽤于来⾃很多不同编程背景
的开发者。我们不会花费很多时间讨论编程是什么或者如何理解它。如
果编程对于你来说是完全陌⽣的，你最好先阅读专门介绍编程的书籍。
如何阅读本书
总体来说，本书假设你会从头到尾顺序阅读。稍后的章节建⽴在之前章节
概念的基础上，同时之前的章节可能不会深⼊讨论某个主题的细节；通常
稍后的章节会重新讨论这些主题。
你会在本书中发现两类章节：概念章节和项⽬章节。在概念章节中，我们
学习 Rust 的某个⽅⾯。在项⽬章节中，我们应⽤⽬前所学的知识⼀同构
建⼩的程序。第⼆、十⼆和⼆十章是项⽬章节；其余都是概念章节。
第⼀章介绍如何安装 Rust，如何编写 “Hello, world!” 程序，以及如何使
⽤ Rust 的包管理器和构建⼯具 Cargo。第⼆章是 Rust 语⾔的实战介
绍。我们会站在较⾼的层次介绍⼀些概念，⽽将详细的介绍放在稍后的章
节中。如果你希望⽴刻就动⼿实践⼀下，第⼆章正好适合你。开始阅读
时，你甚⾄可能希望略过第三章，它介绍了 Rust 中类似其他编程语⾔中
的功能，并直接阅读第四章学习 Rust 的所有权系统。然⽽，如果你是特
别重视细节的学习者，并倾向于在继续之前学习每⼀个细节，你可能希望
略过第⼆章并直接阅读第三章，并在想要构建项⽬来实践这些细节时再回
来阅读第⼆章。
第五章讨论结构体和⽅法，第六章介绍枚举、match表达式和 if let
控制流结构。在 Rust 中，你将使⽤结构体和枚举创建⾃定义类型。
第七章你会学习 Rust 的模块系统和私有性规则来组织代码和公有应⽤程
序接⼝（Application Programming Interface, API）。第⼋章讨论了⼀
些标准库提供的常见集合数据结构，⽐如可变⻓数组(vector)、字符串和
哈希 map。第九章探索了 Rust 的错误处理哲学和技术。
第十章深⼊介绍泛型、trait 和⽣命周期，他们提供了定义出适⽤于多种
类型的代码的能力。第十⼀章全部关于测试，即使 Rust 有安全保证，也
需要测试确保程序逻辑正确。第十⼆章，我们构建了属于⾃⼰的在⽂件中
搜索⽂本的命令⾏⼯具 grep的⼦集功能实现。为此会利⽤之前章节讨
论的很多概念。
第十三章探索了闭包和迭代器：Rust 中来⾃函数式编程语⾔的功能。第
十四章会更深层次的理解 Cargo 并讨论向他⼈分享库的最佳实践。第十
五章讨论标准库提供的智能指针以及启⽤这些功能的 trait。
第十六章会学习不同的并发编程模型，并讨论 Rust 如何助你⽆畏的编写
多线程程序。第十七章着眼于⽐较 Rust 风格与你可能熟悉的⾯向对象编
程原则。
第十⼋章是关于模式和模式匹配的参考章节，它是在Rust程序中表达思想
的有效⽅式。第十九章是⼀个⾼级主题⼤杂烩，包括 unsafe Rust、宏和
更多关于⽣命周期、 trait、类型、函数和闭包的内容。
第⼆十章将会完成⼀个项⽬，我们会实现⼀个底层的、多线程的 web
server！
最后是⼀些附录，包含了⼀些关于语⾔的参考风格格式的实⽤信息。附录
A 介绍了 Rust 的关键字。附录 B 介绍 Rust 的运算符和符号。附录 C 介
绍标准库提供的派⽣ trait。附录 D 涉及了⼀些有⽤的开发⼯具，附录 E
介绍了 Rust 的不同版本。
怎样阅读本书都不会有任何问题：如果你希望略过⼀些内容，请继续！如
果你发现疑惑可能会再跳回之前的章节。请随意阅读。
学习 Rust 的过程中⼀个重要的部分是学习如何阅读编译器提供的错误信
息：它们会指导你编写出能⼯作的代码。为此，我们会提供很多不能编译
的⽰例代码，以及各个情况下编译器会展⽰的错误信息。请注意如果随便
输⼊并运⾏随机的⽰例代码，它们可能⽆法编译！请确保阅读任何你尝试
运⾏的⽰例周围的内容，检视他们是否有意写错。Ferris 也会帮助你区别
那些有意⽆法⼯作的代码：
Ferris
意义
这些代码不能编译！
这些代码会 panic！
这些代码块包含不安全（unsafe）代码。
Ferris
意义
这些代码不会产⽣期望的⾏为。
在⼤部分情况，我们会指引你将任何不能编译的代码纠正为正确版本。
源代码
⽣成本书的源码可以在 GitHub上找到。
译者注：本译本的 GitHub 仓库，欢迎 Issue 和 PR :)
⼊门指南
ch01-00-getting-started.md
commit 1fedfc4b96c2017f64ecfcf41a0a07e2e815f24f
让我们开始 Rust 之旅！有很多内容需要学习，但每次旅程总有起点。在
本章中，我们会讨论：
在 Linux、macOS 和 Windows 上安装 Ru  st
编写⼀个打印 Hello, world!的程序
使⽤ Rust 的包管理器和构建系统 cargo
安装
ch01-01-installation.md
commit bad683bb7dcd06ef7f5f83bad3a25b1706b7b230
第⼀步是安装 Rust。我们会通过 rustup下载 Rust，这是⼀个管理
Rust 版本和相关⼯具的命令⾏⼯具。下载时需要联⽹。
注意：如果你出于某些理由倾向于不使⽤ rustup，请到 Rust 安装
页⾯查看其它安装选项。
接下来的步骤会安装最新的稳定版 Rust 编译器。 Rust 的稳定性确保本书
所有⽰例在最新版本的 Rust 中能够继续编译。不同版本的输出可能略有
不同，因为 Rust 经常改进错误信息和警告。也就是说，任何通过这些步
骤安装的最新稳定版 Rust，都应该能正常运⾏本书中的内容。
命令⾏标记
本章和全书中，我们会展⽰⼀些在终端中使⽤的命令。所有需要输
⼊到终端的⾏都以 $开头。但⽆需输⼊$；它代表每⾏命令的起
点。不以 $起始的⾏通常展⽰之前命令的输出。另
外，PowerShell 专⽤的⽰例会采⽤ >⽽不是 $。
在 Linux 或 macOS 上安装rruussttuupp
如果你使⽤ Linux 或 macOS ，打开终端并输⼊如下命令：
$ curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf 
| sh
此命令下载⼀个脚本并开始安装 rustup⼯具，这会安装最新稳定版
Rust。过程中可能会提⽰你输⼊密码。如果安装成功，将会出现如下内
容：
Rust is installed now. Great!
另外，你需要⼀个某种类型的链接器（linker）。很有可能已经安装，不
过当你尝试编译 Rust 程序时，却有错误指出⽆法执⾏链接器，这意味着
你的系统上没有安装链接器，你需要⾃⾏安装⼀个。C 编译器通常带有正
确的链接器。请查看你使⽤平台的⽂档，了解如何安装 C 编译器。并
且，⼀些常⽤的 Rust 包依赖 C 代码，也需要安装 C 编译器。因此现在安
装⼀个是值得的。
在 Windows 上安装rruussttuupp
在 Windows 上，前往 https://www.rust-lang.org/install.html并按照说
明安装 Rust。在安装过程的某个步骤，你会收到⼀个信息说明为什么需
要安装 Visual Studio 2013 或更新版本的 C++ build tools。获取这些
build tools 最⽅便的⽅法是安装 Build Tools for Visual Studio 2019。当
被问及需要安装什么的时候请确保选择 ”C++ build tools“，并确保包括了
Windows 10 SDK 和英⽂语⾔包（English language pack）组件。
本书的余下部分会使⽤能同时运⾏于 cmd.exe和 PowerShell 的命令。如
果存在特定差异，我们会解释使⽤哪⼀个。
更新和卸载
通过 rustup安装了 Rust 之后，很容易更新到最新版本。在 shell 中运
⾏如下更新脚本：
$ rustup update
为了卸载 Rust 和 rustup，在 shell 中运⾏如下卸载脚本:
$ rustup self uninstall
故障排除（Troubleshooting）
要检查是否正确安装了 Rust，打开 shell 并运⾏如下⾏：
$ rustc --version
你应能看到已发布的最新稳定版的版本号、提交哈希和提交⽇期，显⽰为
如下格式：
rustc x.y.z (abcabcabc yyyy-mm-dd)
如果出现这些内容，Rust 就安装成功了！如果并没有看到这些信息，并
且使⽤的是 Windows，请检查 Rust 是否位于 %PATH%系统变量中。如
果⼀切正确但 Rust 仍不能使⽤，有许多地⽅可以求助。最简单的是位于
Rust 官⽅ Discord 上的 #beginners 频道。在这⾥你可以和其他
Rustacean（Rust ⽤⼾的称号，有⾃嘲意味）聊天并寻求帮助。其它给
力的资源包括⽤⼾论坛和 Stack Overﬂow。
译者：恭喜⼊坑！（此处应该有掌声！）
本地⽂档
安装程序也⾃带⼀份⽂档的本地拷贝，可以离线阅读。运⾏ rustup doc
在浏览器中查看本地⽂档。
任何时候，如果你拿不准标准库中的类型或函数的⽤途和⽤法，请查阅应
⽤程序接⼝（application programming interface，API）⽂档！
Hello, World!
ch01-02-hello-world.md
commit f63a103270ec8416899675a9cdb1c5cf6d77a498
既然安装好了 Rust，我们来编写第⼀个 Rust 程序。当学习⼀门新语⾔的
时候，使⽤该语⾔在屏幕上打印 Hello, world!是⼀项传统，我们将沿
⽤这⼀传统！
注意：本书假设你熟悉基本的命令⾏操作。Rust 对于你的编辑器、
⼯具，以及代码位于何处并没有特定的要求，如果你更倾向于使⽤
集成开发环境（IDE），⽽不是命令⾏，请尽管使⽤你喜欢的 IDE。
⽬前很多 IDE 已经不同程度的⽀持 Rust；查看 IDE ⽂档了解更多细
节。最近，Rust 团队已经致力于提供强⼤的 IDE ⽀持，⽽且进展⻜
速！
创建项⽬⽬录
首先创建⼀个存放 Rust 代码的⽬录。Rust 并不关心代码的存放位置，不
过对于本书的练习和项⽬来说，我们建议你在 home ⽬录中创建 projects
⽬录，并将你的所有项⽬存放在这⾥。
打开终端并输⼊如下命令创建 projects⽬录，并在 projects⽬录中为
“Hello, world!” 项⽬创建⼀个⽬录。
对于 Linux、macOS 和 Windows PowerShell，输⼊：
$ mkdir ~/projects
$ cd ~/projects
$ mkdir hello_world
$ cd hello_world
对于 Windows CMD，输⼊：
> mkdir "%USERPROFILE%\projects"
> cd /d "%USERPROFILE%\projects"
> mkdir hello_world
> cd hello_world
编写并运⾏ Rust 程序
接下来，新建⼀个源⽂件，命名为 main.rs。Rust 源⽂件总是以 .rs扩展
名结尾。如果⽂件名包含多个单词，使⽤下划线分隔它们。例如命名为
hello_world.rs，⽽不是 helloworld.rs。
现在打开刚创建的 main.rs⽂件，输⼊⽰例 1-1 中的代码。
⽂件名: main.rs
fn main() {
println!("Hello, world!");
}
⽰例 1-1: ⼀个打印 Hello, world!的程序
保存⽂件，并回到终端窗⼝。在 Linux 或 macOS 上，输⼊如下命令，编
译并运⾏⽂件：
$ rustc main.rs
$ ./main
Hello, world!
在 Windows 上，输⼊命令 .\main.exe，⽽不是 ./main：
> rustc main.rs
> .\main.exe
Hello, world!
不管使⽤何种操作系统，终端应该打印字符串 Hello, world!。如果没
有看到这些输出，回到安装部分的 “故障排除”⼩节查找有帮助的⽅法。
如果 Hello, world!出现了，恭喜你！你已经正式编写了⼀个 Rust 程
序。现在你成为⼀名 Rust 程序员，欢迎！
分析这个 Rust 程序
现在，让我们回过头来仔细看看 “Hello, world!” 程序中到底发⽣了什么。
这是第⼀块拼图：
fn main() {
}
这⼏⾏定义了⼀个 Rust 函数。 main函数是⼀个特殊的函数：在可执⾏
的 Rust 程序中，它总是最先运⾏的代码。第⼀⾏代码声明了⼀个叫做
main的函数，它没有参数也没有返回值。如果有参数的话，它们的名称
应该出现在⼩括号中，()。
还须注意，函数体被包裹在花括号中，{}。Rust 要求所有函数体都要⽤
花括号包裹起来。⼀般来说，将左花括号与函数声明置于同⼀⾏并以空格
分隔，是良好的代码风格。
在编写本书的时候，⼀个叫做 rustfmt的⾃动格式化⼯具正在开发中。
如果你希望在 Rust 项⽬中保持⼀种标准风格， rustfmt会将代码格式化
为特定的风格。Rust 团队计划最终将该⼯具包含在标准 Rust 发⾏版中，
就像 rustc。所以根据你阅读本书的时间，它可能已经安装到你的电脑
中了！检查在线⽂档以了解更多细节。
在 main()函数中是如下代码：
println!("Hello, world!");
这⾏代码完成这个简单程序的所有⼯作：在屏幕上打印⽂本。这⾥有四个
重要的细节需要注意。首先 Rust 的缩进风格使⽤ 4 个空格，⽽不是 1 个
制表符（tab）。
第⼆，println!调⽤了⼀个 Rust 宏（macro）。如果是调⽤函数，则
应输⼊ println（没有 !）。我们将在第十九章详细讨论宏。现在你只
需记住，当看到符号 !的时候，就意味着调⽤的是宏⽽不是普通函数。
第三，"Hello, world!"是⼀个字符串。我们把这个字符串作为⼀个参
数传递给 println!，字符串将被打印到屏幕上。
第四，该⾏以分号结尾（;），这代表⼀个表达式的结束和下⼀个表达式
的开始。⼤部分 Rust 代码⾏以分号结尾。
编译和运⾏是彼此独⽴的步骤
你刚刚运⾏了⼀个新创建的程序，那么让我们检查此过程中的每⼀个步
骤。
在运⾏ Rust 程序之前，必须先使⽤ Rust 编译器编译它，即输⼊ rustc
命令并传⼊源⽂件名称，如下：
$ rustc main.rs
如果你有 C 或 C++ 背景，就会发现这与 gcc和 clang类似。编译成功
后，Rust 会输出⼀个⼆进制的可执⾏⽂件。
在 Linux、macOS 或 Windows 的 Powe  rShell 上，在 shell  中输⼊ ls
命令可以看见这个可执⾏⽂件。在 Linux 和 macOS，你会看到两个⽂
件。在 Windows PowerShell 中，你会看到同使⽤ CMD 相同的三个⽂
件。
$ ls
main  main.rs
在 Windows 的 CMD 上，则输⼊如下内容：
> dir /B %= the /B option says to only show the file names 
=%
main.exe
main.pdb
main.rs
这展⽰了扩展名为 .rs的源⽂件、可执⾏⽂件（在 Windows 下是
main.exe，其它平台是 main），以及当使⽤ CMD 时会有⼀个包含调试
信息、扩展名为 .pdb的⽂件。从这⾥开始运⾏ main或 main.exe⽂件，
如下：
$ ./main # Windows 是 .\main.exe
如果 main.rs是上⽂所述的 “Hello, world!” 程序，它将会在终端上打印
Hello, world!。
如果你更熟悉动态语⾔，如 Ruby、Python 或 JavaScript，则可能不习惯
将编译和运⾏分为两个单独的步骤。Rust 是⼀种预编译静态类型
（ahead-of-time compiled）语⾔，这意味着你可以编译程序，并将可执
⾏⽂件送给其他⼈，他们甚⾄不需要安装 Rust 就可以运⾏。如果你给他
⼈⼀个 .rb、.py或 .js⽂件，他们需要先分别安装
Ruby，Python，JavaScript 实现（运⾏时环境，VM）。不过在这些语⾔
中，只需要⼀句命令就可以编译和运⾏程序。这⼀切都是语⾔设计上的权
衡取舍。
仅仅使⽤ rustc编译简单程序是没问题的，不过随着项⽬的增⻓，你可
能需要管理你项⽬的⽅⽅⾯⾯，并让代码易于分享。接下来，我们要介绍
⼀个叫做 Cargo 的⼯具，它会帮助你编写真实世界中的 Rust 程序。
Hello, Cargo!
ch01-03-hello-cargo.md
commit f63a103270ec8416899675a9cdb1c5cf6d77a498
Cargo 是 Rust 的构建系统和包管理器。⼤多数 Rustacean 们使⽤ Cargo
来管理他们的 Rust 项⽬，因为它可以为你处理很多任务，⽐如构建代
码、下载依赖库并编译这些库。（我们把代码所需要的库叫做依赖
（dependencies））。
最简单的 Rust 程序，⽐如我们刚刚编写的，没有任何依赖。所以如果使
⽤ Cargo 来构建 “Hello, world!” 项⽬，将只会⽤到 Cargo 构建代码的那
部分功能。在编写更复杂的 Rust 程序时，你将添加依赖项，如果使⽤
Cargo 启动项⽬，则添加依赖项将更容易。
由于绝⼤多数 Rust 项⽬使⽤ Cargo，本书接下来的部分假设你也使⽤
Cargo。如果使⽤ “安装”部分介绍的官⽅安装包的话，则⾃带了 Cargo。
如果通过其他⽅式安装的话，可以在终端输⼊如下命令检查是否安装了
Cargo：
$ cargo --version
如果你看到了版本号，说明已安装！如果看到类似 command not found
的错误，你应该查看相应安装⽂档以确定如何单独安装 Cargo。
使⽤ Cargo 创建项⽬
我们使⽤ Cargo 创建⼀个新项⽬，然后看看与上⾯的 Hello, world! 项⽬
有什么不同。回到 projects⽬录（或者你存放代码的⽬录）。接着，可在
任何操作系统下运⾏以下命令：
$ cargo new hello_cargo
$ cd hello_cargo
第⼀⾏命令新建了名为 hello_cargo的⽬录。我们将项⽬命名为
hello_cargo，同时 Cargo 在⼀个同名⽬录中创建项⽬⽂件。
进⼊ hello_cargo⽬录并列出⽂件。将会看到 Cargo ⽣成了两个⽂件和⼀
个⽬录：⼀个 Cargo.toml⽂件，⼀个 src⽬录，以及位于 src⽬录中的
main.rs⽂件。它也在 hello_cargo⽬录初始化了⼀个 git 仓库，以及⼀个
.gitignore⽂件。
注意：Git 是⼀个常⽤的版本控制系统（version control system，
VCS）。可以通过 --vcs参数使 cargo new切换到其它版本控制
系统（VCS），或者不使⽤ VCS。运⾏ cargo new --help参看可
⽤的选项。
请⾃⾏选⽤⽂本编辑器打开 Cargo.toml⽂件。它应该看起来如⽰例 1-2
所⽰：
⽂件名: Cargo.toml
[package]
name = "hello_cargo"
version = "0.1.0"
authors = ["Your Name <you@example.com>"]
edition = "2018"
[dependencies]
⽰例 1-2: cargo new命令⽣成的 Cargo.toml的内容
这个⽂件使⽤ TOML (Tom's Obvious, Minimal Language) 格式，这是
Cargo 配置⽂件的格式。
第⼀⾏，[package]，是⼀个⽚段（section）标题，表明下⾯的语句⽤
来配置⼀个包。随着我们在这个⽂件增加更多的信息，还将增加其他⽚段
（section）。
接下来的四⾏设置了 Cargo 编译程序所需的配置：项⽬的名称、版本、
作者以及要使⽤的 Rust 版本。Cargo 从环境中获取你的名字和 email 信
息，所以如果这些信息不正确，请修改并保存此⽂件。附录 E 会介绍
edition的值。
最后⼀⾏，[dependencies]，是罗列项⽬依赖的⽚段的开始。在 Rust
中，代码包被称为 crates。这个项⽬并不需要其他的 crate，不过在第⼆
章的第⼀个项⽬会⽤到依赖，那时会⽤得上这个⽚段。
现在打开 src/main.rs看看：
⽂件名: src/main.rs
fn main() {
println!("Hello, world!");
}
Cargo 为你⽣成了⼀个 “Hello, world!” 程序，正如我们之前编写的⽰例
1-1！⽬前为⽌，之前项⽬与 Cargo ⽣成项⽬的区别是 Cargo 将代码放在
src⽬录，同时项⽬根⽬录包含⼀个 Cargo.toml配置⽂件。
Cargo 期望源⽂件存放在 src⽬录中。项⽬根⽬录只存放 README、
license 信息、配置⽂件和其他跟代码⽆关的⽂件。使⽤ Cargo 帮助你保
持项⽬⼲净整洁，⼀切井井有条。
如果没有使⽤ Cargo 开始项⽬，⽐如我们创建的 Hello,world! 项⽬，可
以将其转化为⼀个 Cargo 项⽬。将代码放⼊ src⽬录，并创建⼀个合适的
Cargo.toml⽂件。
构建并运⾏ Cargo 项⽬
现在让我们看看通过 Cargo 构建和运⾏ “Hello, world!” 程序有什么不
同！在 hello_cargo⽬录下，输⼊下⾯的命令来构建项⽬：
$ cargo build
   Compiling hello_cargo v0.1.0 (file:///projects
/hello_cargo)
    Finished dev [unoptimized + debuginfo] target(s) in 
2.85 secs
这个命令会创建⼀个可执⾏⽂件 target/debug/hello_cargo（在 Windows
上是 target\debug\hello_cargo.exe），⽽不是放在⽬前⽬录下。可以通过
这个命令运⾏可执⾏⽂件：
$ ./target/debug/hello_cargo # 或者在 Windows 下为 .\target
\debug\hello_cargo.exe
Hello, world!
如果⼀切顺利，终端上应该会打印出 Hello, world!。首次运⾏ cargo 
build时，也会使 Cargo 在项⽬根⽬录创建⼀个新⽂件：Cargo.lock。这
个⽂件记录项⽬依赖的实际版本。这个项⽬并没有依赖，所以其内容⽐较
少。你⾃⼰永远也不需要碰这个⽂件，让 Cargo 处理它就⾏了。
我们刚刚使⽤ cargo build构建了项⽬，并使⽤ ./target/debug
/hello_cargo运⾏了程序，也可以使⽤ cargo run在⼀个命令中同时
编译并运⾏⽣成的可执⾏⽂件：
$ cargo run
    Finished dev [unoptimized + debuginfo] target(s) in 0.0 
secs
     Running `target/debug/hello_cargo`
Hello, world!
注意这⼀次并没有出现表明 Cargo 正在编译 hello_cargo的输出。
Cargo 发现⽂件并没有被改变，就直接运⾏了⼆进制⽂件。如果修改了源
⽂件的话，Cargo 会在运⾏之前重新构建项⽬，并会出现像这样的输出：
$ cargo run
   Compiling hello_cargo v0.1.0 (file:///projects
/hello_cargo)
    Finished dev [unoptimized + debuginfo] target(s) in 
0.33 secs
     Running `target/debug/hello_cargo`
Hello, world!
Cargo 还提供了⼀个叫 cargo check的命令。该命令快速检查代码确保
其可以编译，但并不产⽣可执⾏⽂件：
$ cargo check
   Checking hello_cargo v0.1.0 (file:///projects
/hello_cargo)
    Finished dev [unoptimized + debuginfo] target(s) in 
0.32 secs
为什么你会不需要可执⾏⽂件呢？通常 cargo check要⽐ cargo 
build快得多，因为它省略了⽣成可执⾏⽂件的步骤。如果你在编写代
码时持续的进⾏检查，cargo check会加速开发！为此很多 Rustaceans
编写代码时定期运⾏ cargo check确保它们可以编译。当准备好使⽤可
执⾏⽂件时才运⾏ cargo build。
我们回顾下已学习的 Cargo 内容：
可以使⽤ cargo build或 cargo check构建项⽬。
可以使⽤ cargo run⼀步构建并运⾏项⽬。
有别于将构建结果放在与源码相同的⽬录，Cargo 会将其放到
target/debug⽬录。
使⽤ Cargo 的⼀个额外的优点是，不管你使⽤什么操作系统，其命令都
是⼀样的。所以从现在开始本书将不再为 Linux 和 macOS 以及
Windows 提供相应的命令。
发布（release）构建
当项⽬最终准备好发布时，可以使⽤ cargo build --release来优化编
译项⽬。这会在 target/release⽽不是 target/debug下⽣成可执⾏⽂件。
这些优化可以让 Rust 代码运⾏的更快，不过启⽤这些优化也需要消耗更
⻓的编译时间。这也就是为什么会有两种不同的配置：⼀种是为了开发，
你需要经常快速重新构建；另⼀种是为⽤⼾构建最终程序，它们不会经常
重新构建，并且希望程序运⾏得越快越好。如果你在测试代码的运⾏时
间，请确保运⾏ cargo build --release并使⽤ target/release下的可
执⾏⽂件进⾏测试。
把 Cargo 当作习惯
对于简单项⽬， Cargo 并不⽐ rustc提供了更多的优势，不过随着开发
的深⼊，终将证明其价值。对于拥有多个 crate 的复杂项⽬，交给 Cargo
来协调构建将简单的多。
即便 hello_cargo项⽬十分简单，它现在也使⽤了很多在你之后的
Rust ⽣涯将会⽤到的实⽤⼯具。其实，要在任何已存在的项⽬上⼯作
时，可以使⽤如下命令通过 Git 检出代码，移动到该项⽬⽬录并构建：
$ git clone someurl.com/someproject
$ cd someproject
$ cargo build
关于更多 Cargo 的信息，请查阅其⽂档。
总结
你已经准备好开启 Rust 之旅了！在本章中，你学习了如何：
使⽤ rustup安装最新稳定版的 Rust
更新到新版的 Rust
打开本地安装的⽂档
直接通过 rustc编写并运⾏ Hello, world! 程序
使⽤ Cargo 创建并运⾏新项⽬
是时候通过构建更实质性的程序来熟悉读写 Rust 代码了。所以在第⼆章
我们会构建⼀个猜猜看游戏程序。如果你更愿意从学习 Rust 常⽤的编程
概念开始，请阅读第三章，接着再回到第⼆章。
编写猜猜看游戏
ch02-00-guessing-game-tutorial.md
commit c427a676393d001edc82f1a54a3b8026abcf9690
让我们⼀起动⼿完成⼀个项⽬，来快速上⼿ Rust！本章将介绍 Rust 中⼀
些常⽤概念，并通过真实的程序来展⽰如何运⽤它们。你将会学到
let、match、⽅法、关联函数、外部 crate 等知识！后续章节会深⼊探
讨这些概念的细节。在这⼀章，我们将做基础练习。
我们会实现⼀个经典的新⼿编程问题：猜猜看游戏。它是这么⼯作的：程
序将会随机⽣成⼀个 1 到 100 之间的随机整数。接着它会请玩家猜⼀个
数并输⼊，然后提⽰猜测是⼤了还是⼩了。如果猜对了，它会打印祝贺信
息并退出。
准备⼀个新项⽬
要创建⼀个新项⽬，进⼊第⼀章中创建的 projects⽬录，使⽤ Cargo 新
建⼀个项⽬，如下：
$ cargo new guessing_game
$ cd guessing_game
第⼀个命令， cargo new，它获取项⽬的名称（guessing_game）作为
第⼀个参数。第⼆个命令进⼊到新创建的项⽬⽬录。
看看⽣成的 Cargo.toml⽂件：
⽂件名: Cargo.toml
[package]
name = "guessing_game"
version = "0.1.0"
authors = ["Your Name <you@example.com>"]
edition = "2018"
[dependencies]
如果 Cargo 从环境中获取的开发者信息不正确，修改这个⽂件并再次保
存。
正如第⼀章那样，cargo new⽣成了⼀个 “Hello, world!” 程序。查看
src/main.rs⽂件：
⽂件名: src/main.rs
fn main() {
println!("Hello, world!");
}
现在使⽤ cargo run命令，⼀步完成 “Hello, world!” 程序的编译和运
⾏：
$ cargo run
   Compiling guessing_game v0.1.0 (file:///projects
/guessing_game)
    Finished dev [unoptimized + debuginfo] target(s) in 
1.50 secs
     Running `target/debug/guessing_game`
Hello, world!
当你需要在项⽬中快速迭代时，run命令就能派上⽤场，正如我们在这
个游戏项⽬中做的，在下⼀次迭代之前快速测试每⼀次迭代。
重新打开 src/main.rs⽂件。我们将会在这个⽂件中编写全部的代码。
处理⼀次猜测
猜猜看程序的第⼀部分请求和处理⽤⼾输⼊，并检查输⼊是否符合预期的
格式。首先，允许玩家输⼊猜测。在 src/main.rs中输⼊⽰例 2-1 中的代
码。
⽂件名: src/main.rs
use std::io;
fn main() {
println!("Guess the number!");
println!("Please input your guess.");
let mut guess = String::new();
    io::stdin().read_line(&mut guess)
        .expect("Failed to read line");
println!("You guessed: {}", guess);
}
⽰例 2-1：获取⽤⼾猜测并打印的代码
这些代码包含很多信息，我们⼀⾏⼀⾏地过⼀遍。为了获取⽤⼾输⼊并打
印结果作为输出，我们需要将 io（输⼊/输出）库引⼊当前作⽤域。io
库来⾃于标准库（也被称为 std）：
use std::io;
默认情况下，Rust 将 prelude模块中少量的类型引⼊到每个程序的作⽤
域中。如果需要的类型不在 prelude 中，你必须使⽤ use语句显式地将
其引⼊作⽤域。std::io库提供很多有⽤的功能，包括接收⽤⼾输⼊的
功能。
如第⼀章所提及，main函数是程序的⼊⼝点：
fn main() {
fn语法声明了⼀个新函数， ()表明没有参数，{作为函数体的开始。
第⼀章也提及了 println!是⼀个在屏幕上打印字符串的宏：
println!("Guess the number!");
println!("Please input your guess.");
这些代码仅仅打印提⽰，介绍游戏的内容然后请求⽤⼾输⼊。
使⽤变量储存值
接下来，创建⼀个储存⽤⼾输⼊的地⽅，像这样：
let mut guess = String::new();
现在程序开始变得有意思了！这⼀⼩⾏代码发⽣了很多事。注意这是⼀个
let语句，⽤来创建变量（variable）。这⾥是另外⼀个例⼦：
let foo = bar;
这⾏代码新建了⼀个叫做 foo的变量并把它绑定到值 bar上。在 Rust
中，变量默认是不可变的。我们将会在第三章的 “变量与可变性”部分详
细讨论这个概念。下⾯的例⼦展⽰了如何在变量名前使⽤ mut来使⼀个
变量可变：
let foo = 5; // 不可变
let mut bar = 5; // 可变
注意：//语法开始⼀个注释，持续到⾏尾。Rust 忽略注释中的所
有内容，第三章将会详细介绍注释。
让我们回到猜猜看程序中。现在我们知道了 let mut guess会引⼊⼀个
叫做 guess的可变变量。等号（ =）的右边是 guess所绑定的值，它
是 String::new的结果，这个函数会返回⼀个 String的新实例。
String是⼀个标准库提供的字符串类型，它是 UTF-8 编码的可增⻓⽂
本块。
::new那⼀⾏的 ::语法表明 new是 String类型的⼀个关联函数
（associated function）。关联函数是针对类型实现的，在这个例⼦中是
String，⽽不是 String的某个特定实例。⼀些语⾔中把它称为静态
⽅法（static method）。
new函数创建了⼀个新的空字符串，你会发现很多类型上有 new函数，
因为它是创建类型实例的惯⽤函数名。
总结⼀下，let mut guess = String::new();这⼀⾏创建了⼀个可变
变量，当前它绑定到⼀个新的 String空实例上。
回忆⼀下，我们在程序的第⼀⾏使⽤ use std::io;从标准库中引⼊了
输⼊/输出功能。现在调⽤ io库中的函数 stdin：
io::stdin().read_line(&mut guess)
    .expect("Failed to read line");
如果程序的开头没有 use std::io这⼀⾏，可以把函数调⽤写成
std::io::stdin。stdin函数返回⼀个 std::io::Stdin的实例，这
代表终端标准输⼊句柄的类型。
代码的下⼀部分，.read_line(&mut guess)，调⽤ read_line⽅法从
标准输⼊句柄获取⽤⼾输⼊。我们还向 read_line()传递了⼀个参
数：&mut guess。
read_line的⼯作是，⽆论⽤⼾在标准输⼊中键⼊什么内容，都将其存
⼊⼀个字符串中，因此它需要字符串作为参数。这个字符串参数应该是可
变的，以便 read_line将⽤⼾输⼊附加上去。
&表⽰这个参数是⼀个引⽤（reference），它允许多处代码访问同⼀处
数据，⽽⽆需在内存中多次拷贝。引⽤是⼀个复杂的特性，Rust 的⼀个
主要优势就是安全⽽简单的操纵引⽤。完成当前程序并不需要了解如此多
细节。现在，我们只需知道它像变量⼀样，默认是不可变的。因此，需要
写成 &mut guess来使其可变，⽽不是 &guess。（第四章会更全⾯的
解释引⽤。）
使⽤RReessuulltt类型来处理潜在的错误
我们还没有完全分析完这⾏代码。虽然这是单独⼀⾏代码，但它是逻辑⾏
（虽然换⾏了但仍是语句）的⼀部分。后⼀部分是这个⽅法：
.expect("Failed to read line");
当使⽤ .foo()语法调⽤⽅法时，通过换⾏加缩进来把⻓⾏拆开是明智
的。我们完全可以这样写：
io::stdin().read_line(&mut guess).expect("Failed to read 
line");
不过，过⻓的⾏难以阅读，所以最好拆开来写，两个⽅法调⽤占两⾏。现
在来看看这⾏代码⼲了什么。
之前提到了 read_line将⽤⼾输⼊附加到传递给它的字符串中，不过它
也返回⼀个值——在这个例⼦中是 io::Result。Rust 标准库中有很多
叫做 Result的类型：⼀个通⽤的 Result以及在⼦模块中的特化版
本，⽐如 io::Result。
Result类型是枚举（enumerations），通常也写作 enums。枚举类型
持有固定集合的值，这些值被称为枚举的成员（variants）。第六章将介
绍枚举的更多细节。
Result的成员是 Ok和 Err， Ok成员表⽰操作成功，内部包含成功
时产⽣的值。 Err成员则意味着操作失败，并且包含失败的前因后果。
这些 Result类型的作⽤是编码错误处理信息。Result类型的值，像
其他类型⼀样，拥有定义于其上的⽅法。io::Result的实例拥有
expect⽅法。如果 io::Result实例的值是 Err， expect会导致程
序崩溃，并显⽰当做参数传递给 expect的信息。如果 read_line⽅法
返回 Err，则可能是来源于底层操作系统错误的结果。如果
io::Result实例的值是 Ok，expect会获取 Ok中的值并原样返回。
在本例中，这个值是⽤⼾输⼊到标准输⼊中的字节数。
如果不调⽤ expect，程序也能编译，不过会出现⼀个警告：
$ cargo build
   Compiling guessing_game v0.1.0 (file:///projects
/guessing_game)
warning: unused `std::result::Result` which must be used
  --> src/main.rs:10:5
   |
10 |     io::stdin().read_line(&mut guess);
   |     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
   |
   = note: #[warn(unused_must_use)] on by default
Rust 警告我们没有使⽤ read_line的返回值 Result，说明有⼀个可能
的错误没有处理。
消除警告的正确做法是实际编写错误处理代码，不过由于我们就是希望程
序在出现问题时⽴即崩溃，所以直接使⽤ expect。第九章会学习如何从
错误中恢复。
使⽤pprriinnttllnn!!占位符打印值
除了位于结尾的⼤括号，⽬前为⽌就只有这⼀⾏代码值得讨论⼀下了，就
是这⼀⾏：
println!("You guessed: {}", guess);
这⾏代码打印存储⽤⼾输⼊的字符串。第⼀个参数是格式化字符串，⾥⾯
的 {}是预留在特定位置的占位符。使⽤ {}也可以打印多个值：第⼀
对 {}使⽤格式化字符串之后的第⼀个值，第⼆对则使⽤第⼆个值，依此
类推。调⽤⼀次 println!打印多个值看起来像这样：
let x = 5;
let y = 10;
println!("x = {} and y = {}", x, y);
这⾏代码会打印出 x = 5 and y = 10。
测试第⼀部分代码
让我们来测试下猜猜看游戏的第⼀部分。使⽤ cargo run运⾏：
$ cargo run
   Compiling guessing_game v0.1.0 (file:///projects
/guessing_game)
    Finished dev [unoptimized + debuginfo] target(s) in 
2.53 secs
     Running `target/debug/guessing_game`
Guess the number!
Please input your guess.
6
You guessed: 6
⾄此为⽌，游戏的第⼀部分已经完成：我们从键盘获取输⼊并打印了出
来。
⽣成⼀个秘密数字
接下来，需要⽣成⼀个秘密数字，好让⽤⼾来猜。秘密数字应该每次都不
同，这样重复玩才不会乏味；范围应该在 1 到 100 之间，这样才不会太
困难。Rust 标准库中尚未包含随机数功能。然⽽，Rust 团队还是提供了
⼀个 rand crate。
使⽤ crate 来增加更多功能
记住，crate是⼀个 Rust 代码包。我们正在构建的项⽬是⼀个⼆进制
crate，它⽣成⼀个可执⾏⽂件。 rand crate 是⼀个库 crate，库 crate
可以包含任意能被其他程序使⽤的代码。
Cargo 对外部 crate 的运⽤是其真正闪光的地⽅。在我们使⽤ rand编写
代码之前，需要修改 Cargo.toml⽂件，引⼊⼀个 rand依赖。现在打开
这个⽂件并在底部的 [dependencies]⽚段标题之下添加：
⽂件名: Cargo.toml
[dependencies]
rand = "0.5.5"
在 Cargo.toml⽂件中，标题以及之后的内容属同⼀个⽚段，直到遇到下
⼀个标题才开始新的⽚段。[dependencies]⽚段告诉 Cargo 本项⽬依
赖了哪些外部 crate 及其版本。本例中，我们使⽤语义化版本 0.5.5来
指定 rand crate。Cargo 理解语义化版本（Semantic Versioning）（有
时也称为 SemVer），这是⼀种定义版本号的标准。0.5.5事实上是
^0.5.5的简写，它表⽰ “任何与 0.5.5 版本公有 API 相兼容的版本”。
现在，不修改任何代码，构建项⽬，如⽰例 2-2 所⽰：
$ cargo build
    Updating crates.io index
  Downloaded rand v0.5.5
  Downloaded libc v0.2.62
  Downloaded rand_core v0.2.2
  Downloaded rand_core v0.3.1
  Downloaded rand_core v0.4.2
   Compiling rand_core v0.4.2
   Compiling libc v0.2.62
   Compiling rand_core v0.3.1
   Compiling rand_core v0.2.2
   Compiling rand v0.5.5
   Compiling guessing_game v0.1.0 (file:///projects
/guessing_game)
    Finished dev [unoptimized + debuginfo] target(s) in 
2.53 s
⽰例 2-2: 将 rand  crate 添加为依赖之后运⾏ cargo build的输出
可能会出现不同的版本号（多亏了语义化版本，它们与代码是兼容
的！），同时显⽰顺序也可能会有所不同。
现在我们有了⼀个外部依赖，Cargo 从 registry上获取所有包的最新版本
信息，这是⼀份来⾃ Crates.io的数据拷贝。Crates.io 是 Rust ⽣态环境
中的开发者们向他⼈贡献 Rust 开源项⽬的地⽅。
在更新完 registry 后，Cargo 检查 [dependencies]⽚段并下载缺失的
crate 。本例中，虽然只声明了 rand⼀个依赖，然⽽ Cargo 还是额外获
取了 libc和 rand_core的拷贝，因为 rand依赖 libc和
rand_core来正常⼯作。下载完成后，Rust 编译依赖，然后使⽤这些依
赖编译项⽬。
如果不做任何修改，⽴刻再次运⾏ cargo build，则不会看到任何除了
Finished⾏之外的输出。Cargo 知道它已经下载并编译了依赖，同时
Cargo.toml⽂件也没有变动。Cargo 还知道代码也没有任何修改，所以
它不会重新编译代码。因为⽆事可做，它简单的退出了。
如果打开 src/main.rs⽂件，做⼀些⽆关紧要的修改，保存并再次构建，
则会出现两⾏输出：
$ cargo build
   Compiling guessing_game v0.1.0 (file:///projects
/guessing_game)
    Finished dev [unoptimized + debuginfo] target(s) in 
2.53 secs
这⼀⾏表⽰ Cargo 只针对 src/main.rs⽂件的微⼩修改⽽更新构建。依赖
没有变化，所以 Cargo 知道它可以复⽤已经为此下载并编译的代码。它
只是重新构建了部分（项⽬）代码。
Cargo.lock⽂件确保构建是可重现的
Cargo 有⼀个机制来确保任何⼈在任何时候重新构建代码，都会产⽣相同
的结果：Cargo 只会使⽤你指定的依赖版本，除⾮你⼜⼿动指定了别的。
例如，如果下周 rand crate 的 0.5.6版本出来了，它修复了⼀个重要
的 bug，同时也含有⼀个会破坏代码运⾏的缺陷，这时会发⽣什么呢？
这个问题的答案是 Cargo.lock⽂件。它在第⼀次运⾏ cargo build时创
建，并放在 guessing_game⽬录。当第⼀次构建项⽬时，Cargo 计算出所
有符合要求的依赖版本并写⼊ Cargo.lock⽂件。当将来构建项⽬
时，Cargo 会发现 Cargo.lock已存在并使⽤其中指定的版本，⽽不是再
次计算所有的版本。这使得你拥有了⼀个⾃动化的可重现的构建。换句话
说，项⽬会持续使⽤ 0.5.5直到你显式升级，多亏有了 Cargo.lock⽂
件。
更新 crate 到⼀个新版本
当你确实需要升级 crate 时，Cargo 提供了另⼀个命令， update，它会
忽略 Cargo.lock⽂件，并计算出所有符合 Cargo.toml声明的最新版本。
如果成功了，Cargo 会把这些版本写⼊ Cargo.lock⽂件。
不过，Cargo 默认只会寻找⼤于 0.5.5⽽⼩于 0.6.0的版本。如果
rand crate 发布了两个新版本， 0.5.6和 0.6.0，在运⾏ cargo 
update时会出现如下内容：
$ cargo update
    Updating crates.io index
    Updating rand v0.5.5 -> v0.5.6
这时，你也会注意到的 Cargo.lock⽂件中的变化⽆外乎现在使⽤的 rand
crate 版本是 0.5.6
如果想要使⽤ 0.6.0版本的 rand或是任何 0.6.x系列的版本，必须
像这样更新 Cargo.toml⽂件：
[dependencies]
rand = "0.6.0"
下⼀次运⾏ cargo build时，Cargo 会从 registry 更新可⽤的 crate，
并根据你指定的新版本重新计算。
第十四章会讲到 Cargo及其⽣态系统的更多内容，不过⽬前你只需要了
解这么多。通过 Cargo 复⽤库⽂件⾮常容易，因此 Rustacean 能够编写
出由很多包组装⽽成的更轻巧的项⽬。
⽣成⼀个随机数
你已经把 rand crate 添加到 Cargo.toml了，让我们开始使⽤ rand。下
⼀步是更新 src/main.rs，如⽰例 2-3 所⽰。
⽂件名: src/main.rs
use std::io;
use rand::Rng;
fn main() {
println!("Guess the number!");
let secret_number = rand::thread_rng().gen_range(1, 
101);
println!("The secret number is: {}", secret_number);
println!("Please input your guess.");
let mut guess = String::new();
    io::stdin().read_line(&mut guess)
        .expect("Failed to read line");
println!("You guessed: {}", guess);
}
⽰例 2-3：添加⽣成随机数的代码
首先，我们新增了⼀⾏ use：use rand::Rng。Rng是⼀个 trait，它
定义了随机数⽣成器应实现的⽅法，想使⽤这些⽅法的话，此 trait 必须
在作⽤域中。第十章会详细介绍 trait。
接下来，我们在中间还新增加了两⾏。rand::thread_rng函数提供实
际使⽤的随机数⽣成器：它位于当前执⾏线程的本地环境中，并从操作系
统获取 seed。接下来，调⽤随机数⽣成器的 gen_range⽅法。这个⽅
法由刚才引⼊到作⽤域的 Rng trait 定义。 gen_range⽅法获取两个数
字作为参数，并⽣成⼀个范围在两者之间的随机数。它包含下限但不包含
上限，所以需要指定 1和 101来请求⼀个 1 和 100 之间的数。
注意：你不可能凭空就知道应该 use 哪个 trait 以及该从 crate 中调
⽤哪个⽅法。crate 的使⽤说明位于其⽂档中。Cargo 有⼀个很棒的
功能是：运⾏ cargo doc --open命令来构建所有本地依赖提供的
⽂档，并在浏览器中打开。例如，假设你对 rand crate 中的其他
功能感兴趣，你可以运⾏ cargo doc --open并点击左侧导航栏中
的 rand。
新增加的第⼆⾏代码打印出了秘密数字。这在开发程序时很有⽤，因为可
以测试它，不过在最终版本中会删掉它。如果游戏⼀开始就打印出结果就
没什么可玩的了！
尝试运⾏程序⼏次：
$ cargo run
   Compiling guessing_game v0.1.0 (file:///projects
/guessing_game)
    Finished dev [unoptimized + debuginfo] target(s) in 
2.53 secs
     Running `target/debug/guessing_game`
Guess the number!
The secret number is: 7
Please input your guess.
4
You guessed: 4
$ cargo run
     Running `target/debug/guessing_game`
Guess the number!
The secret number is: 83
Please input your guess.
5
You guessed: 5
你应该能得到不同的随机数，同时它们应该都是在 1 和 100 之间的。⼲
得漂亮！
⽐较猜测的数字和秘密数字
现在有了⽤⼾输⼊和⼀个随机数，我们可以⽐较它们。这个步骤如⽰例
2-4 所⽰。注意这段代码还不能通过编译，我们稍后会解释。
⽂件名: src/main.rs
use std::io;
use std::cmp::Ordering;
use rand::Rng;
fn main() {
// ---snip---
println!("You guessed: {}", guess);
match guess.cmp(&secret_number) {
        Ordering::Less => println!("Too small!"),
        Ordering::Greater => println!("Too big!"),
        Ordering::Equal => println!("You win!"),
    }
}
⽰例 2-4：处理⽐较两个数字可能的返回值
新代码的第⼀⾏是另⼀个 use，从标准库引⼊了⼀个叫做
std::cmp::Ordering的类型。同 Result⼀样， Ordering也是⼀个
枚举，不过它的成员是 Less、Greater和 Equal。这是⽐较两个值时
可能出现的三种结果。
接着，底部的五⾏新代码使⽤了 Ordering类型， cmp⽅法⽤来⽐较两
个值并可以在任何可⽐较的值上调⽤。它获取⼀个被⽐较值的引⽤：这⾥
是把 guess与 secret_number做⽐较。然后它会返回⼀个刚才通过
use引⼊作⽤域的 Ordering枚举的成员。使⽤⼀个 match表达式，
根据对 guess和 secret_number调⽤ cmp返回的 Ordering成员来
决定接下来做什么。
⼀个 match表达式由分⽀（arms）构成。⼀个分⽀包含⼀个模式
（pattern）和表达式开头的值与分⽀模式相匹配时应该执⾏的代码。
Rust 获取提供给 match的值并挨个检查每个分⽀的模式。match结构
和模式是 Rust 中强⼤的功能，它体现了代码可能遇到的多种情形，并帮
助你确保没有遗漏处理。这些功能将分别在第六章和第十⼋章详细介绍。
让我们看看使⽤ match表达式的例⼦。假设⽤⼾猜了 50，这时随机⽣成
的秘密数字是 38。⽐较 50 与 38 时，因为 50 ⽐ 38 要⼤， cmp⽅法会
返回 Ordering::Greater。 Ordering::Greater是 match表达式得到
的值。它检查第⼀个分⽀的模式，Ordering::Less与
Ordering::Greater并不匹配，所以它忽略了这个分⽀的代码并来到下
⼀个分⽀。下⼀个分⽀的模式是 Ordering::Greater，正确匹配！这个
分⽀关联的代码被执⾏，在屏幕打印出 Too big!。match表达式就此
终⽌，因为该场景下没有检查最后⼀个分⽀的必要。
然⽽，⽰例 2-4 的代码并不能编译，可以尝试⼀下：
$ cargo build
   Compiling guessing_game v0.1.0 (file:///projects
/guessing_game)
error[E0308]: mismatched types
  --> src/main.rs:23:21
   |
23 |     match guess.cmp(&secret_number) {
   |                     ^^^^^^^^^^^^^^ expected struct 
`std::string::String`, found integer
   |
   = note: expected type `&std::string::String`
   = note:    found type `&{integer}`
error: aborting due to previous error
Could not compile `guessing_game`.
错误的核心表明这⾥有不匹配的类型（mismatched types）。Rust 有⼀
个静态强类型系统，同时也有类型推断。当我们写出 let guess = 
String::new()时，Rust 推断出 guess应该是 String类型，并不需
要我们写出类型。另⼀⽅⾯，secret_number，是数字类型。⼏个数字
类型拥有 1 到 100 之间的值：32 位数字 i32；32 位⽆符号数字
u32；64 位数字 i64等等。Rust 默认使⽤ i32，所以它是
secret_number的类型，除⾮增加类型信息，或任何能让 Rust 推断出
不同数值类型的信息。这⾥错误的原因在于 Rust 不会⽐较字符串类型和
数字类型。
所以我们必须把从输⼊中读取到的 String转换为⼀个真正的数字类
型，才好与秘密数字进⾏⽐较。这可以通过在 main函数体中增加如下
两⾏代码来实现：
⽂件名: src/main.rs
// --snip--
let mut guess = String::new();
    io::stdin().read_line(&mut guess)
        .expect("Failed to read line");
let guess: u32 = guess.trim().parse()
        .expect("Please type a number!");
println!("You guessed: {}", guess);
match guess.cmp(&secret_number) {
        Ordering::Less => println!("Too small!"),
        Ordering::Greater => println!("Too big!"),
        Ordering::Equal => println!("You win!"),
    }
}
这两⾏新代码是：
let guess: u32 = guess.trim().parse()
    .expect("Please type a number!");
这⾥创建了⼀个叫做 guess的变量。不过等等，不是已经有了⼀个叫做
guess的变量了吗？确实如此，不过 Rust 允许⽤⼀个新值来隐藏
（shadow） guess之前的值。这个功能常⽤在需要转换值类型之类的场
景。它允许我们复⽤ guess变量的名字，⽽不是被迫创建两个不同变
量，诸如 guess_str和 guess之类。（第三章会介绍 shadowing 的更
多细节。）
我们将 guess绑定到 guess.trim().parse()表达式上。表达式中的
guess是包含输⼊的原始 String类型。 String实例的 trim⽅法会
去除字符串开头和结尾的空⽩字符。u32只能由数字字符转换，不过⽤
⼾必须输⼊ enter键才能让 read_line返回，然⽽⽤⼾按下 enter键
时，会在字符串中增加⼀个换⾏（newline）符。例如，⽤⼾输⼊ 5并按
下 enter，guess看起来像这样：5\n。\n代表 “换⾏”，回车键。
trim⽅法消除 \n，只留下 5。
字符串的 parse⽅法将字符串解析成数字。因为这个⽅法可以解析多种
数字类型，因此需要告诉 Rust 具体的数字类型，这⾥通过 let guess: 
u32指定。guess后⾯的冒号（ :）告诉 Rust 我们指定了变量的类
型。Rust 有⼀些内建的数字类型； u32是⼀个⽆符号的 32 位整型。对
于不⼤的正整数来说，它是不错的类型，第三章还会讲到其他数字类型。
另外，程序中的 u32注解以及与 secret_number的⽐较，意味着 Rust
会推断出 secret_number也是 u32类型。现在可以使⽤相同类型⽐较
两个值了！
parse调⽤很容易产⽣错误。例如，字符串中包含 A%👍，就⽆法将其
转换为⼀个数字。因此，parse⽅法返回⼀个 Result类型。像之前
“使⽤ Result类型来处理潜在的错误”讨论的 read_line⽅法那样，再
次按部就班的⽤ expect⽅法处理即可。如果 parse不能从字符串⽣成
⼀个数字，返回⼀个 Result的 Err成员时，expect会使游戏崩溃并
打印附带的信息。如果 parse成功地将字符串转换为⼀个数字，它会返
回 Result的 Ok成员，然后 expect会返回 Ok值中的数字。
现在让我们运⾏程序！
$ cargo run
   Compiling guessing_game v0.1.0 (file:///projects
/guessing_game)
    Finished dev [unoptimized + debuginfo] target(s) in 
0.43 secs
     Running `target/debug/guessing_game`
Guess the number!
The secret number is: 58
Please input your guess.
  76
You guessed: 76
Too big!
漂亮！即便是在猜测之前添加了空格，程序依然能判断出⽤⼾猜测了
76。多运⾏程序⼏次，输⼊不同的数字来检验不同的⾏为：猜⼀个正确
的数字，猜⼀个过⼤的数字和猜⼀个过⼩的数字。
现在游戏已经⼤体上能玩了，不过⽤⼾只能猜⼀次。增加⼀个循环来改变
它吧！
使⽤循环来允许多次猜测
loop关键字创建了⼀个⽆限循环。将其加⼊后，⽤⼾可以反复猜测：
⽂件名: src/main.rs
// --snip--
println!("The secret number is: {}", secret_number);
loop {
println!("Please input your guess.");
// --snip--
match guess.cmp(&secret_number) {
            Ordering::Less => println!("Too small!"),
            Ordering::Greater => println!("Too big!"),
            Ordering::Equal => println!("You win!"),
        }
    }
}
如上所⽰，我们将提⽰⽤⼾猜测之后的所有内容放⼊了循环。确保 loop
循环中的代码多缩进四个空格，再次运⾏程序。注意这⾥有⼀个新问题，
因为程序忠实地执⾏了我们的要求：永远地请求另⼀个猜测，⽤⼾好像⽆
法退出啊！
⽤⼾总能使⽤ ctrl-c终⽌程序。不过还有另⼀个⽅法跳出⽆限循环，就是
“⽐较猜测与秘密数字”部分提到的 parse：如果⽤⼾输⼊的答案不是⼀
个数字，程序会崩溃。⽤⼾可以利⽤这⼀点来退出，如下所⽰：
$ cargo run
   Compiling guessing_game v0.1.0 (file:///projects
/guessing_game)
    Finished dev [unoptimized + debuginfo] target(s) in 
1.50 secs
     Running `target/debug/guessing_game`
Guess the number!
The secret number is: 59
Please input your guess.
45
You guessed: 45
Too small!
Please input your guess.
60
You guessed: 60
Too big!
Please input your guess.
59
You guessed: 59
You win!
Please input your guess.
quit
thread 'main' panicked at 'Please type a number!: 
ParseIntError { kind: InvalidDigit }', src/libcore
/result.rs:785
note: Run with `RUST_BACKTRACE=1` for a backtrace.
error: Process didn't exit successfully: `target/debug
/guess` (exit code: 101)
输⼊ quit确实退出了程序，同时其他任何⾮数字输⼊也⼀样。然⽽，
这并不理想，我们想要当猜测正确的数字时游戏能⾃动退出。
猜测正确后退出
让我们增加⼀个 break语句，在⽤⼾猜对时退出游戏：
⽂件名: src/main.rs
// --snip--
match guess.cmp(&secret_number) {
            Ordering::Less => println!("Too small!"),
            Ordering::Greater => println!("Too big!"),
            Ordering::Equal => {
println!("You win!");
break;
            }
        }
    }
}
通过在 You win!之后增加⼀⾏ break，⽤⼾猜对了神秘数字后会退出
循环。退出循环也意味着退出程序，因为循环是 main的最后⼀部分。
处理⽆效输⼊
为了进⼀步改善游戏性，不要在⽤⼾输⼊⾮数字时崩溃，需要忽略⾮数
字，让⽤⼾可以继续猜测。可以通过修改 guess将 String转化为
u32那部分代码来实现，如⽰例 2-5 所⽰：
⽂件名: src/main.rs
// --snip--
io::stdin().read_line(&mut guess)
    .expect("Failed to read line");
let guess: u32 = match guess.trim().parse() {
Ok(num) => num,
Err(_) => continue,
};
println!("You guessed: {}", guess);
// --snip--
⽰例 2-5: 忽略⾮数字的猜测并重新请求数字⽽不是让程序崩溃
将 expect调⽤换成 match语句，是从遇到错误就崩溃转换到真正处理
错误的惯⽤⽅法。须知 parse返回⼀个 Result类型，⽽ Result是⼀
个拥有 Ok或 Err成员的枚举。这⾥使⽤的 match表达式，和之前处
理 cmp⽅法返回 Ordering时⽤的⼀样。
如果 parse能够成功的将字符串转换为⼀个数字，它会返回⼀个包含结
果数字的 Ok。这个 Ok值与 match第⼀个分⽀的模式相匹配，该分⽀
对应的动作返回 Ok值中的数字 num，最后如愿变成新创建的 guess变
量。
如果 parse不能将字符串转换为⼀个数字，它会返回⼀个包含更多错误
信息的 Err。 Err值不能匹配第⼀个 match分⽀的 Ok(num)模式，但
是会匹配第⼆个分⽀的 Err(_)模式： _是⼀个通配符值，本例中⽤来
匹配所有 Err值，不管其中有何种信息。所以程序会执⾏第⼆个分⽀的
动作，continue意味着进⼊ loop的下⼀次循环，请求另⼀个猜测。
这样程序就有效的忽略了 parse可能遇到的所有错误！
现在万事俱备，只需运⾏ cargo run：
$ cargo run
   Compiling guessing_game v0.1.0 (file:///projects
/guessing_game)
     Running `target/debug/guessing_game`
Guess the number!
The secret number is: 61
Please input your guess.
10
You guessed: 10
Too small!
Please input your guess.
99
You guessed: 99
Too big!
Please input your guess.
foo
Please input your guess.
61
You guessed: 61
You win!
太棒了！再有最后⼀个⼩的修改，就能完成猜猜看游戏了：还记得程序依
然会打印出秘密数字。在测试时还好，但正式发布时会毁了游戏。删掉打
印秘密数字的 println!。⽰例 2-6 为最终代码：
⽂件名: src/main.rs
use std::io;
use std::cmp::Ordering;
use rand::Rng;
fn main() {
println!("Guess the number!");
let secret_number = rand::thread_rng().gen_range(1, 
101);
loop {
println!("Please input your guess.");
let mut guess = String::new();
        io::stdin().read_line(&mut guess)
            .expect("Failed to read line");
let guess: u32 = match guess.trim().parse() {
Ok(num) => num,
Err(_) => continue,
        };
println!("You guessed: {}", guess);
match guess.cmp(&secret_number) {
            Ordering::Less => println!("Too small!"),
            Ordering::Greater => println!("Too big!"),
            Ordering::Equal => {
println!("You win!");
break;
            }
        }
    }
}
⽰例 2-6：猜猜看游戏的完整代码
总结
此时此刻，你顺利完成了猜猜看游戏。恭喜！
本项⽬通过动⼿实践，向你介绍了 Rust 新概念： let、match、⽅法、
关联函数、使⽤外部 crate 等等，接下来的⼏章，你会继续深⼊学习这些
概念。第三章介绍⼤部分编程语⾔都有的概念，⽐如变量、数据类型和函
数，以及如何在 Rust 中使⽤它们。第四章探索所有权（ownership），
这是⼀个 Rust 同其他语⾔⼤不相同的功能。第五章讨论结构体和⽅法的
语法，⽽第六章侧重解释枚举。
常⻅编程概念
ch03-00-common-programming-concepts.md
commit 1f49356cb21cbc27bc5359bfe655d26757d4b137
本章介绍⼀些⼏乎所有编程语⾔都有的概念，以及它们在 Rust 中是如何
⼯作的。很多编程语⾔的核心概念都是共通的，本章中展⽰的概念都不是
Rust 所特有的，不过我们会在 Rust 上下⽂中讨论它们，并解释使⽤这些
概念的惯例。
具体来说，我们将会学习变量、基本类型、函数、注释和控制流。每⼀个
Rust 程序中都会⽤到这些基础知识，提早学习这些概念会让你在起步时
就打下坚实的基础。
关键字
Rust 语⾔有⼀组保留的关键字（keywords），就像⼤部分语⾔⼀
样，它们只能由语⾔本⾝使⽤。记住，你不能使⽤这些关键字作为
变量或函数的名称。⼤部分关键字有特殊的意义，你将在 Rust 程序
中使⽤它们完成各种任务；⼀些关键字⽬前没有相应的功能，是为
将来可能添加的功能保留的。可以在附录 A 中找到关键字的列表。
变量和可变性
ch03-01-variables-and-mutability.md
commit d69b1058c660abfe1d274c58d39c06ebd5c96c47
第⼆章中提到过，变量默认是不可改变的（immutable）。这是推动你以
充分利⽤ Rust 提供的安全性和简单并发性来编写代码的众多⽅式之⼀。
不过，你仍然可以使⽤可变变量。让我们探讨⼀下 Rust 为何及如何⿎励
你利⽤不可变性，以及何时你会选择不使⽤不可变性。
当变量不可变时，⼀旦值被绑定⼀个名称上，你就不能改变这个值。为了
对此进⾏说明，使⽤ cargo new variables命令在 projects⽬录⽣成⼀
个叫做 variables的新项⽬。
接着，在新建的 variables⽬录，打开 src/main.rs并将代码替换为如下代
码，这些代码还不能编译：
⽂件名: src/main.rs
fn main() {
let x = 5;
println!("The value of x is: {}", x);
    x = 6;
println!("The value of x is: {}", x);
}
保存并使⽤ cargo run运⾏程序。应该会看到⼀条错误信息，如下输出
所⽰：
error[E0384]: cannot assign twice to immutable variable `x`
 --> src/main.rs:4:5
  |
2 |     let x = 5;
  |         - first assignment to `x`
3 |     println!("The value of x is: {}", x);
4 |     x = 6;
  |     ^^^^^ cannot assign twice to immutable variable
这个例⼦展⽰了编译器如何帮助你找出程序中的错误。虽然编译错误令⼈
沮丧，但那只是表⽰程序不能安全的完成你想让它完成的⼯作；并不能
说明你不是⼀个好程序员！经验丰富的 Rustacean 们⼀样会遇到编译错
误。
错误信息指出错误的原因是不能对不可变变量 x ⼆次赋值（cannot 
assign twice to immutable variable x），因为你尝试对不可变变
量 x赋第⼆个值。
在尝试改变预设为不可变的值时，产⽣编译时错误是很重要的，因为这种
情况可能导致 bug。如果⼀部分代码假设⼀个值永远也不会改变，⽽另⼀
部分代码改变了这个值，第⼀部分代码就有可能以不可预料的⽅式运⾏。
不得不承认这种 bug 的起因难以跟踪，尤其是第⼆部分代码只是有时会
改变值。
Rust 编译器保证，如果声明⼀个值不会变，它就真的不会变。这意味着
当阅读和编写代码时，不需要追踪⼀个值如何和在哪可能会被改变，从⽽
使得代码易于推导。
不过可变性也是⾮常有⽤的。变量只是默认不可变；正如在第⼆章所做的
那样，你可以在变量名之前加 mut来使其可变。除了允许改变值之
外，mut向读者表明了其他代码将会改变这个变量值的意图。
例如，让我们将 src/main.rs修改为如下代码：
⽂件名: src/main.rs
fn main() {
let mut x = 5;
println!("The value of x is: {}", x);
    x = 6;
println!("The value of x is: {}", x);
}
现在运⾏这个程序，出现如下内容：
$ cargo run
   Compiling variables v0.1.0 (file:///projects/variables)
    Finished dev [unoptimized + debuginfo] target(s) in 
0.30 secs
     Running `target/debug/variables`
The value of x is: 5
The value of x is: 6
通过 mut，允许把绑定到 x的值从 5改成 6。在⼀些情况下，你会想
⽤可变变量，因为与只⽤不可变变量相⽐，它会让代码更容易编写。
除了防⽌出现 bug 外，还有很多地⽅需要权衡取舍。例如，使⽤⼤型数
据结构时，适当地使⽤可变变量，可能⽐复制和返回新分配的实例更快。
对于较⼩的数据结构，总是创建新实例，采⽤更偏向函数式的编程风格，
可能会使代码更易理解，为可读性⽽牺牲性能或许是值得的。
变量和常量的区别
不允许改变值的变量，可能会使你想起另⼀个⼤部分编程语⾔都有的概
念：常量（constants）。类似于不可变变量，常量是绑定到⼀个名称的
不允许改变的值，不过常量与变量还是有⼀些区别。
首先，不允许对常量使⽤ mut。常量不光默认不能变，它总是不能变。
声明常量使⽤ const关键字⽽不是 let，并且必须注明值的类型。在
下⼀部分，“数据类型”中会介绍类型和类型注解，现在⽆需关心这些细
节，记住总是标注类型即可。
常量可以在任何作⽤域中声明，包括全局作⽤域，这在⼀个值需要被很多
部分的代码⽤到时很有⽤。
最后⼀个区别是，常量只能被设置为常量表达式，⽽不能是函数调⽤的结
果，或任何其他只能在运⾏时计算出的值。
这是⼀个声明常量的例⼦，它的名称是 MAX_POINTS，值是 100,000。
（Rust 常量的命名规范是使⽤下划线分隔的⼤写字⺟单词，并且可以在
数字字⾯值中插⼊下划线来提升可读性）：
const MAX_POINTS: u32 = 100_000;
在声明它的作⽤域之中，常量在整个程序⽣命周期中都有效，这使得常量
可以作为多处代码使⽤的全局范围的值，例如⼀个游戏中所有玩家可以获
取的最⾼分或者光速。
将遍布于应⽤程序中的硬编码值声明为常量，能帮助后来的代码维护⼈员
了解值的意图。如果将来需要修改硬编码值，也只需修改汇聚于⼀处的硬
编码值。
隐藏（Shadowing）
正如在第⼆章猜猜看游戏的 “⽐较猜测的数字和秘密数字”中所讲，我们
可以定义⼀个与之前变量同名的新变量，⽽新变量会隐藏之前的变量。
Rustacean 们称之为第⼀个变量被第⼆个隐藏了，这意味着使⽤这个变
量时会看到第⼆个值。可以⽤相同变量名称来隐藏⼀个变量，以及重复使
⽤ let关键字来多次隐藏，如下所⽰：
⽂件名: src/main.rs
fn main() {
let x = 5;
let x = x + 1;
let x = x * 2;
println!("The value of x is: {}", x);
}
这个程序首先将 x绑定到值 5上。接着通过 let x =隐藏 x，获取
初始值并加 1，这样 x的值就变成 6了。第三个 let语句也隐藏了
x，将之前的值乘以 2，x最终的值是 12。运⾏这个程序，它会有如
下输出：
$ cargo run
   Compiling variables v0.1.0 (file:///projects/variables)
    Finished dev [unoptimized + debuginfo] target(s) in 
0.31 secs
     Running `target/debug/variables`
The value of x is: 12
隐藏与将变量标记为 mut是有区别的。当不⼩心尝试对变量重新赋值
时，如果没有使⽤ let关键字，就会导致编译时错误。通过使⽤ let，
我们可以⽤这个值进⾏⼀些计算，不过计算完之后变量仍然是不变的。
mut与隐藏的另⼀个区别是，当再次使⽤ let时，实际上创建了⼀个新
变量，我们可以改变值的类型，但复⽤这个名字。例如，假设程序请求⽤
⼾输⼊空格字符来说明希望在⽂本之间显⽰多少个空格，然⽽我们真正需
要的是将输⼊存储成数字（多少个空格）：
let spaces = "   ";
let spaces = spaces.len();
这⾥允许第⼀个 spaces变量是字符串类型，⽽第⼆个 spaces变量，
它是⼀个恰巧与第⼀个变量同名的崭新变量，是数字类型。隐藏使我们不
必使⽤不同的名字，如 spaces_str和 spaces_num；相反，我们可以
复⽤ spaces这个更简单的名字。然⽽，如果尝试使⽤ mut，将会得到
⼀个编译时错误，如下所⽰：
let mut spaces = "   ";
spaces = spaces.len();
这个错误说明，我们不能改变变量的类型：
error[E0308]: mismatched types
 --> src/main.rs:3:14
  |
3 |     spaces = spaces.len();
  |              ^^^^^^^^^^^^ expected &str, found usize
  |
  = note: expected type `&str`
             found type `usize`
现在我们已经了解了变量如何⼯作，让我们看看变量可以拥有的更多数据
类型。
数据类型
ch03-02-data-types.md
commit 6598d3abac05ed1d0c45db92466ea49346d05e40
在 Rust 中，每⼀个值都属于某⼀个数据类型（data type），这告诉
Rust 它被指定为何种数据，以便明确数据处理⽅式。我们将看到两类数
据类型⼦集：标量（scalar）和复合（compound）。
记住，Rust 是静态类型（statically typed）语⾔，也就是说在编译时就
必须知道所有变量的类型。根据值及其使⽤⽅式，编译器通常可以推断出
我们想要⽤的类型。当多种类型均有可能时，⽐如第⼆章的 “⽐较猜测的
数字和秘密数字”使⽤ parse将 String转换为数字时，必须增加类型
注解，像这样：
let guess: u32 = "42".parse().expect("Not a number!");
这⾥如果不添加类型注解，Rust 会显⽰如下错误，这说明编译器需要我
们提供更多信息，来了解我们想要的类型：
error[E0282]: type annotations needed
 --> src/main.rs:2:9
  |
2 |     let guess = "42".parse().expect("Not a number!");
  |         ^^^^^
  |         |
  |         cannot infer type for `_`
  |         consider giving `guess` a type
你会看到其它数据类型的各种类型注解。
标量类型
标量（scalar）类型代表⼀个单独的值。Rust 有四种基本的标量类型：整
型、浮点型、布尔类型和字符类型。你可能在其他语⾔中见过它们。让我
们深⼊了解它们在 Rust 中是如何⼯作的。
整型
整数是⼀个没有⼩数部分的数字。我们在第⼆章使⽤过 u32整数类型。
该类型声明表明，它关联的值应该是⼀个占据 32 ⽐特位的⽆符号整数
（有符号整数类型以 i开头⽽不是 u）。表格 3-1 展⽰了 Rust 内建的
整数类型。在有符号列和⽆符号列中的每⼀个变体（例如，i16）都可以
⽤来声明整数值的类型。
表格 3-1: Rust 中的整型
长度有符号⽆符号
8-bit i8 u8
16-bit i16 u16
32-bit i32 u32
64-bit i64 u64
128-bit i128 u128
arch isize usize
每⼀个变体都可以是有符号或⽆符号的，并有⼀个明确的⼤⼩。有符号
和⽆符号代表数字能否为负值，换句话说，数字是否需要有⼀个符号
（有符号数），或者永远为正⽽不需要符号（⽆符号数）。这有点像在纸
上书写数字：当需要考虑符号的时候，数字以加号或减号作为前缀；然
⽽，可以安全地假设为正数时，加号前缀通常省略。有符号数以补码形式
（two’s complement representation）存储。
n - 1 n - 1
每⼀个有符号的变体可以储存包含从 -(2 ) 到 2 - 1 在内的数字，这
7 7
⾥ n是变体使⽤的位数。所以 i8可以储存从 -(2 ) 到 2 - 1 在内的数
n
字，也就是从 -128 到 127。⽆符号的变体可以储存从 0 到 2 - 1 的数
8
字，所以 u8可以储存从 0 到 2 - 1 的数字，也就是从 0 到 255。
另外，isize和 usize类型依赖运⾏程序的计算机架构：64 位架构上
它们是 64 位的， 32 位架构上它们是 32 位的。
可以使⽤表格 3-2 中的任何⼀种形式编写数字字⾯值。注意除 byte 以外
的所有数字字⾯值允许使⽤类型后缀，例如 57u8，同时也允许使⽤ _
做为分隔符以⽅便读数，例如1_000。
表格 3-2: Rust 中的整型字⾯值
数字字⾯值例⼦
Decimal (十进制) 98_222
0xff
Hex (十六进制)
Octal (⼋进制) 0o77
0b1111_0000
Binary (⼆进制)
Byte (单字节字符)(仅限于 u8 ) b'A'
那么该使⽤哪种类型的数字呢？如果拿不定主意，Rust 的默认类型通常
就很好，数字类型默认是 i32：它通常是最快的，甚⾄在 64 位系统上也
是。isize或 usize主要作为某些集合的索引。
整型溢出
⽐⽅说有⼀个 u8，它可以存放从零到 255的值。那么当你将其
修改为 256时会发⽣什么呢？这被称为 “整型溢出”（“integer
overﬂow” ），关于这⼀⾏为 Rust 有⼀些有趣的规则。当在 debug
模式编译时，Rust 检查这类问题并使程序 panic，这个术语被 Rust
⽤来表明程序因错误⽽退出。第九章 “panic!与不可恢复的错误”
部分会详细介绍 panic。
在 release 构建中，Rust 不检测溢出，相反会进⾏⼀种被称为⼆进
制补码包装（two’s complement wrapping）的操作。简⽽⾔
之，256变成 0， 257变成 1，依此类推。依赖整型溢出被认为
是⼀种错误，即便可能出现这种⾏为。如果你确实需要这种⾏为，
标准库中有⼀个类型显式提供此功能，Wrapping。
浮点型
Rust 也有两个原⽣的浮点数（ﬂoating-point numbers）类型，它们是带
⼩数点的数字。Rust 的浮点数类型是 f32和 f64，分别占 32 位和 64
位。默认类型是 f64，因为在现代 CPU 中，它与 f32速度⼏乎⼀样，
不过精度更⾼。
这是⼀个展⽰浮点数的实例：
⽂件名: src/main.rs
fn main() {
let x = 2.0; // f64
let y: f32 = 3.0; // f32
}
浮点数采⽤ IEEE-754 标准表⽰。 f32是单精度浮点数， f64是双精度
浮点数。
数值运算
Rust 中的所有数字类型都⽀持基本数学运算：加法、减法、乘法、除法
和取余。下⾯的代码展⽰了如何在 let语句中使⽤它们：
⽂件名: src/main.rs
fn main() {
// 加法
let sum = 5 + 10;
// 减法
let difference = 95.5 - 4.3;
// 乘法
let product = 4 * 30;
// 除法
let quotient = 56.7 / 32.2;
// 取余
let remainder = 43 % 5;
}
这些语句中的每个表达式使⽤了⼀个数学运算符并计算出了⼀个值，然后
绑定给⼀个变量。附录 B 包含 Rust 提供的所有运算符的列表。
布尔型
正如其他⼤部分编程语⾔⼀样，Rust 中的布尔类型有两个可能的
值：true和 false。Rust 中的布尔类型使⽤ bool表⽰。例如：
⽂件名: src/main.rs
fn main() {
let t = true;
let f: bool = false; // 显式指定类型注解
}
使⽤布尔值的主要场景是条件表达式，例如 if表达式。在 “控制流”
（“Control Flow”）部分将介绍 if表达式在 Rust 中如何⼯作。
字符类型
⽬前为⽌只使⽤到了数字，不过 Rust 也⽀持字⺟。Rust 的 char类型是
语⾔中最原⽣的字⺟类型，如下代码展⽰了如何使⽤它。（注意 char
由单引号指定，不同于字符串使⽤双引号。）
⽂件名: src/main.rs
fn main() {
let c = 'z';
let z = 'ℤ';
let heart_eyed_cat = '';😻
}
Rust 的 char类型的⼤⼩为四个字节(four bytes)，并代表了⼀个
Unicode 标量值（Unicode Scalar Value），这意味着它可以⽐ ASCII 表
⽰更多内容。在 Rust 中，拼⾳字⺟（Accented letters），中⽂、⽇⽂、
韩⽂等字符，emoji（绘⽂字）以及零⻓度的空⽩字符都是有效的 char
值。Unicode 标量值包含从 U+0000到 U+D7FF和 U+E000到
U+10FFFF在内的值。不过，“字符” 并不是⼀个 Unicode 中的概念，所
以⼈直觉上的 “字符” 可能与 Rust 中的 char并不符合。第⼋章的 “使⽤
字符串存储 UTF-8 编码的⽂本”中将详细讨论这个主题。
复合类型
复合类型（Compound types）可以将多个值组合成⼀个类型。Rust 有两
个原⽣的复合类型：元组（tuple）和数组（array）。
元组类型
元组是⼀个将多个其他类型的值组合进⼀个复合类型的主要⽅式。元组⻓
度固定：⼀旦声明，其⻓度不会增⼤或缩⼩。
我们使⽤包含在圆括号中的逗号分隔的值列表来创建⼀个元组。元组中的
每⼀个位置都有⼀个类型，⽽且这些不同值的类型也不必是相同的。这个
例⼦中使⽤了可选的类型注解：
⽂件名: src/main.rs
fn main() {
let tup: (i32, f64, u8) = (500, 6.4, 1);
}
tup变量绑定到整个元组上，因为元组是⼀个单独的复合元素。为了从
元组中获取单个值，可以使⽤模式匹配（pattern matching）来解构
（destructure）元组值，像这样：
⽂件名: src/main.rs
fn main() {
let tup = (500, 6.4, 1);
let (x, y, z) = tup;
println!("The value of y is: {}", y);
}
程序首先创建了⼀个元组并绑定到 tup变量上。接着使⽤了 let和⼀
个模式将 tup分成了三个不同的变量， x、y和 z。这叫做解构
（destructuring），因为它将⼀个元组拆成了三个部分。最后，程序打印
出了 y的值，也就是 6.4。
除了使⽤模式匹配解构外，也可以使⽤点号（.）后跟值的索引来直接访
问它们。例如：
⽂件名: src/main.rs
fn main() {
let x: (i32, f64, u8) = (500, 6.4, 1);
let five_hundred = x.0;
let six_point_four = x.1;
let one = x.2;
}
这个程序创建了⼀个元组，x，并接着使⽤索引为每个元素创建新变量。
跟⼤多数编程语⾔⼀样，元组的第⼀个索引值是 0。
数组类型
另⼀个包含多个值的⽅式是数组（array）。与元组不同，数组中的每个
元素的类型必须相同。Rust 中的数组与⼀些其他语⾔中的数组不同，因
为 Rust 中的数组是固定⻓度的：⼀旦声明，它们的⻓度不能增⻓或缩
⼩。
Rust 中，数组中的值位于中括号内的逗号分隔的列表中：
⽂件名: src/main.rs
fn main() {
let a = [1, 2, 3, 4, 5];
}
当你想要在栈（stack）⽽不是在堆（heap）上为数据分配空间（第四章
将讨论栈与堆的更多内容），或者是想要确保总是有固定数量的元素时，
数组⾮常有⽤。但是数组并不如 vector 类型灵活。vector 类型是标准库
提供的⼀个允许增⻓和缩⼩⻓度的类似数组的集合类型。当不确定是应
该使⽤数组还是 vector 的时候，你可能应该使⽤ vector。第⼋章会详细
讨论 vector。
⼀个你可能想要使⽤数组⽽不是 vector 的例⼦是，当程序需要知道⼀年
中⽉份的名字时。程序不⼤可能会去增加或减少⽉份。这时你可以使⽤数
组，因为我们知道它总是包含 12 个元素：
let months = ["January", "February", "March", "April", 
"May", "June", "July",
"August", "September", "October", "November", 
"December"];
可以像这样编写数组的类型：在⽅括号中包含每个元素的类型，后跟分
号，再后跟数组元素的数量。
let a: [i32; 5] = [1, 2, 3, 4, 5];
这⾥，i32是每个元素的类型。分号之后，数字 5表明该数组包含五个
元素。
以这种⽅式编写数组的类型看起来类似于初始化数组的另⼀种语法：如果
要为每个元素创建包含相同值的数组，可以指定初始值，后跟分号，然后
在⽅括号中指定数组的⻓度，如下所⽰：
let a = [3; 5];
变量名为 a的数组将包含 5个元素，这些元素的值最初都将被设置为
3。这种写法与 let a = [3, 3, 3, 3, 3];效果相同，但更简洁。
访问数组元素
数组是⼀整块分配在栈上的内存。可以使⽤索引来访问数组的元素，像这
样：
⽂件名: src/main.rs
fn main() {
let a = [1, 2, 3, 4, 5];
let first = a[0];
let second = a[1];
}
在这个例⼦中，叫做 first的变量的值是 1，因为它是数组索引 [0]
的值。变量 second将会是数组索引 [1]的值 2。
⽆效的数组元素访问
如果我们访问数组结尾之后的元素会发⽣什么呢？⽐如你将上⾯的例⼦改
成下⾯这样，这可以编译通过，不过在运⾏时会因错误⽽退出：
⽂件名: src/main.rs
fn main() {
let a = [1, 2, 3, 4, 5];
let index = 10;
let element = a[index];
println!("The value of element is: {}", element);
}
使⽤ cargo run运⾏代码后会产⽣如下结果：
$ cargo run
   Compiling arrays v0.1.0 (file:///projects/arrays)
    Finished dev [unoptimized + debuginfo] target(s) in 
0.31 secs
     Running `target/debug/arrays`
thread 'main' panicked at 'index out of bounds: the len is 
5 but the index is
 10', src/main.rs:5:19
note: Run with `RUST_BACKTRACE=1` for a backtrace.
编译并没有产⽣任何错误，不过程序会出现⼀个运⾏时（runtime）错误
并且不会成功退出。当尝试⽤索引访问⼀个元素时，Rust 会检查指定的
索引是否⼩于数组的⻓度。如果索引超出了数组⻓度，Rust 会 panic，这
是 Rust 术语，它⽤于程序因为错误⽽退出的情况。
这是第⼀个在实战中遇到的 Rust 安全原则的例⼦。在很多底层语⾔中，
并没有进⾏这类检查，这样当提供了⼀个不正确的索引时，就会访问⽆效
的内存。通过⽴即退出⽽不是允许内存访问并继续执⾏，Rust 让你避开
此类错误。第九章会讨论更多 Rust 的错误处理。
函数
ch03-03-how-functions-work.md
commit 669a909a199bc20b913703c6618741d8b6ce1552
函数遍布于 Rust 代码中。你已经见过语⾔中最重要的函数之⼀： main
函数，它是很多程序的⼊⼝点。你也见过 fn关键字，它⽤来声明新函
数。
Rust 代码中的函数和变量名使⽤ snake case规范风格。在 snake case
中，所有字⺟都是⼩写并使⽤下划线分隔单词。这是⼀个包含函数定义⽰
例的程序：
⽂件名: src/main.rs
fn main() {
println!("Hello, world!");
    another_function();
}
fn another_function() {
println!("Another function.");
}
Rust 中的函数定义以 fn开始并在函数名后跟⼀对圆括号。⼤括号告诉
编译器哪⾥是函数体的开始和结尾。
可以使⽤函数名后跟圆括号来调⽤我们定义过的任意函数。因为程序中已
定义 another_function函数，所以可以在 main函数中调⽤它。注
意，源码中 another_function定义在 main函数之后；也可以定义在
之前。Rust 不关心函数定义于何处，只要定义了就⾏。
让我们新建⼀个叫做 functions的⼆进制项⽬来进⼀步探索函数。将上⾯
的 another_function例⼦写⼊ src/main.rs中并运⾏。你应该会看到如
下输出：
$ cargo run
   Compiling functions v0.1.0 (file:///projects/functions)
    Finished dev [unoptimized + debuginfo] target(s) in 
0.28 secs
     Running `target/debug/functions`
Hello, world!
Another function.
main函数中的代码会按顺序执⾏。首先，打印 “Hello, world!” 信息，然
后调⽤ another_function函数并打印它的信息。
函数参数
函数也可以被定义为拥有参数（parameters），参数是特殊变量，是函
数签名的⼀部分。当函数拥有参数（形参）时，可以为这些参数提供具体
的值（实参）。技术上讲，这些具体值被称为参数（arguments），但是
在⽇常交流中，⼈们倾向于不区分使⽤ parameter和 argument来表⽰函
数定义中的变量或调⽤函数时传⼊的具体值。
下⾯被重写的 another_function版本展⽰了 Rust 中参数是什么样的：
⽂件名: src/main.rs
fn main() {
    another_function(5);
}
fn another_function(x: i32) {
println!("The value of x is: {}", x);
}
尝试运⾏程序，将会输出如下内容：
$ cargo run
   Compiling functions v0.1.0 (file:///projects/functions)
    Finished dev [unoptimized + debuginfo] target(s) in 
1.21 secs
     Running `target/debug/functions`
The value of x is: 5
another_function的声明中有⼀个命名为 x的参数。x的类型被指定
为 i32。当将 5传给 another_function时，println!宏将 5放⼊
格式化字符串中⼤括号的位置。
在函数签名中，必须声明每个参数的类型。这是 Rust 设计中⼀个经过慎
重考虑的决定：要求在函数定义中提供类型注解，意味着编译器不需要你
在代码的其他地⽅注明类型来指出你的意图。
当⼀个函数有多个参数时，使⽤逗号分隔，像这样：
⽂件名: src/main.rs
fn main() {
    another_function(5, 6);
}
fn another_function(x: i32, y: i32) {
println!("The value of x is: {}", x);
println!("The value of y is: {}", y);
}
这个例⼦创建了有两个参数的函数，都是 i32类型。函数打印出了这两
个参数的值。注意函数的参数类型并不⼀定相同，这个例⼦中只是碰巧相
同罢了。
尝试运⾏代码。使⽤上⾯的例⼦替换当前 functions项⽬的 src/main.rs⽂
件，并⽤ cargo run运⾏它：
$ cargo run
   Compiling functions v0.1.0 (file:///projects/functions)
    Finished dev [unoptimized + debuginfo] target(s) in 
0.31 secs
     Running `target/debug/functions`
The value of x is: 5
The value of y is: 6
因为我们使⽤ 5作为 x的值， 6作为 y的值来调⽤函数，因此打印出
这两个字符串及相应的值。
包含语句和表达式的函数体
函数体由⼀系列的语句和⼀个可选的结尾表达式构成。⽬前为⽌，我们只
介绍了没有结尾表达式的函数，不过你已经见过作为语句⼀部分的表达
式。因为 Rust 是⼀门基于表达式（expression-based）的语⾔，这是⼀
个需要理解的（不同于其他语⾔）重要区别。其他语⾔并没有这样的区
别，所以让我们看看语句与表达式有什么区别以及这些区别是如何影响函
数体的。
实际上，我们已经使⽤过语句和表达式。语句（Statements）是执⾏⼀些
操作但不返回值的指令。表达式（Expressions）计算并产⽣⼀个值。让
我们看⼀些例⼦：
使⽤ let关键字创建变量并绑定⼀个值是⼀个语句。在列表 3-1
中，let y = 6;是⼀个语句。
⽂件名: src/main.rs
fn main() {
let y = 6;
}
列表 3-1：包含⼀个语句的 main函数定义
函数定义也是语句，上⾯整个例⼦本⾝就是⼀个语句。
语句不返回值。因此，不能把 let语句赋值给另⼀个变量，⽐如下⾯的
例⼦尝试做的，会产⽣⼀个错误：
⽂件名: src/main.rs
fn main() {
let x = (let y = 6);
}
当运⾏这个程序时，会得到如下错误：
$ cargo run
   Compiling functions v0.1.0 (file:///projects/functions)
error: expected expression, found statement (`let`)
 --> src/main.rs:2:14
  |
2 |     let x = (let y = 6);
  |              ^^^
  |
  = note: variable declaration using `let` is a statement
let y = 6语句并不返回值，所以没有可以绑定到 x上的值。这与其他
语⾔不同，例如 C 和 Ruby，它们的赋值语句会返回所赋的值。在这些语
⾔中，可以这么写 x = y = 6，这样 x和 y的值都是 6；Rust 中不
能这样写。
表达式会计算出⼀些值，并且你将编写的⼤部分 Rust 代码是由表达式组
成的。考虑⼀个简单的数学运算，⽐如 5 + 6，这是⼀个表达式并计算
出值 11。表达式可以是语句的⼀部分：在⽰例 3-1 中，语句 let y = 
6;中的 6是⼀个表达式，它计算出的值是 6。函数调⽤是⼀个表达
式。宏调⽤是⼀个表达式。我们⽤来创建新作⽤域的⼤括号（代码块），
{}，也是⼀个表达式，例如：
⽂件名: src/main.rs
fn main() {
let x = 5;
let y = {
let x = 3;
        x + 1
    };
println!("The value of y is: {}", y);
}
这个表达式：
{
let x = 3;
    x + 1
}
是⼀个代码块，它的值是 4。这个值作为 let语句的⼀部分被绑定到
y上。注意结尾没有分号的那⼀⾏ x+1，与你见过的⼤部分代码⾏不
同。表达式的结尾没有分号。如果在表达式的结尾加上分号，它就变成了
语句，⽽语句不会返回值。在接下来探索具有返回值的函数和表达式时要
谨记这⼀点。
具有返回值的函数
函数可以向调⽤它的代码返回值。我们并不对返回值命名，但要在箭头
（->）后声明它的类型。在 Rust 中，函数的返回值等同于函数体最后
⼀个表达式的值。使⽤ return关键字和指定值，可从函数中提前返
回；但⼤部分函数隐式的返回最后的表达式。这是⼀个有返回值的函数的
例⼦：
⽂件名: src/main.rs
fn five() -> i32 {
5
}
fn main() {
let x = five();
println!("The value of x is: {}", x);
}
在 five函数中没有函数调⽤、宏、甚⾄没有 let语句——只有数字
5。这在 Rust 中是⼀个完全有效的函数。注意，也指定了函数返回值的
类型，就是 -> i32。尝试运⾏代码；输出应该看起来像这样：
$ cargo run
   Compiling functions v0.1.0 (file:///projects/functions)
    Finished dev [unoptimized + debuginfo] target(s) in 
0.30 secs
     Running `target/debug/functions`
The value of x is: 5
five函数的返回值是 5，所以返回值类型是 i32。让我们仔细检查⼀
下这段代码。有两个重要的部分：首先，let x = five();这⼀⾏表明
我们使⽤函数的返回值初始化⼀个变量。因为 five函数返回 5，这⼀
⾏与如下代码相同：
let x = 5;
其次，five函数没有参数并定义了返回值类型，不过函数体只有单单⼀
个 5也没有分号，因为这是⼀个表达式，我们想要返回它的值。
让我们看看另⼀个例⼦：
⽂件名: src/main.rs
fn main() {
let x = plus_one(5);
println!("The value of x is: {}", x);
}
fn plus_one(x: i32) -> i32 {
    x + 1
}
运⾏代码会打印出 The value of x is: 6。但如果在包含 x + 1的⾏
尾加上⼀个分号，把它从表达式变成语句，我们将看到⼀个错误。
⽂件名: src/main.rs
fn main() {


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
