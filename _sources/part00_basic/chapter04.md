# 第四章 这个叫概率的东西到底是什么？

推断统计技术为我们对可能性的不确定性指定了精确的度量。不确定性是用概率来衡量的，因此我们必须先确定概率的性质，然后才能对其作出推断。本章介绍概率的基本概念。如果这一章对你来说太简短了，可以参考Albert和Rossman的著作(2001年，第227-320页)。

## 4.1 所有可能事件的集合

假设我有一枚硬币要抛出去。它有多大可能会冒出一个头来？它长出尾巴的可能性有多大？它长出躯干的可能性有多大？请注意，当我们考虑每一种结果的可能性时，我们脑海中都有一组所有可能的结果。龙卷风不是可能的结果之一。还请注意，一枚硬币的一次抛出只能产生一种结果；它不能在一次抛硬币中同时出现正面和反面。结果是相互排斥的。

每当我们问一个结果的可能性有多大时，我们总是会考虑到一系列可能的结果。这一套用尽了所有可能的结果，而且结果都是相互排斥的。这个集合称为样本空间。样本空间由我们用来观察世界的测量操作决定。在整本书的所有应用中，我们理所当然地认为有一个明确定义的操作来进行测量。例如，在抛硬币时，我们想当然地认为有一种明确的方法来发射和接住硬币，这样我们就可以准确地决定硬币何时停止运动，并且足够稳定，可以宣布这样或那样的结果。3又比如，在测量一个人的身高时，我们想当然地认为有一种明确的方法可以让一个人摆出对抗尺子的姿势，并准确地决定何时我们有足够稳定的天平读数来宣布一个人的身高的特定值。测量的机械操作化、数学形式化和哲学研究都可以有完整的书籍专门介绍。我们将不得不满足于这一段。

考虑一枚硬币在被抛出时正面朝上的概率。如果硬币是公平的，大约50%的掷硬币都应该是正面朝上的。如果硬币(或其抛掷装置)有偏向，那么抛硬币的次数往往会超过或低于50%。出现正面的概率可以用参数标签θ(希腊字母theta)来表示；例如，当θ=0.5时，硬币是公平的(口语中的“theta等于.5”)。

我们也可以考虑我们相信硬币是公平的程度。我们可能知道这枚硬币是由政府造币厂制造的，因此我们高度相信这枚硬币是公平的。或者，我们可能知道这枚硬币是由Acme Magic and Novity Company制造的，因此我们高度相信这枚硬币是有偏见的。对参数的置信度可以表示为p(θ)。如果硬币是由联邦政府铸造的，我们可能会坚信硬币是公平的；例如，我们可能会相信p(θ=0.5)=0.99，也就是说“θ等于0.5的概率是99%。“。如果硬币是由新奇公司铸造的，我们可能会坚信硬币是有偏见的；例如，我们可能相信p(θ=0.5)=0.0 1，p(θ=0.9)=0.99。

头部或尾部结果的“概率”和偏差中的“信任度”都是指样本空间。抛硬币的样本空间由两种可能的结果组成：正面和尾部。硬币偏差的样本空间由一系列可能的值组成：θ=0.0、θ=0.01、θ=0.02、θ=0.03，以及介于两者之间的所有值，最高可达θ=1.0。当我们抛出一枚给定的硬币时，我们是从头或尾的空间取样。当我们从一袋硬币中随机拿出一枚硬币时，每枚硬币可能有不同的偏向，我们是在从可能存在偏向的空间中抽样。

### 4.1.1 抛硬币：你为什么应该关心？

对于高赌注的游戏来说，硬币的公平性可能会产生巨大的影响，但在生活中，我们抛硬币并关心结果的情况并不常见。那么，为什么还要费心研究抛硬币的统计数据呢？

因为抛硬币是我们关心的无数其他现实生活事件的替代品。对于特定类型的心脏手术，我们可能会将患者的预后分类为存活一年以上或不存活一年，我们可能想知道患者存活一年以上的概率是多少。对于一种特定类型的药物，我们可能会将结果归类为头痛或不头痛，我们可能想知道头痛的概率。对于调查问题，结果可能是同意或不同意，我们想知道每个回答的概率。在两个候选人的选举中，两个结果是候选人A和候选人B，在选举本身之前，我们想从民意调查中估计候选人A获胜的可能性。或者，也许你是在通过测量多题考试的准确性来学习算术能力，因为多题考试的题目结果是正确的或错误的。或者你正在研究不同人群中特定认知过程的大脑偏侧化，在这种情况下，结果是右侧化或左侧化，而你正在估计在亚群中被左侧化的可能性。

无论何时我们讨论抛硬币，这可能不会让你真正着迷，请记住，我们谈论的可能是你真正感兴趣的某个领域！这些硬币仅仅是一系列类似应用的通用代表。

## 4.2  概率：头脑外部还是内部

有时我们谈论的是世界上“存在”的结果的概率。一枚抛出的硬币的表面是这样一个结果：我们可以观察到抛出的情况，而正面朝上的概率可以通过观察几次抛出来估计。

但有时我们谈论的可能性并不是那么清楚地“存在”的，而只是“头脑中”可能的信念。“。我们对硬币公平性的信念是大脑中某些东西的一个例子。这枚硬币可能有一种内在的物理偏见，但现在我指的是我们对这种偏见的信念。我们的信念指的是一个相互排斥、无所不包的可能性空间。说我们从我们的信仰中随机抽样可能有点奇怪，就像我们从一袋硬币中随机抽样一样。然而，正如我们将看到的，头脑外的概率和头脑内的信念的数学特性在本质上是相同的。

### 4.2.1 头脑外部：长期相对频率

对于头脑之外的事件，直观地认为概率是每种可能结果的长期相对频率。例如，如果我说对于一枚公平的硬币，正面的概率是0.5，我的意思是，如果我们多次抛硬币，大约50%的掷硬币会出现正面。从长远来看，在抛硬币很多很多次之后，人头的相对频率将非常接近0.5。

