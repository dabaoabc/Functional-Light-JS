# JavaScript 轻量级函数式编程
# 第 1 章：为什么使用函数式编程？

> 函数式编程人员: 没有任何一个函数式编程者会把变量命名为 x，函数命名为 f，模块代码命名为“zygohistomorphic prepromorphism”。
>
> James Iry ‏@jamesiry 5/13/15
>
> https://twitter.com/jamesiry/status/598547781515485184

函数式编程（FP），不是一个新的概念，它几乎贯穿了整个编程史。我不确定这么说是否合理，但是很确定的一点是：直到最近几年，函数式编程才成为整个开发界的主流观念。所以我觉得函数式编程领域更像学者的领域。

然而一切都在变。不只是从编程语言的角度，一些库和框架都对函数式编程的兴趣空前高涨。你很可能也在读相关内容，因为你终于意识到函数式编程是不容忽视的东西。或者你跟我一样，已经尝试很多次去学函数式编程，但却很难理解所有的术语或数学符号。

无论你出于何目的翻阅本书，欢迎加入我们！

## 置信度

我有一个非常简单的前提，这是我作为软件开发老师（JavaScript）所做的一切基础：你不能信任的代码是你不明白的代码。此外，对你不信任或不明白的代码，你将不能确定这些代码是否符合你的业务场景。代码运行时也只能祈求好运。

信任是什么意思？信任是指你通过读代码，不仅是跑代码，就能理解这段代码能干什么事，而不只是停留在它可能是干什么的层面。也许我们不应该总倾向于通过运行测试程序，来验证程序的正确性。我并不是说测试不好，而是说我们应该对代码了如指掌，这样我们在运行测试代码之前就会知道它肯定能跑通。

通过读代码就能对我们的程序更有信心，我相信函数式编程技术的基础构成，是本着这种心态设计的。理解函数式编程并在程序中用心实践的人，得益于函数式编程已经被证实的原则，能够写出可读性高和可验证的代码，来达到他们想要的目的。

我希望你能通过理解轻量级函数式编程的原则，对你编写的代码更有信心，并且能在之后的路上越走越好。

## 交流渠道

函数式编程为何如此重要？为了回答这个问题，我们退一万步先来讨论一下编程本身的重要性。

我认为代码不是电脑中的一堆指令，这么说你可能感到很奇怪。事实上，代码能指示电脑运行就是一个意外的惊喜。

我深信代码的主要作用是方便人与人交流。

根据以往经验你可能知道，有时候花很多时间“编程”其实只是读现有的代码。我们的大部分时间其实都是在维护别人的代码（或自己的老代码），只有少部分时间是在敲新代码。

你知道研究过这个话题的专家给出了怎样的数据吗？我们在维护代码过程中 70％ 的时间花在了阅读和理解代码上。 也难怪全球程序员每天的平均代码行数是 5 行。我们一天花七个半小时用来读代码，然后找出这 5 行代码应该写在哪里。

我想我们应该更多的关注一下代码的可读性。可能的话，不妨多花点时间在可读性上。顺便提一句，可读性并不意味着最少的代码量，对代码的熟悉程度也会影响代码的可读性（这一点也是被证实过的）。

因此，如果我们要花费更多的时间来关注代码的可读性和可理解性，那么函数式编程为我们提供了一种非常方便的模式。函数式编程的原则是完善的，经过了深入的研究和审查，并且可以被验证。

如果我们使用函数式编程原则，我相信我们将写出更容易理解的代码。一旦我们知道这些原则，它们将在代码中被识别和熟悉，这意味着当我们读取一段代码时，我们将花费更少的时间来进行定位。我们的重点将在于如何组建所有已知的“乐高片段”，而不是这些“乐高片段”是什么意思。

函数式编程是编写可读代码的最有效工具之一（可能还有其他）。这就是为什么函数式编程如此重要。

### 可读性曲线

很重要的是，我先花点时间来讲述一种多年来让我感到困惑和沮丧的现象，在写本书时该问题尤为尖锐。

这也可能是许多开发人员会遇到的问题。亲爱的读者，当你读这篇文章的时候，你可能会发现自己也会遇到同样的状况。但是要振作起来，坚持下去，陡峭的学习曲线总会过去。

