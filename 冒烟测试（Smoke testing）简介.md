近来看到和听到几个关于 Smoke Testing 的说法，也曾几次被顾问客户问及 Smoke Testing，感觉大家似乎对 Smoke Testing 的概念都相当模糊。据说软件测试中的 Smoke Testing 最早源于微软，而在实践中，我曾就此询问过美国微软的几个开发人员，他们的说法也莫衷一是。根据我搜集的一些资料，结合微软的实际测试工作，现将  Smoke Testing 综合介绍一下。
【误区】
　　先说说大家对 Smoke Testing 理解中的问题。查了一下网上有关 Smoke Testing 的资料，发现所有关于这方面的信息不外乎来源于两个：
1.	翻译过来的定义——关于 Smoke Testing 的定义能查到不少，内容基本是一致的，但是定义很表观且陈旧，和当前国际上大软件企业中的 Smoke Testing 实践并不十分相符。
2.	以讹传讹的理解——比如：
•	完全沿用 Smoke Testing 的原始意义——这是在理解一些外来专用语上常犯的一种错误。
•	想当然地理解为“用抽烟的功夫就能完成的测试”——这貌似有道理，但却是最荒谬的，因为 Smoke Testing 并
不见得比常规的测试花费更少的时间，而且在正式的软件测试工作环境里是没有人抽烟的。
•	笼统地把所有粗浅的测试都作为 Smoke Testing——这显然是因为对 Smoke Testing 定义中的“简单测试”或者
“初级测试”等等单词断章取义的理解。
•	认为 Smoke Testing 就是 BVT——这是因为 Smoke Testing 定义的模糊与过时。
等等。
　　那么真正的 Smoke Testing 是什么意思呢？
【Smoke Testing 释义】
　　Smoke Testing 的概念最早源于制造业，用于测试管道。测试时，用鼓风机往管道里灌烟，看管壁外面是否有烟冒出来，以便检验管道是否有缝隙。这一测试显然比较初级，更深层一点的测试至少要进行渗油测试、带压测试等等。Smoke Testing 只是一种初级、直观的测试。
　　软件测试中的 Smoke Testing 实际上用的是其引申含义，而且是引申了不止一道的含义，在这里，Smoke Testing 其实是个俚语——就跟很多其他源于美国软件行业的名词一样。
　　以前我并不知道 Smoke Testing 有适当的中文翻译，最早听到“冒烟测试”这个词还是在我的顾问客户那里。据我的理解，这个翻译只是字面翻译，显然并不能代表 Smoke Testing 的真实含义，换句话说“冒烟测试”只是 Smoke Testing 的字译而非意译。
　　Smoke Testing 在软件测试中的意义，应该说取的是其原始概念中的目的而非手段。通过 Smoke Testing，在软件代码正式编译并交付测试之前，先尽量消除其“表面的”错误，减少后期测试的负担。因此可以说，Smoke Testing 是预测试。
【Smoke Testing 的执行】
　　按照现有定义的说法，Smoke Testing 的执行似乎是在每日构建（daily build）完成时进行的，从这一点来看似乎说的就是 BVT。因此国内有人更加引申一步理解，把研发后期所做的一些不全面的集成测试也认为是 Smoke Testing。
　　实际上 Smoke Testing 的执行是在代码评审（code review）之后、每日构建（daily build）之前完成的工作——关于这一点，如果大家认真查阅国外同行关于 Smoke Testing 的介绍是不难找到叙述的。
【软件研发不同阶段的 Smoke Testing】
　　在实际的软件测试工作中，Smoke Testing 在软件研发的不同阶段有所不同。大体可以分为三类：
1.	形成集成测试版本以前——Smoke Testing 是随着代码的不断开发必做的一项工作，目的是验证各个单元能够成功执行，并保证测试版本能够顺利集成。
2.	形成集成测试版本以后——在代码 check in 到 daily build 之前执行 Smoke Testing，以保证新的或者更改过的代码不破坏集成版本的完成性和稳定性。
3.	后期预测试 Bug 的修正——后期 daily build 相对稳定时，针对每个 Bug 所做的 Bug Fix 都要先在“干净的” build 中进行 Smoke Testing，测试通过的 Bug Fix 才能 check in 到新的 daily build 中。
【Smoke Testing 与 BVT】
　　从 Smoke Testing 的定义上看，BVT 似乎可以看作是 Smoke Testing，但在实际当中 BVT 是与 Smoke Testing 完全独立的一个概念，这是基于以下几个方面：
•	Smoke Testing 与 BVT 的执行阶段不一样。
•	Smoke Testing 与 BVT 的内容不一样。
•	Smoke Testing 与 BVT 结果对后续工作的影响不一样。


冒烟可以分为前冒烟、后冒烟。前冒烟在提交代码到主线时触发，运行一系列测试用例。如果用例有失败则不允许合入主线。后冒烟在代码合入主线后触发， 相当于后校验。前冒烟一般有时间限制，后冒烟则可以放松要求。此外每日构建时也会有一系列用例触发。