我们可以通过两种不同的方法来确定长期相对频率。一种方法是通过实际从太空中多次采样并统计每个事件发生的次数来近似它。第二种方法是通过数学推导。现在依次探讨这两种方法。

#### 4.2.1.1 模拟长期相对频率

假设我们想知道从一枚公平的硬币中获得人头的长期相对频率。似乎显而易见的是，在任何长时间的翻转序列中，我们都应该得到大约50%的人头。但让我们假装这并不是那么明显：我们所知道的是，当我们从中取样时，有一些潜在的过程会产生一个“H”或“T”。该流程有一个名为θ的参数，其值为θ=0.5。如果这就是我们所知道的全部，那么我们可以通过简单地重复从过程中采样来近似得到“H”的长期概率。我们从过程中抽样N次，统计“H”出现的次数，并通过相对频率估计H的概率。

手动采样一个过程，比如抛硬币，会变得乏味而耗时。取而代之的是，我们可以让计算机以更快的速度进行重复采样(希望计算机感觉不会像我们那样乏味)。图4.1显示了计算机模拟一枚公平硬币多次翻转的结果。R编程语言内置了伪随机数生成器，我们将经常使用这些生成器。4在第一次翻转时，计算机随机生成头部或尾部。然后，它计算到目前为止获得的人头比例。如果第一次翻转是头部，则头部比例为1/1=1.0。如果第一次翻转是尾巴，则头部比例为0/1=0.0。然后，计算机随机生成第二个头部或尾部，并计算到目前为止获得的头部的比例。如果到目前为止序列是HH，那么头部的比例是2/2=1.0。如果到目前为止序列是HT或TH，那么头部的比例是1/2=0.5。如果到目前为止序列是TT，那么头部的比例是0/2=0.0。然后，计算机生成第三个头部或尾部，并计算头部s f a r，n d s o n f r m a n y fl i ps的比例。图4.1显示了序列继续时磁头的运行比例。

<img src="https://gitee.com/XiShanSnow/imagebed/raw/master/images/articles/spatialPresent_20210426215201_fe.webp" style="zoom:67%;" />

请注意，在图4.1中，在长序列的末尾，头部的比例接近0.5，但不一定完全等于0.5。这种差异提醒我们，即使是这样的长期运行，仍然只是一个有限的随机样本，不能保证事件的相对频率将与事件的真实潜在概率相匹配。这就是为什么我们说我们是用长期相对频率来近似概率的原因。

#### 4.2.1.2 推导长期相对频率

有时，当情况在数学上足够简单时，我们可以推导出准确的长期相对频率。公平硬币的情况就是这样一个简单的情况。硬币的样本空间由头和尾两种可能的结果组成。通过公平的假设，我们知道每种结果的可能性都是相等的。因此，头部的长期相对频率应该正好是两个中的一个，即1/2，而尾部的长期相对频率也应该正好是1/2。

这一技术很容易推广到其他简单的情况。例如，考虑一个标准的六边形下模。它有六种可能的结果，即1点、2点、…。，6点。如果我们假设骰子是公平的，那么每个结果的长期相对频率应该正好是1/6。假设我们在六面骰子的面上放置不同的点。特别地，假设我们在一个面上放置1个点，在两个面上放置2个点，在其余三个面上放置3个点。

我们仍然假设这六个面中的每一个都有相等的可能性。那么1个点的长期相对频率正好是1/6，2个点的长期相对频率正好是2/6，3个点的长期相对频率正好是3/6。

### 4.2.2 头脑内部：主观信念

你有多相信美国政府铸造的硬币是公平的？如果你认为硬币可能会略有不同，而不是完全公平，那么你有多强烈地相信正面的概率是θ=0.51？或者θ=0.49时？相反，如果您考虑的是一枚古老的、不对称的、不对称的硬币，您认为它本身就有θ=0.5吗？在魔术店买一枚硬币怎么样？我们在这里谈论的不是硬币正面朝上的真实、固有的可能性。我们在讨论我们对每一种可能的概率的信任度。

要说明我们的主观信念，我们必须说明我们认为每种可能结果的可能性有多大。可能很难确定模糊的直觉信仰。在下一节中，我们将探索一种“校准”主观信念的方法，在接下来的一节中，我们将讨论从数学上描述信仰程度的方法。

#### 4.2.2.1 根据偏好校准主观信念

考虑一个可能会影响旅行者的简单问题：你有多相信明年元旦会有一场暴风雪关闭印第安纳波利斯附近的州际高速公路？在回答这个问题时，我们的工作是提供一个介于0和1之间的数字，以准确反映您的信念概率。得出这样一个数字的一种方法是用明确的概率来校准你相对于其他事件的信念。

作为一个比较事件，考虑一下袋装弹珠实验。我们在一个袋子里放了10个弹珠：5个红色的，5个白色的。我们摇一摇麻袋，然后随意画一颗大理石。当然，获得红色大理石的概率是5/10=0.5。我们将用这一袋弹珠作为对比，来考虑新年那天印第安纳波利斯的降雪情况。

考虑一下以下两种你可以选择的赌博：

·赌博A：如果明年新年印第安纳波利斯有暴风雪，你就可以得到100美元。

·赌博 B：y o u g e t$10 0 i f y o u d r a w a r e d m a r b l e f r o m a r b l e e s w i t h h 5 r e d和5个白色弹珠。

你喜欢哪一种赌博？如果你更喜欢赌博B，这意味着你认为印地发生阻止交通的暴风雪的可能性不到50%。所以至少你现在知道了，你对暴风雪阻挡交通的概率的主观信念是小于0.5的。

我们可以通过考虑其他比较赌博来缩小信任度。考虑一下这两个赌注：