<p align="center">
	<img src="fig17.png" width="600">
</p>

我们将在下一章更深入的讨论这个问题。但是你可能写过一些命令式的代码，像 `if` 语句和 `for` 循环这样的语句。这些语句旨在精确地指导计算机**如何**完成一件事情。声明式代码，以及我们努力遵循函数式编程原则所写出的代码，更专注于描述最终的结果。

还有个残酷的问题摆在眼前，我在写本书时花费了很多时间在此问题上：我需要花费更多的精力和编写更多的代码来提高代码的可读性，尽量减少乃至消除可能会引入程序错误的代码部分。

如果你期望用函数式编程重构过的代码能够立刻变得更美观、优雅、智能和简洁的话，这个有点不太现实，这个变化是需要一个过程的。

函数式编程以另一种方式来思考代码应该如何组织才能使数据流更加明显，并能让读者很快理解你的思想。这种努力是非常值得的，然而过程很艰辛，你可能需要花很多时间基于函数式编程来调整代码直到代码可读性变得好一些。

另外，我的经验是，转换为声明式的代码之前，大约需要做六次尝试。对我来说，编写符合函数式编程的代码更像是一个过程，而不是从一个范例到另一个范例的二进制转换。

我也会经常对写过的代码进行重构。就是说，写完一段代码，过几个小时或一天再看会有不一样的感觉。通常，重构之前的代码是比较混乱不堪，所以需要反复调整。

函数式编程的过程并没有让我在艺术的画布上笔下生辉，让观众拍案叫好。相反，编程的过程很艰辛且历历在目，感觉像坐在一辆不靠谱的马车穿过一片杂草丛生的灌木树林。

我并不是试图打消你的激情，而是真切希望你也能够在编程的道路上披荆斩棘。过后我终于看到可读性曲线向上延伸，所有付出都是值得的，我相信你也会有同样的感受。

## 接受

我们要系统的学习函数式编程，探索发现最基本的原则，我相信规范的函数式编程编程者会遵循这些原则并把它们作为开发的框架。但在大多数情况下，我们大都选择避开晦涩的术语或数学符号，否则很容易使学习者受挫。

我觉得一项技术你怎么称呼它不重要，重要的是理解它是什么并且它是怎么工作的。这并不是说共享术语不重要，它无疑可以简化经验丰富的专业人士之间的交流。但对学习者来说，它有点分散人的注意力。

所以我希望这本书能更多地关注基本概念而不是花哨的术语。这并不是说没有术语，肯定会有。但不要太沉迷于华丽的词藻，追寻其背后的含义，这正是本书的目的。

我把这种欠缺正式实践的编程思想称为“轻量级函数式编程”，因为我认为真正的函数式编程的形式主义在于， 因为我认为如果你还不习惯函数式编程主张的思想，你可能很难用它。这不仅仅只是猜测，而是我的亲身经历。即使在传教函数式编程过程和完成这本书之后，我仍然可以说，函数式编程中术语和符号的形式化对于我来说是非常非常困难的。我已经再三尝试，发现大部分都是很难掌握的。

我知道很多函数式编程编程者会认为形式主义本身有助于学习。但我认为这是一个坑，当你试图用形式主义获得某种安慰时，你就会踩坑。但如果碰巧你有数学背景，甚至还有一些 CS 经验，这些问题对你来说就可能驾轻就熟。但是我们中的一些人不具备这些条件，不管我们怎么努力，形式主义总是阻碍我们前进。

因此，这本书介绍了一些我认为函数式编程会涉及到的概念，虽然不能直接让你受益但可以帮你逐步理解函数式编程整个过程。 

## 你不需要它

如果你规划一个项目花了很长时间，那么别人一定会告诉你“YAGNI” —— “你不需要它”。这个原则主要来自极限编程，强调构建特性的高风险和成本，这个风险和成本源自于项目本身是否需要。

有时我们考虑到将来可能会用到一个功能，并且认为现在构建它能够使得构建其他应用时更容易，后来意识到我们猜错了，原来这个功能并不需要，或者需要的完全是另外一套。另外一种情形是我们预估的功能是正确的，但构建得太早的话，相当于占用了开发现有功能的时间。有点像赔了夫人又折兵。