·赌博A：如果明年新年印第安纳波利斯有暴风雪堵车，你就可以得到100美元。

·赌博C：如果你从一袋有1个红色弹珠和9个白色弹珠的弹珠中抽出一个红色弹珠，你就可以得到100美元。

你喜欢哪一种赌博？如果你现在更喜欢赌博A，这意味着你认为新年那天印地有超过10%的可能性会阻止暴风雪的交通。加在一起，这两个比较赌博告诉你，你的主观概率在0.1到0.5之间。我们可以继续考虑对其他候选赌博的偏好，以更准确地校准您的主观信念。

#### 4.2.2.2 对主观信念的数学描述

当样本空间中有几种可能的结果时，试图校准你对每一种可能结果的主观信念可能太费力了。相反，你可以使用一个数学函数来总结你的信仰。

例如，你可能认为美国女性的平均身高是5？4？？，但你要接受这个平均值可能略高于或低于这个值的可能性。这太乏味了，而且可能无法指定您的平均高度是4？1？？，或者r 4？2？，或者r 4？3？，依此类推，直到6？1？、6？2？、n d 6？3？？等等。因此，您可以用一条钟形曲线来描述您的信仰程度，该曲线在5？4？？时最高。在最有可能的高度上下对称下落。你可以改变曲线的宽度和中心，直到它看起来最能抓住你的主观信念。在这本书的后面，我们将讨论这类函数的精确数学公式，但现在的重点仅仅是理解数学函数可以定义曲线的想法，这些曲线可以用来描述信任度。

### 4.2.3 概率将数字分配给可能性

一般说来，概率，无论是在头脑之外还是头脑内部，都只是将数字分配给一组相互排斥的可能性的一种方式。这些被称为“概率”的数字只需要满足三个性质(Kolmogorov，1956)：

1.概率值必须为非负(即零或正)。

2.整个样本空间中所有事件的概率之和必须为1.0(即，该空间中的一个事件必须发生，否则该空间不会用尽所有可能性)。

3.对于任何两个相互排斥的事件，其中一个或另一个发生的概率是它们各自的概率之和。例如，公平的六面骰子出现3点或4点的概率是1/6+1/6=2/6。

对符合这三个属性的事件的任何数字赋值也将具有我们将在下面讨论的所有概率属性。因此，无论概率被认为是世界上结果的长期相对频率，还是主观信念的大小，它在数学上的表现都是一样的。

## 4.3 概率分布

概率分布仅仅是所有可能结果及其相应概率的列表。对于一枚硬币，概率分布是微不足道的：我们列出两个结果(头部和尾部)及其对应的两个概率(θ和1−θ)。然而，对于其他几组结果，分布可能更为复杂。例如，考虑随机选择的人的身高。对于每个可能的精确高度，高度可能是60.2？？，高度将是68.9？，依此类推。当结果是连续的，比如高度，那么概率的概念就会呈现出一些微妙之处，正如我们将看到的那样。

### 4.3.1 离散分布：概率质量

当样本空间由离散的结果组成时，我们可以讨论每个不同结果的概率。例如，抛硬币的样本空间有两个离散的结果，我们讨论正面或尾部的概率。六面骰子的样本空间有六个离散的结果，我们讨论1点、2点的概率，依此类推。

对于连续的结果空间，我们可以将其离散化成一个相互排斥且穷举的有限集合。“。例如，虽然人的身高是一个连续的标尺，但我们可以将标尺划分为有限数量的区间，例如<51？？，51？？到53？？，53？到55？？，55？到57？？，…。，>83℃。然后我们可以讨论随机选择的人落入这些区间的概率。假设我们随机抽样10,000人，非常精确地测量身高。图4.2的顶部面板显示了10,000个测量值的散点图，用垂直虚线标记间隔。具体地说，落在63？到65？区间内的测量值数量为1,473，这意味着(估计的)落入该区间的概率为1,473/10,000=0.1473。

<img src="https://gitee.com/XiShanSnow/imagebed/raw/master/images/articles/spatialPresent_20210426220010_49.webp" alt="image-20210426215948933" style="zoom:67%;" />

离散结果的概率，例如落入连续尺度上的区间的概率，被称为概率质量。粗略地说，术语“质量”指的是物体中物质的数量。当材料是概率，对象是一个尺度的区间时，质量就是区间中结果的比例。请注意，跨区间的概率质量之和必须为1。

### 4.3.2 连续分布：与密度交会

如果你仔细考虑一个连续的结果空间，你会意识到谈论一个特定值在连续体上的概率是有问题的，而不是在连续体上的一个区间。例如，随机选择的人的身高(以英寸为单位)正好为67.21413908…的概率。本质上是零，这对于你所关心的任何精确值都是正确的。然而，我们可以讨论区间的概率质量，就像我们在上面的例子中所做的那样。然而，使用间隔的问题是它们的宽度和边缘是任意的，宽间隔不是很精确。因此，我们要做的是使区间无限窄，而不是讨论每个无穷小区间的无穷小概率质量，而是讨论概率质量与区间宽度的比率。这个比率叫做概率密度。

不严格地说，密度是指每单位空间所占的物料量。因为我们是用它的质量来衡量物质的数量，所以密度就是质量除以它所占的空间。请注意，小质量可以具有高密度：一毫克金属铅的密度超过每立方厘米11克，因为这毫克只占用0.000088立方厘米的空间。重要的是，我们可以设想空间中某一点的密度，即当所考虑的空间缩小到该点周围的无限小区域时，质量与空间的比率。

图4.2显示了这种想法的示例。如前所述，上面的面板显示了10,000个随机选择的人的身高(以英寸为单位)的散点图，间隔宽度为2.0。为了计算63°到65°区间内的平均概率密度，我们将区间的概率质量除以区间的宽度。概率质量为(估计为)1473/10000=0.1473，区间宽度为2.0Unit(即65−63)，因此区间内的平均概率密度为0.074(四舍五入)。这是该间隔内的平均概率密度。要在较窄的间隔内获得更精确的密度，请考虑图4.2的下部面板。它的质量(估计)为665/10000，因此区间内的平均概率密度为(665/10000)/(64−63)=0.066(四舍五入)。我们可以继续缩小间隔和计算密度。

图4.2中的例子说明了从有限样本跨非无穷小区间估计密度。但要计算无穷小区间的密度，我们必须假设无限人口不断地分布在整个尺度上。那么，即使是一个无穷小的区间也可能包含一些非零(虽然无穷小)的概率质量，我们可以参考尺度上某一点的概率密度。我们很快就会看到这个想法的数学例子。

图4.3显示了另一个示例，以强调概率密度可以大于1，即使概率质量不能超过1。图4.3的上部面板显示了随机选择的10,000扇门的高度(以英寸为单位)，这些门被制造为7英尺(84英寸)高。由于制造过程的规律性，门的高度之间只有很小的随机变化，从图中可以看出，刻度范围很小，只从83.6？？降至84.4？？因此，所有的概率质量都集中在一个很小的标度范围内。

<img src="https://gitee.com/XiShanSnow/imagebed/raw/master/images/articles/spatialPresent_20210426220139_dc.webp" style="zoom:67%;" />

因此，84英寸的值附近的概率密度超过1.0。例如，在区间83.9097？？到83.9355？？中，存在概率质量730/10000=0.073。但该质量集中在仅83.9355−83.9097=0.0258的箱宽上，因此区间内的平均密度为0.073/0.0258=2.829。概率密度大于1.0没有什么神秘之处；它仅仅意味着相对于尺度有高度集中的概率质量。

#### 4.3.2.1 概率密度函数的性质

一般而言，对于分割成区间的任何连续值，区间的概率质量之和必须为1，因为根据进行测量的定义，测量尺度的某个值必须出现。我们可以把这个事实写成一个方程式，但我们需要先定义一些记号。设连续变量记为x，x上区间的宽度记为？x(符号“？”这是希腊字母，大写为Delta)。设i是区间的指标，[xi，xi+？x]表示xi和xi+？x之间的区间，第i个区间的概率质量记为p([xi，xi+？x])。那么这些概率质量的和必须是1，其表示如下：
$$
\sum_{i} p\left(\left[x_{i}, x_{i}+\Delta x\right]\right)=1
$$
现在回想一下概率密度的定义：它是概率质量与区间宽度之比。通过除以？x并乘以？x，我们可以根据每个区间的密度改写公式4.1，如下所示：
$$
\sum_{i} \Delta x \frac{p\left(\left[x_{i}, x_{i}+\Delta x\right]\right)}{\Delta x}=1
$$
在极限中，当区间宽度变得无穷小时，我们将x附近的区间宽度表示为dx而不是？x，并将x附近无穷小区间内的概率密度简记为p(X)。不要将概率密度p(X)与p([xi，xi+？x])混淆，p([xi，xi+？x])是区间内的概率质量。那么等式4.2中的求和就变成了一个积分：
$$
\underbrace{\sum_{i}}_{\int} \underbrace{\Delta x}_{\mathrm{d} x} \underbrace{\frac{p\left(\left[x_{i}, x_{i}+\Delta x\right]\right)}{\Delta x}}_{p(x)}=1 \quad \text{即，} \int \mathrm{d} x p(x)=1
$$
在本书中，积分将用dx项写在积分符号旁边，如公式4.3所示，而不是写在表达式的最右端。虽然这个位置不是最传统的符号，但它既不是错误的，也不是本书独有的。将dx放在整数旁边，可以很容易地看到要对哪个变量进行积分，而不必在整数上加上下标。当我们遇到涉及多变量的函数积分时，这种用法特别有用。在重写离散和和积分时，将dx放在整数旁边也可以保持项的分组，这样？X变为？dx，而不必将dx移动到表达式的末尾。

重申一下，在方程式4.3中，p(X)是关于x的无穷小区间内的概率密度。通常，我们让上下文告诉我们是指概率质量还是指概率密度，并使用相同的符号p(X)，f或r b o t h。例如，如果x是六面骰子的面值，则p(X)是概率质量。如果x是高度的精确点值，那么p(X)就是概率密度。然而，在使用中可能会有“滑移”。例如，如果x指的是高度，但刻度被离散成区间，那么p(X)实际上指的是x落入的区间的概率质量。归根结底，你必须注意上下文，并容忍模棱两可。

#### 4.3.2.2 正态概率密度函数

任何仅具有非负值并且积分为1(即，满足公式4.3)的函数可以被解释为概率密度函数。也许最著名的概率密度函数是正态分布，也称为高斯分布。法线曲线的图形是众所周知的钟形；图4.4中显示了一个示例。

<img src="https://gitee.com/XiShanSnow/imagebed/raw/master/images/articles/spatialPresent_20210426220541_8d.webp" style="zoom:67%;" />

正态概率密度的数学公式有两个参数：μ(希腊µ)称为分布的平均值，σ(希腊西格玛)称为标准偏差。μ的值控制钟形中间在x轴上的位置，因此它被称为位置参数，而σ的值控制钟形的宽度，因此它被称为比例参数。正如第2.2节中所讨论的，您可以将参数视为控制旋钮，用于操作分布的位置和规模。正态概率密度的数学公式为：
$$
p(x)=\frac{1}{\sigma \sqrt{2 \pi}} \exp \left(-\frac{1}{2}\left[\frac{x-\mu}{\sigma}\right]^{2}\right)
$$
图4.4中显示了μ和σ特定值的正态分布示例。请注意，当标准差σ较小时，峰值概率密度可以大于1.0.。换言之，当标准差较小时，大量的概率群被压缩到一个小区间内，因此该区间内的概率密度较高。