YAGNI 挑战，告诉我们：即使有的功能在某种情况下是反直觉的，我们也常常应该推迟构建,直到当前需要这个功能。我们倾向于夸大一个功能未来重构成本的心理估计，但往往这个重构是在将来需要时才会做。

上述情况对函数式编程也同样适用，不过我还是要先敲个警钟: 本书包含了大量你想去尝试的有趣的开发模式，但这不意味着你的代码一定要使用这些模式。

我与很多函数式编程开发人员的不同之处在于：你掌握了函数式编程并不意味着你一定得用它。此外，解决问题的方法很多，即使你掌握了更精炼的方法，能对维护和可扩展性更"经得起未来的考验"，但更轻量的函数式编程模式可能更适合该场景。

一般来说，我建议你在代码中寻求平衡，并且当你掌握函数式编程的诀窍时，在应用的过程中也应保持谨慎。在决定某个模式或抽象概念是否能使得部分代码可读性提高，或是否只是引入更智能的库时，YAGNI 的原则同样适用。

> 提醒一句，一些未曾用过的扩展点不仅浪费精力，而且可能妨碍你的工作。
>
> Jeremy D. Miller @jeremydmiller 2/20/15
>
> https://twitter.com/jeremydmiller/status/568797862441586688

记住，你编写的每一行代码之后都要有人来维护，这个人可能是你的团队成员，也可能是未来的你。如果代码写的太过复杂，那么无论谁来维护都会对你炫技式的故作聪明的做法倍感压力。

最好的代码是可读性高的代码，因为它在正确的（理想主义）和必然的（正确的）之间寻求到了恰到好处的平衡。

## 资源

我撰写这篇文章的过程参考了许多不同的资源。我相信你也会从中受益，所以我想花点时间把它们列出来。

### 书籍推荐

一些你务必要阅读的函数式编程 / JavaScript 书籍：

* [Professor Frisby's Mostly Adequate Guide to Functional Programming](https://drboolean.gitbooks.io/mostly-adequate-guide/content/ch1.html) by [Brian Lonsdorf](https://twitter.com/drboolean)
* [JavaScript Allongé](https://leanpub.com/javascript-allonge) by [Reg Braithwaite](https://twitter.com/raganwald)
* [Functional JavaScript](http://shop.oreilly.com/product/0636920028857.do) by [Michael Fogus](https://twitter.com/fogus)

### 博客和站点

一些其他作者和相关内容供查阅：

* [Fun Fun Function Videos](https://www.youtube.com/watch?v=BMUiFMZr7vk) by [Mattias P Johansson](https://twitter.com/mpjme)
* [Awesome函数式编程JS](https://github.com/stoeffel/awesome-fp-js)
* [Kris Jenkins](http://blog.jenkster.com/2015/12/what-is-functional-programming.html)
* [Eric Elliott](https://medium.com/@_ericelliott)
* [James A Forbes](https://james-forbes.com/)
* [James Longster](https://github.com/jlongster)
* [André Staltz](http://staltz.com/)
* [Functional Programming Jargon](https://github.com/hemanth/functional-programming-jargon#functional-programming-jargon)
* [Functional Programming Exercises](https://github.com/InceptionCode/Functional-Programming-Exercises)

### 一些库

本书中的代码段不使用库。我们发现的每一个操作，将派生出如何在独立的、普通的 JavaScript 中实现它。然而，当你开始使用函数式编程构建更多的真正代码时，你很快就会使用现有库中所提供的更可靠高效的通用功能。

顺便说一下，你要确保检查你所使用的库函数的文档，以确保你知道它们是如何工作的。它与本文中构建的代码有许多相似之处，但毫无疑问即便跟最流行的库相比还是会存在一些差异。

下面是一些流行的 JavaScript 版本的函数式编程库，可以开启你的探索之路：

* [Ramda](http://ramdajs.com)
* [lodash/fp](https://github.com/lodash/lodash/wiki/FP-Guide)
* [functional.js](http://functionaljs.com/)
* [Immutable.js](https://github.com/facebook/immutable-js)

附录 C 展示了用到了本书中一些示例的库。

## 总结

这就是 JavaScript 轻量级函数式编程。我们的目标是学会与代码交流，而不是在符号或术语的大山下被压的喘不过气。希望这本书能开启你的旅程！