图4.4还说明，法线下的面积实际上是1。x轴被分成一个密集的小间隔梳子，宽度表示为？x。如公式4.2所示，通过将所有微小间隔的质量相加来近似正常密度的t h e i n t g r a l。如图中的文本所示，间隔面积的总和实质上是1.0。只有舍入误差，以及分布的极端尾部不包括在和中的事实，才会阻止和恰好为1

### 4.3.3 分布的均值和方差

当我们有一个以概率p(X)生成的数值(而不仅仅是分类的)值时，我们可以想知道，如果我们重复采样x的值，那么从长远来看，它的平均值会是多少。例如，如果我们有一个公平的六边形骰子，那么从长远来看，它的六个值中的每个值都应该出现六分之一的时间。所以骰子的长期平均值是(1/6)1+(1/6)2+(1/6)3+(1/6)4+(1/6)5+(1/6)6=3.5。作为另一个例子，如果我们玩老虎机，我们以0.001的概率赢得$100，我们以0.14%的概率赢得$5，否则我们损失$1，那么从长远来看，我们的收益是(0.001)($100)+(0.14)($5)+(0.859)(−$1)=−$0.059。换句话说，从长远来看，强盗的手臂每拉一次，我们就会损失大约6美分。注意我们在这些计算中做了什么：我们根据发生的概率对每个可能的结果进行加权。此过程定义概率分布的平均值，也称为期望值，表示为E[x]：
$$
E[x]=\sum_{x} p(x) x
$$
当x的值是离散的时，公式4.5适用，因此p(X)表示概率质量。当x的值连续时，p(X)表示概率密度，并且和成为无穷小区间上的积分：
$$
E[x]=\int \mathrm{d} x p(x) x
$$
无论x是离散的还是连续的，概念上的含义都是相同的：E[x]是这些值的长期平均值。

直观地讲，分布的平均值通常位于分布的中间位置。例如，正态分布的平均值是其参数μ的值。换句话说，结果是E[x]=μ。这一事实的一个具体示例如图4.4中所示，可以看到大部分分布集中在x=μ上；有关μ的确切值，请参见图中的文本。

下面是一个使用公式4.6计算连续分布平均值的例子。考虑定义在区间x−[0，1]上的概率密度函数p(X)=6x(1∈x)。这实际上是一个概率密度函数：它是一个倒置抛物线，从x=0开始，在x=0.5上达到峰值，在x=1处再次下降到基线。因为它是对称分布，直觉告诉我们平均值应该在它的中点，x=0.5。让我们来检查一下它是不是真的是：
$$
\begin{aligned} E[x] &=\int \mathrm{d} x p(x) x \\ &=\int_{0}^{1} \mathrm{~d} x 6 x(1-x) x \\ &=6 \int_{0}^{1} \mathrm{~d} x\left(x^{2}-x^{3}\right) \\ &=6\left[\frac{1}{3} x^{3}-\frac{1}{4} x^{4}\right]_{0}^{1} \\ &=6\left[\left(\frac{1}{3} 1^{3}-\frac{1}{4} 1^{4}\right)-\left(\frac{1}{3} 0^{3}-\frac{1}{4} 0^{4}\right)\right] \\ &=0.5 \end{aligned}
$$
我们在这本书中做的微积分相对较少，公式4.7是我们能学到的最高级的。如果你的微积分知识是生疏的，不要担心，只要继续阅读来理解概念就行了。

概率分布的方差是表示该分布远离其平均值的离散度的数字。关于x的值离其平均值有多远，有许多可以想象的定义，但用于特定术语“方差”的定义是基于x和平均值之间的平方差。方差的定义就是x值与其平均值的均方差(MSD)：
$$
\operatorname{var}_{x}=\int \mathrm{d} x p(x)(x-E[x])^{2}
$$
请注意，方程式4.8就像平均值(方程式4.6)e x c e p t的公式，我们不是对x按x的概率加权进行积分，而是对(x−E[x])2进行按x的概率加权的积分。换言之，方差就是(x−E[x])2的平均值。对于离散分布，公式4.8中的积分变成和，类似于公式4.5和公式4.6中的关系。方差的平方根，有时称为均方根(RMSD)，称为分布的标准差。

正态分布的方差是其参数σ的平方。因此，对于正态分布，Varx=σ2。换句话说，正态分布的标准差是参数σ的值。在正态分布中，大约34%的分布在μ和μ+σ之间(请参阅练习4.5)。请看图4.4后，直观地确定μ和μ+σ在x轴上的位置(μ和σ的值在图中的文本中标明)，以获得一个标准差离平均值有多远的直观印象。但是，请注意不要过度概括到其他形状的分布：非正态分布的平均值和第一标准差之间可能有非常不同的区域。

概率分布可以指测量值的概率或参数值的概率。概率可以解释为一个值可以从生成过程中抽样多少，也可以解释为该值相对于其他值有多大的可信度。当p(θ)代表θ的可信度值，而不是抽样θ的概率时，p(θ)的平均值可以被认为是代表典型可信值的θ的值。θ的标准差衡量了分布的广度，可以看作是对候选值之间不确定性的衡量。如果标准差很小，那么我们强烈相信θ的值接近平均值。如果标准差很大，那么我们就不太确定应该相信θ的什么值。标准差这个代表不确定性的概念将经常出现。分布宽度的相关度量是最高密度区间，如下所述。

#### 4.3.3.1 以最小方差表示的平均值

另一种概念上的重点是从方差的定义开始，推导出均值的定义，而不是从均值开始，然后得出方差的定义。在这个备选概念下，目标是定义概率分布的中心趋势值。如果值接近分布的极有可能值，则值表示分布的中心趋势。

因此，我们将分布的中心趋势定义为，无论值M如何最小化它与x的所有其他值之间的长期预期距离。但是，我们应该如何定义值之间的“距离”呢？定义距离的一种方法是平方差：x和M之间的距离是(x−M)2。这个定义的一个优点是x到M i s t h es s a m e a s t h e d i s t a n c e f r o m M to x的距离，因为(x−M)2=(M−x)2。但这个定义的主要优点是它使许多后续的代数易于处理(这里不再赘述)。因此，中心趋势是最小化(x−M)2的期望值的值M。因此，我们想要最小化？dxp(X)(x−M)2的值M。这看起来熟悉吗？它本质上是分布方差的公式，在方程式4.8中，但这里被认为是M的函数。这里最有趣的是：它证明了最小化？dxp(X)(x−M)2的M的值是E[x]。换句话说，分布的平均值是最小化预期平方偏差的值。在这种情况下，平均数是分布的中心趋势。

另外，如果将M和x之间的距离定义为|x−M|，则最小化预期距离的值称为分布的中值。类似的说法适用于分布模式，对于任何完全匹配，距离定义为零，对于任何不匹配，距离定义为一。

### 4.3.4 最高密度间隔(HDI)

总结分布的另一种方法(我们将经常使用)是最高密度区间，缩写为HDI。6HDI指示分布的哪些点是最可信的，哪些覆盖了分布的大部分。因此，HDI通过指定跨越大部分分布(比方说分布的95%)的区间来总结分布，使得区间内的每个点都比区间外的任何点具有更高的可信度。

图4.5显示了HDI的示例。上面的面板呈正态分布，平均值为0，标准差为1。因为这个正态分布在零附近是对称的，所以95%的−从1.96扩展到+1.96。在这些界限之间的曲线下的面积，在图4.5中以灰色表示，面积为0.95。此外，在这些限制内的任何x的概率密度都比那些限制之外的任何x具有更高的概率密度。

<img src="https://gitee.com/XiShanSnow/imagebed/raw/master/images/articles/spatialPresent_20210426221404_0d.webp" style="zoom:67%;" />

图4.5的中间面板显示了倾斜分布的95%HDI。根据定义，95%HDI限制之间的曲线下面积(图中以灰色表示)的面积为0.95，并且这些限制内的任何x的概率密度都高于这些限制之外的任何x。重要的是，请注意，左侧尾部的区域小于左侧HDI限制，大于右侧尾部的区域，大于右侧HDI限制。换句话说，HDI不一定在HDI之外产生等面积的尾部。(对于那些以前遇到过等尾可信区间概念的人，您可以向前看图12.2，第342页，以了解HDI与等尾区间有何不同。)。

图4.5的下部面板显示了一个奇特的双峰概率密度函数。在许多实际应用中，不会出现这样的多峰分布，但是这个例子对于澄清HDI的定义很有用。在这种情况下，HDI被分成两个子间隔，每个子间隔对应于分布的每种模式。但是，定义特征与以前相同：95%HDI限制内曲线下的区域在图中以灰色着色，总面积为0.95，并且这些限制内的任何x的概率密度都高于这些限制外的任何x。

HDI的形式化定义就是这两个本质特征的数学表达。95%HDI包括密度至少与某个值W一样大的所有x值，使得所有这些x值的积分为95%。形式上，95%HDI中x的值是p(X)>W，其中W满足？X：p(X)>wdx p(X)=0.95。

当分布指的是价值的可信度时，HDI的宽度是衡量信仰不确定性的另一种方式。如果HDI很宽，那么信仰就不确定了。如果人类发展指数很窄，那么信仰就相对确定。正如将在第13章详细讨论的那样，有时研究的目标是获得关于特定参数值的相当高确定性的数据。所需的确定程度可以用95%HDI的宽度来衡量。例如，如果μ是一种药物降低血压多少的量度，研究人员可能想要一个95%的HDI宽度在血压计上不超过5个单位的估计值。再举一个例子，如果θ是衡量一个人群对候选人A的偏好程度，而不是对候选人B的偏好，研究人员可能想要一个95%的HDI宽度不超过10个百分点的估计值。

## 4.4 双向分布

在许多情况下，我们对两个结果的结合感兴趣。发一张既是皇后又是王牌的牌的概率是多少？遇到红头发和绿眼睛的人的可能性有多大？当玩一个骰子和旋转手柄的棋盘游戏时，我们相信骰子和旋转手柄都是公平的。

![](https://gitee.com/XiShanSnow/imagebed/raw/master/images/articles/spatialPresent_20210426221602_7f.webp)

作为开发这些想法的一个具体示例，请考虑Ta b l e 4。1，w h i c h h s ho w是人们眼睛颜色和头发颜色不同组合的概率。这些数据来自特定的便利样本(Snee，1974)，并不代表任何更大的人群。Ta，b，l，e，4。1考虑了列中列出的四种可能的眼睛颜色和列中列出的四种可能的头发颜色。在每个主要单元格中，该表显示了眼睛颜色和头发颜色的特定组合的联合概率。例如，左上角的单元格表示棕色眼睛和黑色头发的联合概率为0.11(即11%)。请注意，并不是所有眼睛颜色和头发颜色的组合都是一样的。例如，蓝眼睛和黑头发的联合概率只有0.03(即3%)。We表示眼睛颜色e和头发颜色h的联合概率为p(e，h)。联合概率的符号是对称的：P(e，h)=p(h，e)。

我们可能会对眼睛的整体颜色、跨发色折叠的概率感兴趣。这些概率在表的右侧空白处表示，因此称为边际概率。只需将每行中的联合概率相加，即可计算出行和。例如，不管头发颜色如何，绿色眼睛的边际概率是0.11。由于原始数据的舍入误差，表中指示的连接值并不完全与显示的边际值相加。眼睛颜色e的边际概率表示为p(E)，它是通过将所有头发颜色的关节概率相加计算得出的：p(E)=？Hp(e，h)。

当然，我们也可以考虑各种发色的边际概率。毛发颜色的边际概率显示在Ta、b、l、e、4的下边距上。1.例如，不管眼睛颜色如何，黑发的概率是0.18。边际概率是通过对每列内的联合概率求和来计算的。因此，p(H)=？Ep(e，h)。

通常，考虑行变量r和列变量c。当行变量是连续的而不是离散的时，p(r，c)是概率密度，并且用于计算边际概率的总和变成积分，p(R)=dcp(r，c)，w e r e所得到的边际分布p(R)也是概率密度。这个求和过程被称为对c的边际化或对变量c的积分。当然，我们也可以通过对r进行边际化来确定概率p(C)：p(C)=？drp(r，c)。

### 4.4.1 条件概率

我们经常想知道一种结果的概率，因为我们知道另一种结果是真的。例如，假设我从Ta b l e 4中提到的人口中随机抽样一个人。假设我告诉你这个人有一双蓝眼睛。根据这些信息，这个人拥有金发(或任何其他特定发色)的可能性有多大？如何计算答案很直观：我们从Ta，b，l，e，4的蓝眼行看。1蓝眼睛人口的总数(即边际)是0.36，0.16的人口是蓝眼睛和金发。因此，在0.36名蓝眼睛的人中，0.16/0.36人的头发是金色的。换句话说，在蓝眼睛的人中，45%的人是金发。我们还注意到，在蓝眼睛的人中，0.03/0.36=8%是黑色头发。Ta，b，l，e，4。2显示了每种头发颜色的计算结果。

头发颜色的概率表示每种可能的头发颜色的可信度。从Ta b l e 4的边缘分布可以看出，这一人群拥有金发的概率一般为0.21。1.但当我们得知这一群体中的一个人是蓝眼睛时，那个金发的人的可信度就会增加到0.45，从Ta b l l e 4可以看出。2.这种对可能的发色可信度的重新分配是贝叶斯推断！但我们有些言过其实了；下一章将详细解释贝叶斯推理的基本数学。

条件概率的直观计算可以用简单的形式表达式表示。We表示给定眼睛颜色的头发颜色的条件概率为p(h|e)，它被称为“给定e的h的概率”。然后将上述直观计算写成p(h|e)=p(e，h)/p(E)。将该方程作为条件概率的定义。回想一下，边际概率仅仅是小区概率的总和，因此定义可以写为p(h|e)=p(e，h)/p(E)=p(e，h)/？Hp(e，h)。这个等式可能会令人困惑，因为分子中的h是头发颜色的特定值，但分母中的h是一个变量，它采用所有可能的头发颜色值。为了消除h的两个含义的歧义，方程式可以写成p(h|e)=p(e，h)/p(E)=p(e，h)/？H∗p(e，h∗)，w h e r e h∗表示头发颜色的可能值。

<img src="https://gitee.com/XiShanSnow/imagebed/raw/master/images/articles/spatialPresent_20210426221810_f4.webp" style="zoom:67%;" />

条件概率的定义可以使用更通用的变量名来编写，其中r指的是任意行属性，c指的是任意列属性。然后，对于具有离散值的属性，条件概率定义为
$$
p(c \mid r)=\frac{p(r, c)}{\sum_{c^{*}} p\left(r, c^{*}\right)}=\frac{p(r, c)}{p(r)}
$$
当列属性为连续时，总和变为整数：
$$
p(c \mid r)=\frac{p(r, c)}{\int \mathrm{d} c p(r, c)}=\frac{p(r, c)}{p(r)}
$$
当然，我们可以以另一个变量为条件。也就是说，我们可以考虑p(r|c)而不是p(c|r)。重要的是要认识到，一般来说，p(r|c)不等于p(c|r)。例如，假设正在下雨，地面是湿的概率与假设地面是湿的情况下下雨的概率是不同的。下一章将进一步讨论p(r|c)和p(c|r)之间的关系。

同样重要的是要认识到，条件概率中没有时间顺序。当我们说“x给定y的概率”时，并不意味着y已经发生了，而x还没有发生。我们的意思是，我们将概率的计算限制在可能结果的特定子集。P(x|y)的一个更好的解释是，“在所有具有值y的联合结果中，它们中的这一比例也具有值x。”例如，假设第二天早上有云，我们可以讨论前一天晚上下雨的条件概率。这仅仅是指前一天晚上所有多云早晨下雨的比例。

### 4.4.2 属性的独立性

假设我有一个六边形骰子和一枚硬币。假设他们是公平的。我抛硬币，它就会正面朝上。考虑到硬币的这个结果，掷骰子上升3的概率是多少？在回答这个问题时，你可能会想，“硬币对骰子没有影响，所以无论硬币的结果如何，骰子升3的概率是1/6。“。如果你是这么想的，那你是在假设旋转器和硬币是独立的。

一般来说，当y的值对x的值没有影响时，给定y的x的概率通常就是x的概率。在形式上，这个概念表示为x和y的所有值的p(x|y)=p(X)。让我们想一想这意味着什么。我们从条件概率的定义中知道，在公式4.9或4.10中，th a tp(x|y)=p(x，y)/p(Y)。组合这些方程意味着x和y的所有值的p(X)=p(x，y)/p(Y)。将两边乘以p(Y)后，我们得到x和y的所有值的p(x，y)=p(X)p(Y)的蕴涵。这个蕴涵也是反过来的：当x和y的所有值的p(x，y)=p(X)p(Y)时，x和y的所有值的p(x，y)=p(X)=p(X)。当x和y的所有值的p(x，y)=p(x|y)=p(X)时，x和y的所有值的p(x，y)=p(X)=p(x。这两个条件都是我们对属性独立性的数学定义。重申，说属性x和y是独立的意味着对于x和y的所有值p(x|y)=p(X)，这在数学上等同于说对于x和y的所有值p(x，y)=p(X)p(Y)。

考虑一下Ta b l e 4中眼睛颜色和头发颜色的例子。1(第90页)。这些属性是独立的吗？从日常经验中，我们直观地知道答案应该是否定的，但我们可以用数学方法来表示。要证明独立性，我们只需要一些眼睛颜色e和一些头发颜色h，其中p(h|e)？=p(H)，或者e q u i v a l e n t l y or其中p(e，h)？=p(E)p(H)。我们已经处理过这样的情况了，就是蓝眼睛和金发。Ta，b，l，e，4。1表示金发的边际概率为p(金发)=0.21，而Ta b l e为4。2表明，在给定蓝眼睛的情况下，金发的条件概率为p(金色|蓝色)=0.45。因此，p(金发|蓝色)？=p(金发)。相反，我们可以通过交叉相乘边际概率并表明它们不等于联合概率来反驳独立性：p(蓝色)·p(金色)=0.36·0.21=0.08？=0.16=p(蓝色，金色)。

作为两个独立属性的简单示例，请考虑标准纸牌中扑克牌的花色和价值。有四种花色(方块、红心、梅花和黑桃)和十三种值(王牌、2、…。、9、杰克、王后、国王)，总共打出52张牌。考虑一张随机发的牌。它是心脏的可能性有多大？(答案：13/52=1/4。)。假设我看了看这张牌，但没有让你看，我告诉你它是一位女王。那么它是心脏的可能性有多大呢？(答案是：四分之一。)。一般来说，告诉你纸牌的价值不会改变花色的概率，因此价值和花色是独立的。我们也可以用交叉乘法边际概率来验证这一点：价值和花色的每一种组合都有1/52的机会被处理(在相当混乱的一副牌中)。请注意，1/52正好是任何一个花色的边际概率(1/4)乘以任何一个值的边际概率(1/13)。

在其他环境中，当我们构建关于不止一个参数的信念的数学描述时，独立性就会出现。我们将创建我们对一个参数的信念的数学描述，以及我们对另一个参数的信念的另一个数学描述。然后，为了描述我们对参数组合的看法，我们通常会假设它们是独立的，然后简单地将单独的可信度相乘，以确定联合可信度。

## 4.5 习题

在https://sites.google.com/site/doingbayesiandataanalysis/上寻找更多练习。

练习4.1。[目的：在处理一个计算条件概率的具体例子的同时，获得R中应用函数的经验。]。来自Ta b l e 4的眼睛颜色头发颜色数据。1内置于R中，作为名为HairEyeColor的数组。这个数组是男性和女性眼睛和头发颜色的频率。在R中运行以下代码：

![](https://gitee.com/XiShanSnow/imagebed/raw/master/images/articles/spatialPresent_20210426222154_fe.webp)

在你的写作中，包括上面的每一行及其结果。解释每一行的作用(比行内注释更详细一些)。通过计算给出棕色眼睛的头发颜色的概率和给出棕色头发的眼睛颜色的概率来扩展上面的命令。

练习4.2。[目的：给你一些R中随机数生成的经验]。修改第4.5节RunningProportion.R中的掷硬币程序，以模拟p(H)=0.8的有偏硬币。修改打印中参照线的高度以匹配p(H)。注释您的代码。提示：阅读示例命令的帮助。

练习4.3。[目的：了解4.2.1.2节中提供的逻辑示例。]。确定从洗过的皮诺奇牌中抽到10分的确切概率。(在一副皮诺奇牌中，有48张牌。共有六个值：9、10、Jack、Queen、King、Ace。每套标准的四套西装中，每种价值都有两份复印件：红心、方块、梅花、黑桃。)。(甲)得10分的概率是多少？(B)得10分或杰克的概率是多少？

练习4.4。[目的：让您亲身体验R和微积分中的简单概率密度函数，并再次强调密度函数的值可以大于1。]。考虑周长为[0，1]的微调器。假设旋转器被倾斜、磁化或以某种方式弯曲，使得它是偏置的，并且它的概率密度函数是p(X)=6x(1−x)在区间x∈[0，1]上。(A)调整程序IntegralOfDensity.R绘制该密度函数并近似其积分。注释您的代码。请注意，仅考虑区间[0，1]内的x值。提示：您可以省略关于均值和sdval的前两行，因为这些参数值只与正态分布有关。然后将xlow=0和xhigh=1，a n d s e t dx设置为某个较小的值。(B)用微积分导出精确积分。提示：请参阅示例方程式4.7。(C)此函数是否满足公式4.3？(D)通过检查图形，p(X)的最大值是多少？

练习4.5。目的：让你用一条正态曲线来描述信仰。知道μ和σ之间的正常曲线下的面积也很方便。]。

(A)修改IntegralOfDensity.R中的代码，以(近似)确定从x=μ−σ到x=μ+σ的正态曲线下的概率质量。注释您的代码。提示：只需适当更改xlow和xhigh，并更改文本位置，使该区域仍显示在绘图中。

(B)现在使用正态曲线来描述以下信念。假设你认为女性的身高呈钟形分布，以162厘米为中心，大约三分之二的女性身高在147厘米到177厘米之间。μ和σ参数值应该是什么？

练习4.6。[目的：认识并处理这样一个事实，即公式4.9可以求解联合概率，这将是发展贝叶斯定理的关键。]。对学龄儿童最喜欢的食物进行了调查。在全部样本中，20%是一年级学生，20%是六年级学生，60%是11年级学生。对于每个年级，下表显示了选择三种食物中每一种作为自己最喜欢的食物的受访者比例：

<img src="https://gitee.com/XiShanSnow/imagebed/raw/master/images/articles/spatialPresent_20210426222311_28.webp" style="zoom:50%;" />

根据这些信息，构建一个等级和喜爱食物的联合概率表。另外，说出等级和喜爱的食物是否独立，以及你是如何确定答案的。提示：你被给予p(等级)和p(食物|等级)。你需要确定p(等级，食物)。