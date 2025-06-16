### A 函数和极限
1. 实数
	- 无尽小数的等同关系：
		- $（E_{1}）-0.000\dots=+0.000\dots$
		- $(E_{2}) \pm b_{0}.b_{1}b_{2}\dots b_{p}999\dots=\pm b_{0}.b_{1}b_{2}\dots (b_{p}+1)000\dots;$ $(其中b_{p}<9）$ 
	- 大小比较：逐个位数比较
	- 实数的连续性（$\mathbb{R}:\pm \times /;\lim_{  }\pm \times /$）
		- 确界原理
			- 上界：$\exists L\in \mathbb{R},\forall x\in E$ 使得 $L\geq x$ 则称集合 E 有上界
			- 上确界：实数M 满足（i）$\forall x\in E, x\leq M$  (ii) $\forall M^ `<M,\exists x\in E,x>M^`$ 则称 M 为 E 的上确界，记为 $supE$
			- 下界，下确界同理，下确界记为 $infE$
			- **确界原理**：$\mathbb{R}$ 的任何一个非空有上界的子集 D 在 $\mathbb{R}$ 中有上确界
		- 单调收敛原理
		- Cauchy 收敛原理——极限不存在怎么描述？
	- 数域：有理数域 $Q$ 是最小的数域，$Q+\left\{ a_{1},\dots,a_{n} \right\}$ 也是一个数域
2. 极限
	- $\epsilon-N语言$ 
		- 必要性？$\lim_{ n \to \infty }\sqrt[n]{ n }$   Stirling 公式 ......——有一把标尺定义极限
		- 定义：$\lim_{ n \to \infty }a_{n}=a$ 的描述
			- $Def: 设 a_{n}\in \mathbb{R},\ s.t.\forall \epsilon>0,\ \exists N\in \mathbb{N}(\epsilon),\ s.t.\ \forall n\geq N$   
				有 $\left| a_{n}-a \right|<\epsilon$，则称序列 $\left\{ a_{n} \right\}$ 有 **极限**
				否则，则称序列**发散**
			- Eg：证明 $\lim_{ n \to \infty }\sqrt[n]{ n }=1$ 
				- 取 $n=\left[ \frac{2}{\epsilon^2} \right]+1$
				- $n> \frac{2}{\epsilon^2}\implies n<1+\frac{n(n+1)}{2}\epsilon^2<(1+\epsilon)^n\implies \sqrt[n]{ n }-1<\epsilon$
				- 由 $\epsilon$ 的任意性可得：$\lim_{ n \to \infty }\sqrt[n]{ n }=1$ 
			- **注：证明的本质是用 $\epsilon 表示N$ 
		- 注：不等式与极限求解（伯努利不等式、AGM 不等式...）
			- Eg 1: $\left( 1+\frac{1}{\sqrt[]{ n }} \right)^n>1+\sqrt[]{ n }>\sqrt[]{ n }\implies\left( 1+\frac{1}{\sqrt[]{ n }} \right)^2>\sqrt[n]{ n }$ 
			- Eg 2: $\sqrt[n]{ n }=\sqrt[n]{ \sqrt[]{ n }\sqrt[]{ n }1\dots\\1}<\dots$ 
	- 三明治原理
		- Proof：$N=max\left\{ N_{1},N_{2} \right\},a-\epsilon\leq y_{n}\leq x_{n}\leq z_{n}<a+\epsilon$ 
	- 基本性质
		- 极限的四则运算—习题 (i) 可以加减项，绝对值不等式证明（ii）无穷小序列
			- Tips 1：一定要先验证极限存在 (如： $\frac{0}{0}\quad \frac{\infty}{\infty}$）
			- Tips 2：只限于有限次四则运算
				- 思考题：$\sum_{i=n+1}^{2n}\frac{1}{i}\quad \prod_{i=2}^{N}1-\frac{1}{i^2}$    ($ln2\quad\frac{1}{2}$)
			- Stoltz 定理：离散的洛必达法则（列出上下数列）
				- $\lim_{ n \to \infty }a_{n}=a \implies \lim_{ n \to \infty }\frac{a_{n}+\dots+a_{n}}{n}$ （柯西命题）
				- 托布利兹数 $\lim_{ n \to \infty }\sum_{k=1}^{n}t_{nk}=1\quad\forall k,\lim_{ n \to \infty }t_{nk}=0$
				- $若\lim_{ n \to \infty }a_{n}=a,\lim_{ n \to \infty }\sum_{k=1}^{n}t_{nk}a_{k}=a$ 
				- 令 $a_{k}=\frac{y_{k}-y_{k-1}}{x_{k}-x_{k-1}},t_{nk}=\frac{x_{k}-x_{k-1}}{x_{n}}$ 
		- $\lim_{ n \to \infty }a_{n}=a$ 可推出{$a_{n}$}有界；反之则不行
			- Proof: 取 $\epsilon=1\implies \forall n>N,\left| a_{n} \right|<1+\left| a \right|$
				   $K=max\left\{ a_{1},\dots ,a_{n},\left| a \right|+1 \right\}$
				   显然有 $K\geq \left| a_{n} \right|$
	- 单调收敛原理
		- 递增数列{$x_{n}$}收敛的充分必要条件是他有上界（对于任意 $x_{n}$ 均成立）（下界相反即可）
		- 用法：前后项来判断数列单调性，归纳法 （不动点） or显然得到有界，从而得到存在极限。对递推式 $x_{n+1}=f(x_{n})$ 两侧取极限即可得到极限 a
	- e 的定义 (e= $\lim_{ n \to \infty }\left( 1+\frac{1}{n} \right)^{n}$ )
		- 极限存在：
			- 单调递增 $a_{n}=\prod_{i=1}^{n}\frac{n+1}{n}\times 1\leq \frac{\frac{n+1}{n}*n+1}{n+1}^{n+1}=a_{n+1}$
			- 有上界 $\lim_{ n \to \infty }\left( 1+\frac{1}{n} \right)^{n}=\lim_{ n \to \infty }1+1+\sum_{k=2}^{n}\frac{1}{k!}\prod_{i=1}^{k-1}\left( 1-\frac{1}{i} \right)$    < $\lim_{ n \to \infty }1+1+\sum_{k=2}^{n}\frac{1}{k!}<\lim_{ n \to \infty }1+\sum_{i=1}^{n}\frac{1}{2^{i}}=3$ 
				- 注：该方法不能证明 e 严格小于 3，如要证明则需证明 $\lim_{ n \to \infty }\left( 1+\frac{1}{n} \right)^{n}=\lim_{ n \to \infty }1+1+\sum_{k=2}^{n}\frac{1}{k!}$
		- 2<e<3
		- e= $\lim_{ n \to \infty }1+1+\sum_{k=2}^{n}\frac{1}{k!}$ 求极限的先后性问题
			- $0\leq e-b_{n}\leq\left( \frac{1}{n!*n} \right)$
			- 证明 e 是无理数
		- $\left( 1+\frac{1}{n} \right)^{n}<e<\left( 1+\frac{1}{n} \right)^{n+1}$ AG不等式放缩
		- $x^{y}=y^{x}$ 的解
		- Stirling 公式弱版本：$\lim_{ n \to \infty }\left( \frac{\sqrt[n]{ n! }}{n} \right)=\frac{1}{e}$ 
			- Stirling 公式：$\lim_{ n \to \infty }\left( \frac{e^{n}n!}{n^{n}\sqrt[]{ n }} \right)=\sqrt[]{ 2\pi }$ 
		- $\lim_{ n \to \infty }(\sum_{i=1}^{n}\frac{1}{i})-\ln n=\gamma$ （ln x+1<x）
	- 序列与子序列的极限
		- 若序列 $\left\{ a_{n} \right\}$ 收敛于 $a$ ，则其任何子序列 $a_{n_{k}}$ 都收敛于 $a$
			- 可以利用这个＋反证法：如一个序列的子序列收敛的极限不同，则该序列极限不存在
		- （Bolzano-Weierstrass）$x_{n}$ 是**有界序列**，则它具有一个收敛的子序列
	- 柯西收敛原理
		- 柯西序列：$\forall \epsilon>0,\exists N\in \mathbb{N}\quad s.t.\forall m,n>N时，有|x_{m}-x_{n}|<\epsilon$ 则称这个序列为柯西序列
		- 柯西收敛原理：序列{$x_{n}$}收敛 $\iff$ 序列{$x_{n}$}是柯西序列（有一个聚集的趋势）（往往我们不用提前知道极限为何，来证明存在极限）
			 - 充分性：$\forall n>N,|a_{n}-a|<\epsilon/2$
		$\implies |a_{m}-a_{n}|=|(a_{m}-a)-(a_{n}-a)|\leq|(a_{m}-a)|+|(a_{n}-a)|<\epsilon$  
			 必要性：设 $x_{n_{k}}\to a\quad \forall m,n>N,|a_{m}-a_{n}|<\epsilon/2$ 
				 又 $\forall k>N_{1},|a_{n_{k}}-a|<\epsilon/2$
				 取 $n>max\left\{ N,N_{1} \right\},|a_{n}-a|<\epsilon$ 
		- 由此可以得到一个序列收敛的充分必要条件：
			- $\forall \epsilon>0,\exists N\in \mathbb{N}s.t.\forall n>N和p\in \mathbb{N},|a_{n+p}-a_{n}|<\epsilon$ 
		- Eg：
			- $a_{n}=\sum_{i=1}^{n}\frac{1}{i}$
			- （压缩映照原理）设 f 在【a，b】上有定义，且满足 1）$f([a,b])\subset[a,b]$ 2) $\exists q\in(0,1)s.t.|f(x)-f(y)|\leq q|x-y|(\forall x,y\in[a,b])$ 则 $\exists 唯一的c\in[a,b]s.t.f(c)=c$ 
2.  函数的极限
	- Question？$e^{x}$ 的定义？初等函数的连续性？$\to$ 函数的连续性和极限
	- $e^{x}:=\lim_{ n \to \infty }e^{p_{n}},其中p_{n}\in Q,\lim_{ n \to \infty }p_{n}=x$ 
		- 唯一性需说明，是否存在一个 $q_{n}$ 两个极限相等，同时 $e^{x}$ 的极限相同
		- $\left| a^{p}-a^{q} \right|\leq a^{q}(a-1)|p-q|$ 
	- 序列式定义（Heine 归结原理）： $\lim_{ x \to \ x_{0}}f(x)=l \iff \forall \left\{ x_{n} \right\},x_{n}\neq x_{0},\lim_{ n \to \infty }x_{n}=x_{0},有\lim_{ x \to x_{0} }f(x_{n})=l$
		- 一定是任意序列
			- 利用这点可以反证函数极限不存在
		- 结合序列极限可以得
			- 极限唯一性
			- 夹逼定理
			- 四则运算（直接用极限的四则运算）
			- 复合函数 $\left\{ f(x_{n}) \right\}\subset \breve{U}(b)$ 
	- $\epsilon-\delta$ 定义： 设 $f在\left\{ x:0<|x-x_{0}|<\delta_{0} \right\}$ 若 $\exists l\in \mathbb{R}\forall \epsilon>0,\exists \delta>0s.t.|f(x)-l|<\epsilon$ 则称 $\lim_{ x \to x_{0} }f(x)=l$ （即 $\lim_{ n \to \infty }f(x)=f(\lim_{ n \to \infty }x)$） 
		- $f在\breve{U}(x_{0},\delta)局部有界、局部保号、保序$
		- 四则运算（都是针对在邻域内的性质，其他同序列极限）
		- 收敛定理 $\lim_{ x \to x_{0} }f(x)存在\iff \forall \epsilon>0,\exists \delta>0s.t.x,x^{\prime} \in B(x_{0},\delta),|f(x)-f(x^{\prime})<\epsilon|$
		- 无穷极限
			- 自变量趋向无穷 $\exists \Delta\in R,s.t.\forall x>\Delta,f(x)\dots$
			- 函数值趋向无穷 $\dots,s.t.x\in U,f(x)>E$ 
		- 左极限 $\to x\in(a-\delta,a)$ ，右极限同理
		- 闭区间上函数连续性是基于实数的完备性
		- 注 1：极限不需要在 $x_{0}$ 处有定义
		- 注 2：区分 f 在一点连续和 f 在定义域上连续
		- 注 3：邻域上有极限 $\neq x_{0}$ 上有极限
			- Eg $f(x)=\sin \frac{1}{x}\quad f(x)=xD(x)\quad \mathcal{R}(x)在无理数点有极限$ 
	- 无穷小量代换
		- 本质是用简单的无穷小量代替复杂的，但是要保证略去的是更高阶的小量
		- 必须是商形式，所以分式和应当通分
3. 函数的连续
	- 连续的定义：$\lim_{ x \to x_{0} }f(x)=f(x_{0})$ 
		- 连续的性质可以将函数值的关系，拓展到邻域 $f(x_{0})<g(x_{0})\to \exists \delta,\forall x\in \breve{U}(x_{0},\delta),f(x)<g(x)$ 
		- 复合函数连续性 $|g(y)-g(y_{0})|<\epsilon,(|y-y_{0}|<\sigma)\quad |y-y_{0}|<\sigma,(|x-x_{0}|<\delta)$ 
	- 间断点分类
		- 1）左右极限存在但不相等
		- 2）左右极限相等但不等于该点函数值（可去间断点）$\frac{\sin x}{x} \mathcal{R}(x)$ 
		- 3）左/右极限至少一个不存在 $D(x)$
	- 闭区间连续函数性质
		- 有界性
		- 最值可取
		- 介值定理（闭区间套）
			- 压缩映射原理
		- 一致连续性（研究闭区间的收敛数列，收敛性＋连续）
			- 定义 $\forall \epsilon>0,\exists \delta>0,s.t.\forall|x-x_{0}|<\delta,|f(x)-f(x_{0})|<\epsilon$
	-  单调函数
		- 定理 1：如果 f 在区间 I 上连续那么 $J=f(I)=\left\{ f(x)|x\in I \right\}$ 也是一个区间
		- 定理 2：对于单调函数，$f在I上连续\iff f(I)是一个区间$ 
		- 定理 3：设 $f在区间I上严格单调且连续，则反函数$$g=f^{-1}在区间J=f(I)上严格单调且连续$ 
	- 研究几类函数
		- $|a^{x}-a^{x_{0}}|\leq a^{x_{0}}(a-1)|x-x_{0}|$ （把指数逼近转化为序列逼近）
			- $\forall r\in \mathbb{Q},|r|<1\quad |a^{r}|=(a^{m})^{1/n}\leq (a-1)|r|+1$  
			- $\forall x\in \mathbb{R},a^{x}=\lim_{ n \to \infty }a^{P_{n}}(P_{n}\to x)$ 
			- $|a^{x}-a^{x_{0}}|\leq \lim_{ n \to \infty }a^{x_{0}}(a-1)|p_n-q_n|\quad (\lim q_{n}=\lim p_{n}=x_{0})$  
		- $|\sin x-\sin x_{0}|=2|\sin \frac{x-x_{0}}{2}\cos\frac{x+x_{0}}{2}|\leq 2|\sin\frac{x-x_{0}}{2}|\leq|x-x_{0}|$  
	- 几个重要极限
		- $\lim_{ x \to 0 } \frac{\sin x}{x}=1\quad \lim_{ x \to \infty }\left( 1+\frac{1}{x} \right)^{x}=e\quad \lim_{ \alpha \to 0 } \frac{\log_{b}(1+\alpha )}{\alpha}=\frac{1}{\ln b}$
		- $\lim_{ \alpha \to 0 } \frac{b^{ \alpha }-1}{\alpha}=\ln b\quad \lim_{ \alpha \to 0 }\frac{(1+\alpha)^{\mu}-1}{\alpha}=\mu$ 
		- 
		- 迭代关系
#### 解题方法
1. 数列极限
	- 变量代换、适当放大（基本不等式、二项式定理）
	- 截断控制法：分析趋势、配平、截断（控制条件）、部分放大（凑形式）
	- 两个工具：
		- 夹逼定理（变换形式）
		- 单调收敛原理（作商、做差、找递推式、取极限）
		- 截断控制 （cauchy 命题+均值不等式/引入无穷小序列）
		- Stolz 公式
	- 柯西收敛准则（寻找发散子列）
	- Stolz 定理：有时候要调整一下形式再使用
		- 反向构造（从差分极限得到项的极限）
	- 先判断数列的收敛方向，单调 or 跳跃
	- 观察形式，对数列进行组合得到一个可以比较的形式/找到递推式
	- 注意数列的 n 只能是整数
	- 迭代收敛
		- 如果迭代函数为增函数，数列为单调的
		- 如果为减函数，则为奇偶交替单调
		- 找出不动点，判断单调性，判断与不动点关系
	- 对数不等式 $\left( 1+\frac{1}{n} \right)^{n}<e<\left( 1+\frac{1}{n} \right)^{n+1}\quad \frac{1}{n+1}<\ln\left( 1+\frac{1}{n} \right)< \frac{1}{n}$ 
	- 几个重要极限
	- 根号的裂项别忘了
2. 函数极限
	- 和数列极限的区别是，要先划定一个 $\delta$ 范围
	- 指数转化为对数求极限
	- $0^{0}$ 形式取对数等价无穷小
	- $1^{\infty}$ 形式要凑 $\left( 1+\frac{1}{n} \right)^{n}$ 的形式，先取 e 的极限，再分析指数
	- 多项式连乘可以考虑取对数变换成连加分析
	- 证明极限发散要用归结原理，即选择两个子序列，收敛不一致
1. 闭区间函数性质
	- 一定要结合介值定理，有界性综合去考虑（控制函数的范围（上下界））
	- 极限的上的介值定理一定要**给定一个区间或限制一个大于 N 的序列**再说明
	- 不是闭区间，但是端点限制的，可以端点附近分析+闭区间定理/构造辅助函数在闭区间分析
	- 一致连续性从控制 $\epsilon$ 从而控制 $\delta$ 找出不满足的情况
2. 微小区间（有理数上的性质/邻域的性质）都可以利用数列的各种方法进行推广 （闭区间套（也可以归结为有界性）、极限有界性...）
3. $有界\implies有收敛子序列\implies根据题目条件推广全部收敛$
### B 微积分基本概念
1. 导数
	- $f^{\prime}(x)=\lim_{ h \to 0 } \frac{f(x+h)-f(x)}{h}$ 
	- 由连续存在：导数存在的充分必要条件是左右两侧导数存在且相等
	- $f(x)在x_{0}可导\to 在x_{0}处连续$ （反命题不一定成立）$\lim_{ x \to x_{0} }f(x)=\lim_{ h \to 0 }f(x_{0}+h)=\lim_{ h \to 0 }f(x_{0})+f^{\prime}(x)h=f(x_{0})$ 
	- 反函数求导：$y=\varphi(x),\psi=\varphi^{-1}\to \psi(y_{0})=\frac{1}{\varphi(x_{0})}=\frac{1}{\varphi(\psi(y_{0}))}$ 
	- 参数求导：$y=\varphi(t),x=\psi(t)\to y=\varphi(\psi^{-1}(x))\to y^{\prime}=\frac{\varphi ^{\prime}(t)}{\psi ^{\prime}(t)}$ 
		- 注意高阶导数
	- 高阶导数（莱布尼茨公式）$(uv)^{(n)}=\sum_{k=0}^{n}C_{n}^{k}u^{(n-k)}v^{(k)}$ 
	- 罗尔定理：$设函数f在闭区间[a,b]连续，在(a,b)可导，并且满足f(a)=f(b)$ $则存在c\in(a,b),使得f^{\prime}(c)=0$ 
	- 拉格朗日中值定理：$设函数f在闭区间[a,b]连续，在(a,b)可导，则存在至少一个c\in(a,b)$ $使得f^{\prime}(c)=\frac{f(b)-f(a)}{b-a}$  
	- 有限增量公式：$设\theta=\frac{\xi-x_{0}}{x-x_{0}}\in(0,1),则\xi=x_{0}+\Delta x\cdot \theta,$ $f(x_{0}+\Delta x)=f(x_{0})+f^{\prime}(x_{0}+\Delta x\theta)\Delta x$
	- Darboux 定理
2. 定积分
	- 黎曼和
		- 闭区间 $[a,b]$ 的一个**分割**，指插入在 a 和 b 之间的有限个分点 $P:a=x_{0}<x_{1}<\cdots<x_{m}=b$
		- 记 $\Delta x_{i}=x_{i}-x_{i-1}$，把 $|P|=max\left\{ \Delta x_{1} ,\Delta x_{2},\cdots,\Delta x_{m}\right\}$ 称作分割 P 的**模
		- 记 $\xi_{i}\in[x_{i-1},x_{i}]$ 这 m 个数为 P 的一组**标志点**
		- 设函数在闭区间上有定义，则我们称 $\sigma(f,P,\xi)=\sum_{i=1}^{m}f(\xi_{i})\Delta x_{i}$ 为闭区间上的**黎曼和
	- 可积性
		- 设函数 $f$ 在闭区间 $[a,b]$ 上有定义，$I\in \mathbb{R}$，如果 $\forall \epsilon>0,\exists \delta>0,$$s.t.只要|P|<\delta,无论相应的标志点组\xi_{i}怎么选取，都有$ $|\sigma(f,P,\xi)-I|<\epsilon$ 我们就说 $f$ **可积**（对应达布上下和和一致连续）
		- 1）连续函数，有界且间断点有限的函数，单调函数
		- 2）$\lim_{|\Delta|\to0}\sum_{i=1}^{n}\omega_{i}|x_{i+1}-x_{i}|=0$
		- 3）f 的不连续点零测
	- 从可积性得到有界性
	- 微积分中值定理
		- $若m\leq f(x)\leq M,则m(b-a)\leq \int_{a}^{b} f(x) \, d\leq M(b-a)$
		- $同时若f在[a,b]上连续，可以找到一点c，f(c)=\frac{1}{b-a}\int_{a}^{b} f(x) \, dx$
	- 牛顿-莱布尼茨公式
		- 题设：设 $f(x)在[a,b]上连续，且存在一个F(x)在[a,b]连续，在(a,b)可导$ $满足F^{\prime}(x)=f(x)$ 
		- 证明：$f(x)可积并且\int_{a}^{b} f(x) \, dx=F(b)-F(a)$
			- $RHS=\sum_{i=1}^{m}F(x_{i})-F(x_{i-1})=\sum_{i=1}^{m}f(\eta_{i})(x_{i}-x_{i-1})$ （拉格朗日中值定理）$\implies=\sigma(f,P,\eta)$
		$LHS=\sigma(f,P,\xi)\to L-R=\sum_{i=1}^{m}(f(\xi_{i})-f(\eta_{i}))(x_{i}-x_{i-1})$
			- 由一致连续性 $\exists\delta>0,s.t.\forall |u-v|<\delta,|f(u)-f(v)|< \frac{\epsilon}{b-a}$
			- $L-R< \frac{\epsilon}{b-a}\sum_{i=1}^{m}\Delta x_{i}=\epsilon$
			- 证毕
	- 可积≠有原函数 （对于不连续的情况）
	- 连续函数一定有原函数
	- 变上限积分函数
	- 定积分是一个求极限过程
4. 积分计算
	1. 定积分
		- 不定积分＋牛顿莱布尼茨公式
		- 几何含义、周期性
		- 定义域问题
5. 积分中值定理
	1. 第一积分中值定理
	2. 第二积分中值定理 $f\in R[a,b],g在[a,b]上单调$ $\exists \xi\in[a,b]s.t.\quad \int_{a}^{b} f(x)g(x)\,dx=g(a)\int_{a}^{\xi} f(x) \, dx+g(b)\int_{\xi}^{b} f(x) \, dx$
#### 解题方法
##### 导数
1. 区分导函数在某点的单侧极限和在某点的单侧导函数
2. 莱布尼茨公式，求 n 阶导数找递推式

##### 定积分
1. 对称性的考虑
	1. $\int_{a}^{b} f(x) \, dx =\int_{a}^{b}f(a+b-x)  \, dx$
	2. $\int_{0}^{a} f(x) \, dx=2\int_{0}^{a/2} f(x) \, dx\quad (f(x)=f(a-x))$
	3. $\int_{0}^{a} f(x) \, dx =\int_{0}^{a/2} g(x) \, dx \quad g(x)=f(x)+f(a-x)$ 
2. 估计定积分（极限＋积分）
	1. 取微小区间分段进行分析
	2. 分部积分再算
	3. 面对抽象函数，往往用积分中值定理将函数从积分抽象出来（黎曼勒贝格引理）
3. 积分不等式
### C 利用导数研究函数
#### 1 中值定理
- 罗尔定理：若 $f(x)\in C[a,b],D(a,b),f(a)=f(b)$，则 $\exists \xi,s.t.f^{\prime}(\xi)=0$ （闭区间连续函数存在最值）
- 拉格朗日中值定理：若 $f(x)\in C[a,b],D(a,b)$, 则 $\exists \xi\in(a,b),s.t.f^{\prime}(\xi)=\frac{f(b)-f(a)}{b-a}$
	- 证明：$\frac{f(b)-f(a)}{b-a}=k\implies F(x)=f(x)-kx\quad F(b)=F(a)\implies F^{\prime}(\xi)=0$ 
- 柯西中值定理：若 $f(x)，g(x)\in C[a,b],D(a,b)\quad g^{\prime}(x)\neq 0$, 则 $\exists \xi\in(a,b),s.t. \frac{f^{\prime}(\xi)}{g^{\prime}(\xi)}=\frac{f(b)-f(a)}{g(b)-g(a)}$
	- 证明：$\frac{f(b)-f(a)}{g(b)-g(a)}=k\implies F(x)=f(x)-kg(x)\quad F(a)=F(b)$
	- 可以从参数方程（坐标变换）去理解：$x=f(t),\quad y=g(t)$ $F(x)=f(g^{-1}(x))\implies F^{\prime}(\xi)=\frac{f^{\prime}(\tilde{\xi})}{g^{\prime}(\tilde{\xi})}=\frac{f(b)-f(a)}{g(b)-g(a)}$
- 达布中值定理
#### 2 洛必达法则和泰勒公式
- 洛必达法则 
- 小 o 余项的泰勒公式$f(x)=f(a)+\sum_{i=1}^{n} \frac{f^{(i)}(a)}{i!}(x-a)^{i}+o((x-a)^{n})=P(x)+o((x-a)^{n})$）
	- 唯一性 （局部的唯一性）
	- 存在性：若 $\varphi(a)=\varphi ^{\prime}(a)=\cdots=\varphi^{(n)}(a)=0$ $\implies \varphi(x)=o((x-a)^{n})$，令 $\varphi(x)=f(x)-P(x)$
- 极值充分条件：
	- 若 $x\in U(x_{0},\eta),f^{\prime}(x_{0})=\cdots=f^{(n-1)}(x_{0})=0,f^{(n)}(x_{0})\neq 0$
	- 则（1）若 n 为偶数，则 f 在 $x_{0}$ 处取得严格最值；（2）若 n 为奇数，则 $x_{0}$ 不是 f 极值点
- 有限增量泰勒公式
	- 为了方便估计余项，我们引入有限增量 $f(x)=P_{n}(x)+R_{n+1}(x)$
	- 拉格朗日余项：$R_{n+1}(x)=\frac{f^{(n+1)}(\xi)}{(n+1)!}(x-a)^{n+1}$
	- 积分余项：$R_{n+1}(x)=\frac{(x-a)^{n+1}}{n!}\int_{0}^{1} (1-t)^{n}f^{(n+1)}(a+t(x-a)) \, dt$
	- 柯西型余项：对上式用积分中值定理 $R_{n+1}(x)=\frac{(1-\theta)^{n}}{n!}f^{(n+1)}(a+\theta(x-a))(x-a)^{n+1}$
#### 3 凹凸性
设函数 $f$ 在区间 $I$ 有定义，如果 $\forall x_{1},x_{2}\in I,x_{1}<x_{2}\quad \forall \alpha_{1},\alpha_{2}\geq 0,\alpha_{1}+\alpha_{2}=1$ 都有 $f(\alpha_{1}x_{1}+\alpha_{2}x_{2})\leq \alpha_{1}f(x_{1})+\alpha_{2}f(x_{2})$，则称该函数为**下凸函数**
- 性质（以下几个性质等价）
	- $f(x)$ 在区间 $I$ 下凸
	- $\forall x_{1}<x<x_{2},f(x)\leq \frac{x_{2}-x}{x_{2}-x_{1}}f(x_{1})+\frac{x-x_{1}}{x_{2}-x_{1}}f(x_{2})$
	- $\frac{f(x)-f(x_{1})}{x-x_{1}}\leq \frac{f(x_{2})-f(x_{1})}{x_{2}-x_{1}}\leq \frac{f(x_{2})-f(x)}{x_{2}-x}$
- 琴生不等式
	- 设 $x_{1},\cdots ,x_{m}\in I,\alpha_{1},\cdots,\alpha_{m}\geq 0,\sum_{i=1}^{m}\alpha_{i}=1$，若 f 是在区间 $I$ 的下凸函数，则有 $f\left( \sum_{i=1}^{m}\alpha_{i}x_{i} \right)\leq \sum_{i=1}^{m}\alpha_{i}f(x_{i})$
#### 解题方法
中值定理（找 $\xi\,s.t.\,F(\xi,a,b,x,f)=0$）
1. 待定参数法
	1. 尝试对 F 进行参数分离 $F_{1}(\xi,f)=F_{2}(a,b,x,f)$
	2. 令 $\lambda=F_{2}(a,b,x,f)$ 并进行代数变形
	3. 选择合适的 a/b/x 作为中间变量构造辅助函数
	4. 运用中值定理
2. 若不能分离，则尝试凑微分法
	1. 尝试凑出全微分，然后用罗尔中值定理
### D 多元函数微分学
#### 1 多元极限
##### 1.1 定义
设 $D\subset \mathbb{R}^{m},a=(a_{1},\cdots,a_{m})$ 是 $D$ 的聚点，$m$ 元函数 $f$ 在 $U(a,\eta)\cap D$ 上有定义，$\forall \epsilon>0,\exists \delta>0,s.t.x \in D,\quad 0<||x-a||<\delta 有 |f(x)-A|<\epsilon$ 那我们就称：当 x 沿集合 D 趋近于 a 是，函数极限为 $A$
- 注：要想保证 $\lim_{ (x,y) \to (x_{0},y_{0}) }f(x,y)$ 收敛，就必须使得对于任意接近的集合 D 得到的极限都相等
##### 1.2 收敛极限计算
1. 夹逼原理，设法将函数值控制在一个值上
2. 整体换元，如果二元可以组合为一元，可以采用一元极限
3. 极坐标换元，对称性较好时，可以用这个大大简化问题（夹逼时）
##### 1.3 发散极限判定
**多路径接近法**，采用不同的接近路径集合 D，导出函数极限不同
#### 2 闭区域连续函数的性质
#### 3 多元微分
##### 3.1 方向导数、偏导数和全微分
方向导数：对于 $\boldsymbol{e}=(\cos \theta,\sin \theta)$，定义该方向的导数 $\partial_{e}f(x_{0},y_{0})=\lim_{ t \to 0 } \frac{f(x_{0}+t\cos \theta,y_{0}+t\sin \theta)-f(x_{0},y_{0})}{t}$

偏导数：则是对于 $\boldsymbol{e}_{x}=(1,0),\boldsymbol{e}_{y}=(0,1)$ 而言，故可以得到 $\partial_x f (x_{0},y_{0})=\lim_{ h \to 0 } \frac{f(x_{0}+h,y_{0})-f(x_{0},y_{0})}{h}$
注意要先取定一个值，再取极限

全微分：设 $f(x,y)$ 在 $(x_{0},y_{0})$ 附近有定义，如果存在实数 $A,B$ 使得 $\Delta f=f(x_{0}+h,y_{0}+k)-f(x_{0},y_{0})=Ah+Bk+o(\sqrt[]{ h^{2}+ k^{2}})$，则称 $f(x,y)$ 在 $(x_{0},y_{0})$**可微**。其**全微分**记为 $df=Adx+Bdy$

##### 3.2 可微、连续、可偏导的关系
1. 如果 $f(x,y)$ 在点 $(x_{0},y_{0})$ 处可微，那么 $f(x,y)$ 在点 $(x_{0},y_{0})$ 处连续
2. 如果 $f(x,y)$ 在点 $(x_{0},y_{0})$ 处可微，那么 $f(x,y)$ 在点 $(x_{0},y_{0})$ 处的各方向导数都存在，并且 $A=f_{x}(x_{0},y_{0}),\quad B=f_{y}(x_{0},y_{0})$
3. 如果偏导数在 $(x_{0},y_{0})$ 处连续，那么 $f(x,y)$ 在点 $(x_{0},y_{0})$ 处可微


若要证明可微性与否：
1. 从定义，在 $\partial_xf,\partial_yf$ 存在的前提下，计算 $\lim_{ (\Delta x,\Delta y) \to (0,0)} \frac{f(x_{0}+\Delta x,y_{0}+\Delta y)-f(x_{0},y_{0})-\partial_xf(x_{0},y_{0})\Delta x-\partial_y f(x_{0},y_{0})\Delta y }{\sqrt[]{ \Delta x^{2}+\Delta y^{2} }}$ 如果收敛且为 0，则可微，反之则不可微
2. 从必要条件判定，若偏导数不存在/在 $(x_{0},y_{0})$ 不连续，则不可微

##### 3.3 几何图像

切平面和法向量：
考虑参数方程 （对应直线） $x=\varphi(t),\quad y=\psi(t),\quad z=\omega(t)$
于是有恒等式 $F(\varphi,\psi,\omega)=0$
对 t 求导数得 $F_{x}\varphi ^{\prime}(t_{0})+F_{y}\psi ^{\prime}(t_{0})+F_{z}\omega ^{\prime}(t_{0})=0$
法向量： $\boldsymbol{n}=(F_{x},F_{y},F_{z})$
切平面方程： $F_{x}(x-x_{0})+F_{y}(y-y_{0})+F_{z}(z-z_{0})=0$

对于二元参数方程（对应平面） $x=x(u,v),\quad y=y(u,v),\quad z=z(u,v)$
$\boldsymbol{n}=\boldsymbol{r}_{u}\times \boldsymbol{r}_{v}=\det \begin{pmatrix}\boldsymbol{i}&\boldsymbol{j}&\boldsymbol{k}\\x_{u}& y_{u}& z_{u}\\x_{v}& y_{v}& z_{v} \end{pmatrix}=\left( \frac{D(y,z)}{D(u,v)} ,\frac{D(z,x)}{D(u,v)},\frac{D(x,y)}{D(u,v)}\right)$

**多元函数可微**实际上是可以**用切平面近似**（代表了任意方向上的函数值增量都很小 $o(\sqrt[]{ \Delta x^{2}+\Delta y^{2} })$）


### E 重积分
> [!question] 平面区域的面积？
- 在重积分中怎么去定义一个区域的面积
- 自然的，要满足一些性质（可加性，单调性，非负性...）
实际上，面积就是一个映射 $(S:\Omega \subseteq \mathbb{R}^{2}\to \mathbb{R})$，称该映射为**测度**

#### Jordan 测度
思路：用有限长方体族从内部和外部逼近
令 $\mathcal{A}=\left\{ A_{1},\cdots A_{n} \right\}$ 且相互不交
定义 $M(\Omega,\mathcal{A})\equiv \sum_{A_{i}\cap \Omega\neq \phi}V(A_{i});\quad m(\Omega,\mathcal{A})\equiv \sum_{A_{i}\subseteq \Omega}V(A_{i})$
若 $inf_{\mathcal{A}}M(\Omega)=sup_{\mathcal{A}}m(\Omega)$，则称可求体积（Jordan 可测）

注：
- 直观理解，可求体积需要一个良好的边界
- 若边界由有限可求长集合/光滑曲线组成，则可求体积
- 可积性：可积一定有界
- 若 $f:D\to \mathbb{R}$ 在 $D$ 上分块连续，则 $f$ 在 $D$ 上可积

#### 积分中值定理
$D$ 为有界闭区域，且 $f:D\to \mathbb{R}$ 连续
则 $\exists(x_{0},y_{0})\in D ,s.t.\quad \iint_{D}f(x,y)dxdy=f(x_{0},y_{0})\iint_{D}dxdy$
利用多元函数介值定理（要求：连续，区域联通）

#### 三重积分计算
1. 根据图形，先固定（x，y）对 z 积分，再对 xy 进行二重积分
2. 先固定 z 在 z 的割面上进行二重积分，再对 z 积分

> [!example] 改变积分次序
> $$
> I=\int_{0}^{1}  \, dx \int_{0}^{1-x}  \, dy \int_{0}^{x+y} f(x,y,z) \, dz   
> $$
> 代数变换：（思想非常重要）
> $$
> I=\int_{0}^{1}  \, dz \int_{0}^{1}  \, dx \int_{0}^{1} f(x,y,z)\cdot\mathbb{1}_{\left\{ y\leq x \right\} }\cdot\mathbb{1}_{\left\{ z\leq x+y \right\} } \, dy  
> $$ 

#### 计算技巧
1. 对称性
2. 交换积分次序
3. 换元（主要把握旋转对称性，旋转之后体积微元不变）
4. 怎么把一个难算的单元积分，转化为重积分？

#### 应用

计算曲面和曲线的核心是**参数化**

计算曲面面积：z=f (x, y)，$S=\iint \Delta S^{*}$
$\Delta S^{*}=?$

利用切平面近似, 在 dx, dy 区域上用切平面面积微元近似
$$
z=z_{0}+\frac{ \partial f }{ \partial x } (x_{0},y_{0})(x-x_{0})+\frac{ \partial f }{ \partial y } (x_{0},y_{0})(y-y_{0})=0
$$
转化成点法式
$$
\frac{ \partial f }{ \partial x } (x_{0},y_{0})(x-x_{0})+\frac{ \partial f }{ \partial y } (x_{0},y_{0})(y-y_{0})-(z-z_{0})=0
$$
故
$$
\vec{n}=\left( -\frac{ \partial f }{ \partial x } (x_{0},y_{0}),-\frac{ \partial f }{ \partial y } (x_{0},y_{0}),1 \right)
$$
于是
$$
\Delta S^{*}=\frac{1}{|\cos \gamma|}dxdy=\frac{|\vec{n}||\vec{e}_{z}|}{|\vec{n}\cdot \vec{e}_{z}|}dxdy=\sqrt[]{ 1+|\nabla f(x,y)|^{2} }dxdy
$$
补充：
切平面的刻画？
切平面实际上是所有经过 (x, y) 点切线的集合

参数曲面怎么求面积？
$$
\begin{cases}
x=x(u,v) \\
y=y(u,v) \\
z=z(u,v)
\end{cases}
$$
想法：找经过（x, y, z）点的曲线，他们在此处的切向量应该可以张成整个切平面
曲线？参数化 $t\to(u_{0}+c_{1}t,v_{0}+c_{2}t)$
在平面上切向量 
$$
W=\frac{d}{dt} |_{t=0}(x(u,v),y(u,v),z(u,v)),\quad
\begin{cases}
 u=u_{0}+c_{1}t \\
v=v_{0}+c_{2}t
\end{cases}
$$

法向量
$$
\vec{n}=\vec{W}_{u}\times \vec{W}_{v}=A\vec{e}_{1}+B\vec{e}_{2}+C\vec{e}_{3}
$$
不妨设 $C\neq0$，那么又逆映射定理，在 (x, y) 的一个邻域，存在唯一的逆映射
$$
\begin{cases}
u=u(x,y) \\
v=v(x,y)
\end{cases}\implies z=z(u,v)=z(x,y)
$$
此时又变成第一种情况
$$
dS=\frac{1}{|\cos \gamma|}dxdy=\frac{\sqrt[]{ A^{2}+B^{2}+C^{2} }}{|C|}dxdy=\frac{\sqrt[]{ \cdots }}{|C|}\frac{ \partial (x,y) }{ \partial (u,v) }dudv=\sqrt[]{ \cdots } dudv
$$

（另解）**其实也可以**
$$
dS=|dr_{u}\times dr_{v}|=|\vec{W}_{u}\times \vec{W}_{v}|dudv=\sqrt[]{ A^{2}+B^{2}+C^{2} }dudv
$$

由于 A、B、C 比较难求，我们可以再化简 
$$
\begin{cases}
E=|\vec{W}_{u}|^{2} \\
F=\vec{W}_{u}\cdot \vec{W}_{v} \\
G=|\vec{W}_{v}|^{2} 
\end{cases}\implies dS=\sqrt[]{ EG-F^{2} }dudv
$$


#### 注意事项：
1. 可以利用重积分解决一些无法计算的定积分问题
2. 一定要画出积分区域，判断形状再积分
### F 曲线曲面积分
#### 曲线曲面积分
分类：
1. 第一型：对 ds 沿路径积分，
2. 第二型：对 dx, dy 沿相对位移积分
两种思路：
3. 把曲线、曲面参数化，化成对应自由度再积分
4. 利用斯托克斯公式或者高斯定理（小心奇点）（小心不光滑的边界点）

#### 曲面积分计算技巧 
第一型曲面积分：
通过参数化，把被积函数转化为两个自由度，曲面则按照上一章的在两个参数的平面上做投影，再利用重积分计算（$z=z(x,y)$ 和 $z=z(x(u,v),y(u,v))$ 两种情况）
- 还可以观察从曲面积分转化成第二型的，再用高斯公式

第二型曲面积分：
主要是转化为第一型曲面积分，再转化为重积分（或者利用高斯公式）
$$
\iint_{S}Pdydz+Qdzdx+Rdxdy=\iint_{S}(P,Q,R)\cdot \vec{n}_{S}\,dS
$$
如 $z=z(x,y)$
$$
=\iint_{S}(P,Q,R)\cdot \frac{(-z_{x},-z_{y},1)}{\sqrt[]{ \cdots }}\,\sqrt[]{ \cdots }dxdy
$$
另外两个参数的情况下
$$
=\iint_{S}(P,Q,R)\cdot d\vec{S}=\iint_{S}\vec{F}\cdot(\vec{W}_{u}\times \vec{W}_{v})\,dudv
$$


#### Green定理推广 ：散度定理
考虑 $F=(P(x,y),Q(x,y))$
$$
\oint_{L}-Qdx+Pdy=\oint_{L}(P,Q)\cdot(\tau_{2},-\tau_{1})ds=\iint_{S}\frac{ \partial P }{ \partial x } +\frac{ \partial Q }{ \partial y } dxdy
$$
可以得到 ($\vec{n}=(\tau_{2},-\tau_{1})=\left( \frac{dy}{ds},-\frac{dx}{ds} \right)$)
$$
\oint_{L}F(x,y)\cdot \vec{n}(x,y)ds=\iint_{S}\nabla \cdot Fdxdy
$$

散度定理的推广（n 维情况）
$$
\int_{\partial \Omega }\vec{F}\cdot \vec{n}\,dS=\int_{\Omega}div\vec{F}\,dV
$$

> [!example] 一个例子
> $$
> \oint_{L}\frac{ \partial u }{ \partial \vec{n} } ds=\iint_{S} \Delta udxdy
> $$

#### 更一般的散度定理（stokes 公式）

对于一个 n 维向量场
$$
\oint_{L}\vec{F}\cdot \vec{\tau}\,ds=\iint_{S}(curl\vec{F})\cdot \vec{n}\,dA
$$
> [!tip] curlF 的理解
> 1. CurlF 的方向给出了 F 局部旋转轴的方向
> 2. CurlF 的大小给出了局部旋转的强度

对于三维向量场
$$
curl\vec{F}=\det \begin{pmatrix}
\vec{e}_{1} & \vec{e}_{2} & \vec{e}_{3} \\
\frac{ \partial   }{ \partial x }  & \frac{ \partial   }{ \partial y }  & \frac{ \partial   }{ \partial z }  \\
P & Q & R
\end{pmatrix}
$$
> [!Note] 二维和三维的联系
> 对于二维向量场 $\vec{F}=(P(x,y),Q(x,y))$
> 我们将其扩充到三维 $\vec{\tilde{F}}=(P,Q,0)$
> 利用三维散度定理就可得到二维的斯托克斯定理

#### 散度旋度的数学理解
考虑一个初始位置为 $\boldsymbol{x}$ 的粒子，他在 t 时刻的位置为 $\Phi(\boldsymbol{x},t)$，并且它随着流速场 $\vec{F}$ 运动，满足以下方程
$$
\frac{d}{dt}\Phi(\boldsymbol{x},t)=\vec{F}(\Phi(\boldsymbol{x},t)),\quad \Phi(\boldsymbol{x},0)=\boldsymbol{x}
$$
$\Phi(\cdot,t)$ 给出了每个粒子初始位置到 t 时刻位置的映射，$\Phi(\boldsymbol{x},\cdot)$ 给出了向量场 F 的一条积分曲线

考虑 $\Phi$ 的雅可比矩阵（刻画了局部空间形变量），其演化方程可表示为
$$
\frac{d}{dt}\nabla_{\boldsymbol{x}}\Phi(\boldsymbol{x},t)=\nabla \vec{F}(\Phi)\nabla_{\boldsymbol{x}}\Phi(\boldsymbol{x},t),\quad \nabla_{\boldsymbol{x}}\Phi(\boldsymbol{x},0)=Id
$$

进一步，这个雅可比矩阵的行列式表示了局部的体积变化率，其演化方程可以表示为
$$
\frac{d}{dt}\det(\nabla_{\boldsymbol{x}}\Phi(\boldsymbol{x},t))=div\,\vec{F}(\Phi)\det(\nabla_{\boldsymbol{x}}\Phi(\boldsymbol{x},t)),\quad \det(\nabla_{\boldsymbol{x}}\Phi(\boldsymbol{x},0))=1
$$
由此可以看出 divF刻画了由 F定义的流映射导致空间膨胀/收缩的趋势大小,因此它对应了向量场 F 在局部上的发散/收拢的程度
推论：如果 $div\,F=0$ 则体积微元是不随时间变化的（刘维尔定理）

现在我们把注意力放在 F 上，由上式我们可以看出 F 的梯度可能有重要的意义，于是我们对 F 进行泰勒展开
$$
\vec{F}(\boldsymbol{x}_{0}+\Delta \boldsymbol{x})-\vec{F}(\boldsymbol{x}_{0})=\nabla \vec{F}(\boldsymbol{x}_{0})\Delta \boldsymbol{x}+o(|\Delta \boldsymbol{x}|)=D\Delta \boldsymbol{x}+W\Delta \boldsymbol{x}+o(|\Delta \boldsymbol{x}|)
$$
其中我们定义 D 为对称部分，W 为反对称部分
$$
A:=\nabla \vec{F}\implies D=\frac{1}{2}(A+A^{T}),\quad W=\frac{1}{2}(A-A^{T})
$$
然后我们可以导出
$$
\frac{d}{dt}|_{t=0}|\Phi(\boldsymbol{x}_{0}+\Delta \boldsymbol{x},t)-\Phi(\boldsymbol{x}_{0},t)|^{2}=2\Delta \boldsymbol{x}^{T}D \Delta \boldsymbol{x}+o(|\Delta \boldsymbol{x}|^{2})
$$
由于 D 是实对称矩阵，可以正交对角化，于是看到，其特征值就代表了局部流场拉伸和压缩的相对变化率，特征方向为拉伸和压缩的主方向。此外 $div\,F=div\,D=\sum \lambda_{i}$，所以 F 的散度刻画了总的变化率之和

$$
\vec{\omega}:=curl\,\vec{F}(\boldsymbol{x}_{0}),\quad \forall \Delta \boldsymbol{x},W\Delta \boldsymbol{x}=\frac{1}{2}\vec{\omega}\times \Delta \boldsymbol{x}
$$
![image.png](https://cdn.jsdelivr.net/gh/mashiromikuu/my-obsidian-library/20250406212318459.png)



曲面可定向的概念
曲面为 C 1 正则曲面，且存在连续的法向量场，则称**曲面可定向**

> [!faq] 曲线怎么定向？
> 1. 沿着 L 正向移动时，保证曲面 s 总在其左侧
> 2. 可以设定边界一点法向指向向曲面的向量 $\vec{b}$，则 $(\tau,b,n)$ 构成右手系


#### 积分与路径无关

要求**在单连通区域 D**, 有
$$
\oint_{L} Pdx+Qdy=0\quad \forall L\in D\iff \frac{ \partial P }{ \partial y } =\frac{ \partial Q }{ \partial x } \iff \exists V,dV=Pdx+Qdy
$$
其中第二个条件推第三个是需要单连通条件的，但是第三个推第二个无条件

一种求全微分的方法（已知 P，Q）
对于每个 y，我们都可以得到一个解
$$
u=\int P\,dx+C(y)=\varphi(x,y)+C(y)\implies C^{\prime}(y)=Q-\frac{ \partial \varphi }{ \partial y} 
$$

#### 积分因子

怎么找积分因子 $\mu$
$$
\mu Mdx+\mu Ndy\implies M\frac{ \partial \mu }{ \partial y } -N\frac{ \partial \mu }{ \partial x } =\mu\left( \frac{ \partial N }{ \partial y }  -\frac{ \partial M }{ \partial x } \right)
$$
考虑特殊情况：
1. 若 :
$$
\frac{\frac{ \partial N }{ \partial y } -\frac{ \partial M }{ \partial x } }{N}=f(x)
$$
则可找 $\mu=\mu(x)$
$$
\frac{d\mu}{dx}=-\mu f(x)
$$
2. 若全微分可以分解成两个部分，对于这两个部分都有一个积分因子
$$
(P_{1}dx+Q_{1}dy)+(P_{2}dx+Q_{2}dy)=0
$$
$$
\mu_{1}(P_{1}dx+Q_{1}dy)=d\Phi_{1},\quad \mu_{2}(P_{2}dx+Q_{2}dy)=d\Phi_{2}
$$
则对于连续函数 $g_{1},g_{2}$，$\mu_{1}g_{1}(\Phi_{1}),\mu_{2}g_{2}(\Phi_{2})$ 也都分别为上式的积分因子，假如我们能**恰当的选取**这两个函数，使得 $\mu=\mu_{1}g_{1}(\Phi_{1}),\mu_{2}g_{2}(\Phi_{2})$，那么这个 $\mu$ 就是积分因子

3. 一个重要式子
$$
\frac{xdy-ydx}{x^{2}+y^{2}}=d\left( \arctan\left( \frac{y}{x} \right) \right)
$$

4. 若 $M(x,y),N(x,y)$ 均为 k 次齐次函数，则微分方程 $Mdx+Ndy$ 具有积分因子
$$
\mu=\frac{1}{xM+yN}
$$


#### 调和函数


#### 注意事项
1. 曲线曲面积分运用格林公式时，要先观察奇点
2. 对于奇点一定要小心奇点（斜率）不连续的情况
3. 注意第一型曲面积分和第二型之间的转化关系
4. 涉及平方的三角函数都不为零
$$
\iint_{S}P\,dydz+Q\,dzdx+R\,dxdy=\iint_{S}(P,Q,R)\cdot \vec{n}\,dS=\iint_{S}(Pn_{1}+Qn_{2}+Rn_{3})\,dS
$$
5. 注意法向量的归一化**系数**
### G 常微分方程

#### 1 基本概念

> [!tip] 定义：通解
> 如果一个 n 阶 ODE 有解 $y=\varphi(x;C_{1},C_{2},\cdots,C_{n})$
> 其中 $C_{1},C_{2},\cdots$ 为 n 个独立变化的自由参数，则称他为一个通解

- 通解自由参数要和自由参数数目（方程阶数）相吻合
- 一个不含有自由参数的解叫**特解**，特解不一定能被通解所表示（这种叫奇解）
- 怎么说明自由参数独不独立？
$$
\frac{ \partial (\varphi,\varphi ^{\prime},\cdots\varphi^{(n-1)}) }{ \partial (C_{1},C_{2},\cdots,C_{n}) } \neq 0 ,\quad \forall x \in (a,b)
$$

初值问题（Cauchy 问题）(IVP, initial value problem)
对于 n 阶 ODE，在同一个点 $x_{0}$ 给出 n 个初值条件
$$
\begin{cases}
y(x_{0})=y_{0} \\
y^{\prime}(x_{0})=y_{1} \\
\cdots \\
y^{(n-1)}(x_{0})=y_{n-1}
\end{cases}
$$
如果是给出边界处取值，则称为**边值问题**（BVP，boundary value problem）

#### 2 基本解法
> [!tip] 分离变量法
> $$
> \frac{dy}{dx}=f(x)g(y)
> $$
> 1. 若 g (y)≠0，则对 $dy/g(y)=f(x)dx$ 积分
> 2. 另外，若 g (y)=0 有根 $y=y_{0}$ 则这个根为一个特解
- 若有初值条件 $y(x)=y_{0}$ 那么一般这个对应了无数个解

可转化为分离变量的形式：
1. 
$$
\frac{dy}{dx}=f(ax+by+c)\implies \frac{dz}{dx}=a+b \frac{dy}{dx}=a+bf(z),\quad z=ax+by+c
$$
2. 若方程右边为零次齐次，则做换元 $u=y/x$，x=0 时单独考虑
$$
f(x,y)=h\left( \frac{y}{x} \right)\implies \frac{du}{dx}=\frac{h(u)-u}{x}
$$
3. 形如
$$
y^{\prime}=f\left( \frac{a_{1}x+b_{1}y+c_{1}}{a_{2}x+b_{2}y+c_{2}} \right)
$$
若 $c_{1},c_{2}\neq0$ （同时为零转化成 2 的讨论）
1） $\det \begin{pmatrix}a_{1}&b_{1}\\a_{2}&b_{2}\end{pmatrix}\neq 0$，则可以做一个平移变换为齐次情况
2）$\det \begin{pmatrix}a_{1}&b_{1}\\a_{2}&b_{2}\end{pmatrix} = 0$，则可以通分，把这个转为只有分母有自变量的情况，用 1 处理

> [!tip] 一阶线性 ODE
> $$
> y^{\prime}+P(x)y=Q(x),\quad P,Q\in C(a,b)
> $$
> 如果 $Q(x)\equiv0$ 则称 ODE 为一阶齐次，反之称为非齐次

这个“线性”有什么良好的性质？
1. 如果 $y_{1}$ 和 $y_{2}$ 为齐次线性 ODE 的解，则 $\forall \lambda_{1},\lambda_{2}\in \mathbb{R},\quad \lambda_{1}y_{1}(x)+\lambda_{2}y_{2}(x)$ 也是解
2. 如果 $y_{1}$ 和 $y_{2}$ 为非齐次线性 ODE 的解，则 $y_{1}-y_{2}$ 是齐次线性 ODE 的解

齐次线性方程的全体解构成了一个实线性空间 $V_{0}$
非齐次线性方程的全体解有如下表示，若 $y=y(x)$ 是一个解，则解空间为 $\left\{ y(x)+z(x)|z(x)\in V_{0} \right\}$

1）对于一阶齐次方程
$$
y=Ce^{ -\int_{x_{0}}^{x} P(t) \, dt  }
$$
全体解构成一维实线性空间

2）对于一阶非齐次方程
用积分因子法，令 $F(x)=e^{ \int_{x_{0}}^{x} P(t) \, dt }$，有
$$
(F(x)y)^{\prime}=F(x)Q(x)\implies y(x)=F(x)^{-1}\left( \int_{x_{0}}^{x} F(t)Q(t) \, dt+C  \right)
$$
所以最终解为
$$
y(x)=\int_{x_{0}}^{x} Q(t)e^{ -\int_{t}^{x} P(s) \, ds  } \, dt +Ce^{ -\int_{x_{0}}^{x} P(t) \, dt  }
$$
注：第一项解代表了 t 时刻 Q (t) 这个扰动，按照指数的过程（第二项的变化）进行 t 到 x累积（卷积）的结果——（Duhamel 原理）

（常数变易法）猜测可能的解
$$
y(x)=u(x)e^{ -\int_{x_{0}}^{x} P(t) \, dt  }\implies u(x)=\cdots
$$
本质上是相同的


二阶 ODE 降阶
1) 不显含 y 的方程
$$
F(x,y^{\prime},y^{\prime\prime})=0\implies F(x,z,z^{\prime})=0,\quad (z=y^{\prime})
$$
2) 不显含 x 的方程
$$
F(y,y^{\prime},y^{\prime\prime})=0\implies F\left( y,p(y),p(y) \frac{dp}{dy}(y) \right)=0
$$
令 $p=y^{\prime}$，且将 y 作为新的自变量
这需要利用反函数定理 $x=x(y)$ ，有 $p(y(x))=y^{\prime}(x)\implies p(y)=y^{\prime}(x(y))$
此时
$$
y^{\prime\prime}(x)=\frac{d}{dx}(y^{\prime}(x))=\frac{d}{dx}(p(y)) \frac{dy}{dx}=\frac{dp}{dy}p
$$

伯努利方程
$$
y^{\prime}(x)+P(x)y=Q(x)y^{n}\implies\left( \frac{1}{1-n}y^{1-n} \right)^{\prime}+(1-n)P(x)\left( \frac{1}{1-n}y^{1-n} \right)=Q(x)
$$
#### 3 一阶ODE 解的存在性和唯一性

Cauchy 问题：
$$
\begin{cases}
y^{\prime}=f(x,y) \\
y(x_{0})=y_{0}
\end{cases}\quad (*)
$$
是否存在解，以及解是否唯一？

> [!tip] 定义（Lipschitz 函数）
> 若存在一个映射：$f:(a,b)\to \mathbb{R}$
> 若 $\exists L>0,s.t.\forall x_{1},x_{2}\in(a,b)$ 都有
> $$
> |f(x_{1})-f(x_{2})|\leq L|x_{1}-x_{2}|
> $$
> 则称 $f(x)$ 是 **Lipschitz 连续**的，L 是一个只和**区间有关的常数**
- 考察一个复合函数的 Lipschitz 性质可以从函数的导数入手
- 若一个函数可导，导数有界 $\iff$ Lipschitz

> [!tip] 定理（Picard）
> 考虑 (\*)，设 f 在 $R：=\left\{ (x,y)|\quad  |x-x_{0}|\leq a,|y-y_{0}|\leq b\right\}$ 中**连续**，且关于 y 是 Lipschitz 连续的
> 则 (\*) 在 $[x_{0}-h,x_{0}+h]$ 中**存在唯一解**
> （其中 $h:=min(a,b/M)\quad M:=max_{\mathbb{R}}|f(x,y)|$）

注：
1. 这个定理只能证明**局部**解的存在唯一性
2. 其实还有更弱的版本（Peano）：若 f 在 R 上连续，则有解的（局部）存在性

证明思路：
1）首先注意到（\*）等价于以下积分方程 $*\implies**,\quad **\implies*$
$$
y(x)=y_{0}+\int_{x_{0}}^{x} f(t,y(t)) \, dt \quad (**)
$$
2）Picard 迭代 
定义
$$
y_{1}(x)=y_{0}+\int_{x_{0}}^{x}f(t,y_{0})  \, dt,\quad x\in[x_{0}-h,x_{0}+h]:=I
$$
为了保证函数在这个区间 I 上都存在（即不会从上下穿出），就要控制这个 I 的长度
根据上面对 h 的定义，这个结论是成立的
$$
|y_{1}(x)-y_{0}|=|\int_{x_{0}}^{x} f(t,y_{0}) \, dt |\leq M|x-x_{0}|\leq b
$$
下定义一个递推式
$$
y_{n+1}(x)=y_{0}+\int_{x_{0}}^{x} f(t,y_{n}(t)) \, dt 
$$
同理可以证明这个函数在 I 上都是存在的

这样我们就得到一个函数序列 $\left\{ y_{n}(x) \right\}_{n\in \mathbb{Z}}$

3）我们接下来证明 $\forall x\in I,\lim_{ n \to \infty }y_{n}(x)$ 存在，记作 $\varphi(x)$
由于 Lipschitz 条件，可以证明
$$
\forall n\in \mathbb{Z}_{+},\quad |y_{n+1}(x)-y_{n}(x)|\leq b\cdot L^{n}\cdot \frac{|x-x_{0}|^{n}}{n!}
$$
$\left\{ y_{n} \right\}_{n\in \mathbb{Z}}$ 是一个 Cauchy 列

4）对 $y_{n}$ 两边取连续，则有
$$
\varphi(x)=y_{0}+\lim_{ n \to \infty } \int_{x_{0}}^{x}f(t,y_{n}(t))  \, dt\quad (?)=y_{0}+\int_{x_{0}}^{x} f(t,\varphi(t)) \, dt 
$$
5）论唯一性：设在区间 I 上有两个解 $\varphi(x),\psi(x)$
做差，且由 Lipschitz 连续性
$$
|\varphi(x)-\psi(x)|\leq \int_{x_{0}}^{x} |f(t,\varphi(t))-f(t,\psi(t))| \, d t\leq \int_{x_{0}}^{x} L|\varphi(t)-\psi(t)| \, dt \leq 2b
$$
继续将左式带入倒数第二个式子,可以归纳得到
$$
|\varphi(x)-\psi(x)|\leq 2b\cdot  \frac{L^{n}}{n!}|x-x_{0}|^{n}
$$
令 n 区域∞，则可证明唯一性

注记：
事实上，这里整个证明可以看成一个不动点迭代（压缩映射）的问题，我么可以将 
$$
y_{n+1}=T(y_{n})=y_{0}+\int_{x_{0}}^{x} f(t,y_{n}) \, dt 
$$
这里的 T 看成一个算子，它满足压缩映射的条件（常数是 L）

推论：
1. 如果 (\*) 中 f (x, y) 连续并且关于 y 的导数连续，那么我们可以得到过 $(x_{0},y_{0})$ 当且仅当只有一条曲线（通过区域内运用 picard 定理不断延拓，我们可以知道函数曲线不会在区域内部终止，但是区域的边界可能趋于一个值）
2. 我么可以把 Picard 定理推广到向量值函数上，即对于 
$$
\frac{d\vec{z}}{dx}=\vec{F}(x,\vec{z}(x)),\quad \vec{z}(x_{0})=\vec{z}_{0}
$$
如果 F 是关于 z 是 Lipschitz 连续的
$$
|\vec{F}(\vec{z}_{1})-\vec{F}(\vec{z}_{2})|\leq L|\vec{z}_{1}-\vec{z}_{2}|
$$
则存在唯一解

> [!note] 一类高阶 ODE 初值问题
> $$
> \begin{cases}
> y^{(n)}(x)=f(x,y(x),y^{\prime}(x),\cdots,y^{(n-1)}(x)) \\
> y(x_{0})=y_{0},\quad y^{\prime}(x)=y_{1},\quad \cdots \quad ,y^{(n-1)}(x)=y_{n-1}
> \end{cases}
> $$
> 可化为一阶 ODE 方程组（即向量值函数），令 $\vec{z}=(y(x),y^{\prime}(x),\cdots,y^{(n-1)}(x))^{T}$
> 则
> $$
> \frac{d \vec{z}}{dx}=(y^{\prime}(x),y^{\prime\prime}(x),\cdots,f(x,y,y^{\prime},\cdots))=\vec{F}(x,\vec{z}(x))
> $$

> [!tip] Gronwall 不等式（积分形式）
> 设 $u,B\geq0$ 且连续 
> $$
> u(t)\leq A+\int_{0}^{t} B(s)u(s) \, ds,\quad t\in[0,1],A>0 
> $$
> $$
> \implies u(t)\leq Ae^{ \int_{0}^{t} B(s) \, ds  }
> $$

- 利用这个不等式我们也可以说明常微分方程解的唯一性（本质上是对初值的依赖）
先考虑 A=0 的情况，此时 $u\equiv0$，利用 Lipschitz 条件
$$
|u_{1}-u_{2}|\leq \int_{0}^{t} |f(t,u_{1})-f(t,u_{2})| \, dt\leq \int_{0}^{t} L|u_{1}-u_{2}| \, dt\implies u_{1}\equiv u_{2} 
$$
- 我们还可以得到比较定理

#### 4 高阶线性ODE

对于齐次方程
$$
y^{\prime\prime}+p(x)y^{\prime}+q(x)y=0
$$
> [!tip] 定理
> 若 $\varphi_{1},\varphi_{2}$ 为线性无关的两个解，则 
> 1.  $\forall c_{1},c_{2}\in \mathbb{R}$，$c_{1}\varphi_{1}+c_{2}\varphi_{2}$ 是通解
> 2. 齐次方程的所有解均可表示为上述形式
> $\implies$ 齐次方程全体解构成了线性空间

> [!tip] 引理：解的线性相关
> 设 $\varphi_{1}(x),\varphi_{2}(x)$ 是二阶齐次方程的解
> 则**这两个解线性相关**
> $$
>  \iff W(x)=\det \begin{pmatrix}
> \varphi_{1}(x) & \varphi_{2}(x) \\
> \varphi_{1}^{\prime}(x) & \varphi_{2}^{\prime}(x) 
> \end{pmatrix}=0\quad (Wroski)
> $$
> 注：其实任取区间内的一个点 $x_{0}$ 使得 $W(x_{0})=0$ 上述结论也成立

关于注的解释：
$$
\frac{d}{dx}W(x)=
\det \begin{pmatrix}
\varphi_{1}^{\prime} & \varphi_{2}^{\prime} \\
\varphi_{1}^{\prime} & \varphi_{2}^{\prime} 
\end{pmatrix}
+\det \begin{pmatrix}
\varphi_{1} & \varphi_{2}\\
\varphi_{1}^{\prime\prime} & \varphi_{2}^{\prime\prime} 
\end{pmatrix}
=-p(x)W(x)
$$
这是关于 W 的一个一阶微分方程
$$
W(x)=W(x_{0})e^{ -\int_{x_{0}}^{x} p(x) \, dx  }
$$

于是我们可以完成上述定理的证明：
1）只需证明 $c_{1},c_{2}$ 的独立性
$$
\frac{ \partial (y,y^{\prime}) }{ \partial (c_{1},c_{2}) } =W(x)\neq0
$$
2）已知的这两个解是由两个线性无关的初值条件决定的，于是**这两组初值条件可以导出任意初值条件**，由**解的唯一性**，那么所有的特解都能包含在个通解中
- **齐次线性**的这个性质就告诉我们，由于对于线性无关的解所对应的初值条件也是线性无关的，因此任意初值条件都可以变成这两个初值条件的线性组合，进而**诱导**出通解的线性组合，所以**关于初值的 Wroski 行列式才是决定性的**

- 这个结论可以推广到 n 阶的线性 ODE
（思考：推导此时 $\frac{dW}{dx}=\cdots?$）
- 如果是非齐次二阶方程，则所有解可以表示为“一个特解+齐次通解”的形式

**特殊高阶 ODE**

**欧拉方程**
$$
x^{n}y^{(n)}+P_{1}x^{n-1}y^{(n-1)}+\cdots+P_{n-1}xy^{\prime}+P_{n}y=f(x)
$$
假设 $x= e^{ t }$（$x>0$）$=-e^{ t }$（$x<0$），此时转化为关于 t 的微分方程形式
$$
D=\frac{d}{dt}\implies x^{k}y^{(k)}=D(D-1)\cdots (D-k+1)y
$$
再用 t 反代即可得到方程


**非齐次二阶方程**
$$
y^{\prime\prime}+py^{\prime}+q=f(x)
$$
解法：
1. 微分算子的因式分解
  设特征方程 $\lambda^{2}+p\lambda+q$ 两个解为 $\lambda_{1,2}$
  则原方程等价于
$$
\left( \frac{d}{dx}-\lambda_{1} \right)\left( \frac{d}{dx}-\lambda_{2} \right)y=f(x)
$$
$$
\implies \begin{cases}
\frac{dz}{dx}-\lambda_{1} z=f(x) \\
\frac{dy}{dx}-\lambda_{2}y=z(x)
\end{cases}
$$
- 这个方法在解含有共振的项时非常好算

2. 常数变易法
问题：
$$
y^{\prime\prime}+p(x)y+q(x)=f(x)
$$
假设我已经知道他的齐次方程的两个线性无关解 $\varphi_{1},\varphi_{2}$，如何利用它们求特解

那么我们可以假设他的特解满足以下形式
$$
y(x)=C_{1}(x)\varphi_{1}(x)+C_{2}(x)\varphi_{2}(x)
$$
求导得到
$$
y^{\prime}(x)=C_{1}\varphi_{1} ^{\prime}+C_{2}\varphi_{2}^{\prime}+C_{1}^{\prime}\varphi_{1}+C_{2}^{\prime}\varphi_{2}
$$
注意到我们的特解是由选取的自由度的，我可以在此给他加上一个限制
$$
C_{1}^{\prime}\varphi_{1}+C_{2}^{\prime}\varphi_{2}=0,\quad (1)
$$
再次求导可以得到
$$
y^{\prime\prime}=C_{1}\varphi_{1}^{\prime\prime}+C_{2}\varphi_{2}^{\prime\prime}+C_{1}^{\prime}\varphi_{1}^{\prime}+C_{2}^{\prime}\varphi_{2}^{\prime}
$$
代入方程可以得到
$$
C_{1}^{\prime}\varphi_{1}^{\prime}+C_{2}^{\prime}\varphi_{2}^{\prime}=f(x),\quad (2)
$$
(1)(2) 联立可以得到一个线性方程组，又由于 $\varphi_{1},\varphi_{2}$ 线性无关，Wroski 行列式不等于 0，那么可以解出 $C_{1},C_{2}$


3. 对于特殊的 f 我们猜测解的形式（待定系数，这个一般只能得到特解）
	- $f(x)=P_{n}(x)$，我们设想解有如下形式 $y=Q_{n}(x)$
		- 若 q≠0，ODE左边右边均为 n次多项式，我们只要解一个线性方程组
		- 若 q=0，设想 $y=xQ_{n}(x)$ （使得左右两边次数相同）（实际上这是多此一举直接先求对 y 撇的方程即可）
	- $f(x)=e^{ \alpha x }$，则假设 $y=Ae^{ \alpha x }$ （和算子方法同理）
		- 若 $\alpha^{2}+p\alpha+q\neq0$，则可以求出
		- 若 $\alpha$ 为特征多项式的根，则假设 $y=Axe^{ \alpha x }$
		- 若为二重根，则 $y=Ax^{2}e^{ \alpha x }$
	- 推论：$f(x)=a\cos \beta x+b\sin \beta x$（这里实际上代表了两个共轭复根的耦合：$\pm \beta i$，所以要同时考虑 sin 和 cos）
		- 若 $i\beta$ 不是特征方程根，设 $y=A\cos \beta x+B\sin \beta x$
		- 若 $i\beta$ 为单根，设 $y=x(A\cos \beta x+B\sin \beta x)$
		- 例：$y^{\prime\prime}+y=x\cos x$（这个用算子法比较好算）
		- 注：如果是 $e^{ \alpha x }\sin \beta x$ 这种形式的，判断根应是判断是否是 $\alpha\pm \beta i$ 这种根
4. 算子法（对于高阶常系数微分方程的特解）
$$
D=\frac{d}{dx},\quad P(x)=\sum_{i=0}^{N} c_{i}x^{i}
$$
于是我们可以把微分方程和解表示为
$$
P(D)y=f(x)\implies y=\frac{1}{P(D)}f(x)
$$
一些性质：
1）线性性 
$$
\frac{1}{P(D)}(\alpha f(x)+\beta g(x))=\alpha\frac{1}{P(D)}f+\beta \frac{1}{P(D)}g
$$
2）关于 e 的指数
$$
\frac{1}{P(D)}e^{ \lambda x }f(x)=e^{ \lambda x }\frac{1}{P(D+\lambda)}f(x)
$$
3）若 f (x) 为关于 x 的不超过 m 阶多项式形式，且 $P(0)\neq 0$，$\frac{1}{P}=\sum_{i=0}^{m}a_{i}x^{i}+o(x^{m})$，则
$$
y=\frac{1}{P(D)}f(x)=\sum_{i=0}^{m} a_{i}f^{(i)}(x)
$$
这个对于解决 $f(x)=x^{k}e^{ \alpha x }\cos \beta x$ 十分有用（三角函数引入实虚部即可）


#### 5 常系数线性方程组
现在考虑这样一个**向量值函数**的微分方程
$$
\frac{d\vec{y}}{dx}=\boldsymbol{A}\vec{y}+\vec{f}(x),\quad \vec{y}\in \mathbb{R}^{n}\,,\boldsymbol{A}\in \mathbb{R}^{n\times n}\,,\vec{f}\in C(a,b)
$$

定理：
1. 对于以上方程加上一个初值条件 $\vec{y}(x_{0})=\vec{y}_{0}$，则该初值问题对于每个初值条件有唯一解（利用 Picard 定理的向量值形式）
2. 则通解可以表示为 $\vec{y}(x)=\vec{\varphi}_{*}(x)+c_{1}\vec{\varphi}_{1}+\cdots+c_{n}\vec{\varphi}_{n}$

以上都是理论的一些讨论，接下来我们关心怎么求解

法一：**相似变换**
1）若 A 是对角阵，则方程已经解耦，我们只需解 $y_{i}^{\prime}=\lambda_{i}y_{i}+f_{i}(x)$
2）我们接下来讨论更一般的形式，想法是通过变量替换转化为情形 1，为此我们取可逆矩阵 $\boldsymbol{P}^{-1}\in \mathbb{C}^{n\times n}$

$$
\boldsymbol{P}^{-1} \frac{d\vec{y}}{dx}=\boldsymbol{P}^{-1}\boldsymbol{A}\vec{y}+\boldsymbol{P}^{-1}\vec{f}=\boldsymbol{P}^{-1}\boldsymbol{A}\boldsymbol{P}(\boldsymbol{P}^{-1}\vec{y})+\vec{f}
$$

那么我们通过相似变换可以简化 A 的形式

我们还可以通过代数的方法得到解的矩阵（Jordan 标准型的幂次）


法二：**转化为高阶常微分方程消元**
我们发现
$$
\frac{d\vec{y}}{dx}=\boldsymbol{A}\vec{y}\implies \vec{y}^{(n)}=\boldsymbol{A}^{n}\vec{y}
$$
由 Hamilton-Cayley 定理
对于 A 的特征多项式 $P(\lambda)=\det(\lambda \boldsymbol{I}-\boldsymbol{A})$ ，有 $P(\boldsymbol{A})\equiv0$，同时存在一个唯一的极小多项式 P（最高阶项与 Jordan 块相关），于是我们可以令
$$
P(\boldsymbol{A})\vec{y}=(\boldsymbol{A}^{k}+C_{k-1}\boldsymbol{A}^{k-1}+\cdots+C_{0}\boldsymbol{I})\vec{y}=0\implies y^{(k)}+C_{k-1}y^{(k-1)}+\cdots=0
$$

- 事实上通过高阶方程和线性方程的转化，我们可以证明这两种方法本质上是等价的（特征多项式相同）

#### 注意事项
1. 一定要小心微分方程的通解（不能随意除以一个数）
2. 小心 $\int\frac{1}{x}=\ln|x|,\quad \int_{1} \frac{1}{-x}=-\ln|x|$
3. 在定出积分常数的时候一定要考虑积分常数取某个值的影响
4. 解不出的常微分方程要从一阶齐次/伯努利方程考虑
### H 数项级数

#### 基本概念

**Cauchy 收敛原理**
定义：序列 $\left\{ a_{n} \right\}_{n=1}^{\infty}$，如果 $\forall\varepsilon>0,\exists N_{\varepsilon}>0$，s.t.只需要 $m,n\geq N_{\varepsilon}$ 就有 $|a_{n}-a_{m}|\leq \varepsilon$，则称 $\left\{ a_{n} \right\}$ 为一个 **Cauchy 列**

定理：实数序列 $\left\{ a_{n} \right\}_{n=1}^{\infty}$ 是 Cauchy 列 $\iff$ $\left\{ a_{n} \right\}_{n=1}^{\infty}$ 在 $\mathbb{R}$ 中收敛
- 这个定理本质上是 $\mathbb{R}$ 的完备性（上述定理在 $\mathbb{Q}$ 中不成立）

法一：**柯西准则**（最基本）
级数 $\sum_{n=1}^{\infty}a_{n}$ 收敛的充分必要条件是，$\forall\varepsilon>0$，$\exists N\in \mathbb{N}$，如果 $n>m>N$ 就一定有 $|\sum_{k=m+1}^{n}a_{k}|<\varepsilon$
- 数列收敛 $\implies \lim_{ n \to \infty }a_{n}=0$，这个结论是上述的推论（取 n=m+2）
- **一般判断发散可以先从通项不趋于零入手**
- 一般用来找反例，即存在部分和序列不收敛则可以证明级数不收敛

收敛序列的性质：
1. $\sum_{k=1}^{\infty}a_{k}$ 与 $\sum_{k=1}^{\infty}b_{k}$ 收敛 $\implies \sum_{k=1}^{\infty}(a_{k}\pm b_{k})$ 收敛，且结果为两个之和（可以推广到乘积）
2. 如果两个级数和满足 $\exists N>0,\,s.t.\,a_{n}=b_{n}\,(\forall n\geq N)$，则两个级数的敛散性相同
	1. 于是可以推知，改变/删除/增加有限多项不改变级数的敛散性
3. 在收敛级数中任意添加括号构成的新级数也收敛且和不变
	1. 需要级数收敛，反例是 $\sum_{k=1}^{\infty}(-1)^{k}$

接下来我们研究正项级数（因为单调易分析，可以推广到绝对收敛）
定理：正项级数 $\sum_{k=1}^{\infty}u_{k}$ 收敛 $\iff$ 部分和序列有上界


#### 1 **正项级数**
法二：**比较判别法**（正项级数）
设 $\sum_{n=1}^{\infty}a_{n}$ 和 $\sum_{n=1}^{\infty}b_{n}$ 是两个正项级数，如果存在参数 $C>0$ 和 $N\in \mathbb{N}^{*}$ 使得 $\forall n>N,a_{n}<Cb_{n}$ 成立，那么：
1. 如果 $\sum_{n=1}^{\infty}b_{n}$ 收敛，那么 $\sum_{n=1}^{\infty}a_{n}$ 收敛
2. 如果 $\sum_{n=1}^{\infty}a_{n}$ 发散，那么 $\sum_{n=1}^{\infty}b_{n}$ 发散

命题：对于一个收敛级数 $\left\{ a_{n} \right\}$ 我们总能找到一个比它减小还慢的级数 $\left\{ b_{n} \right\}$ 使得其也收敛

法三：比较的推广——**量级判别法**
设极限 $\lim_{ n \to \infty } \frac{b_{n}}{a_{n}}=c$
1. 如果 c 是正实数，那么二者具有相同敛散性
2. c=0， $a_{n}$ 级数和收敛则 $b_{n}$ 级数和收敛
3. c=∞，反之
在具体做题时，我们可以利用这个极限的性质，选取一个合适的量去转化为一个已知的级数和，最后再用比较判别

> [!example] $\sum_{n=1}^{\infty} \frac{1}{\sqrt[]{ n }\ln(n+1)}$ 的敛散性
> 首先我们要先判断以下，可知大概率是发散的
> 然后我们要选取一个比较的级数来论证（细节上我们要严格证明大小关系）
> 考虑 $\beta>0,\quad\lim_{ x \to \infty } \frac{\ln(x+1)}{x^{\beta}}=0$
> 于是 $\exists N>0,\,s.t.\,n>N,\ln(1+n)\leq n^{\beta}$
> 故 $\forall n>N,\, \frac{1}{\sqrt[]{n  }\ln(1+n)}\geq \frac{1}{n^{1/2+\beta}}$，不妨取 $\beta=\frac{1}{2}$ 由于调和级数发散可知所求级数发散

怎么比较？最常用的是两类级数
- 等比级数 $\sum_{n=1}^{\infty}q^{n}$，若 $q\geq1$ 则发散；$0<q< 1$ 收敛
- P 级数 $\sum_{n=1}^{\infty} \frac{1}{n^{p}}$，若 $p>1$ 则收敛；$0<p\leq 1$ 发散（用二的幂次分割，再换用等比级数判别）

附注：**比值判别法**

法四：公式性判别法（实际上都是以比较判别法为基础的）
一切的判别都是去估计衰减速率


**达朗贝尔判别法**
-  $\lim_{ n \to \infty } \frac{a_{n+1}}{a_{n}}=l$，如果 $l>1$ 级数发散，$l<1$ 级数收敛，如果为 1，则无法判断，要用下面的拉阿贝判别法
- 适用于含阶乘或者分式型级数
证明（与几何级数比较）
若 $l<1$，取 $l<q<1$，则 $\exists N>0\,s.t.n\geq N,\,a_{n+1}/a_{n}\leq q<1$
于是由比较判别，级数收敛


**柯西判别法**（不去考虑相邻项，以防止极限不存在）
- $\lim_{ n \to \infty }\sqrt[n]{ a_{n} }=l$，如果 $l>1$ 级数发散，$l<1$ 级数收敛，如果为 1，则无法判断
- 适用于含 n 幂的级数
- 其实柯西判别法能推出达朗贝尔判别法
证明也是在一个很大的 N 后能被几何级数控制

局限性：这两个都有局限性就是只能判断衰减很快（指数）的，不能判断 p 级数这种

我们想能不能与 p 级数比较 $\implies$
拉阿贝判别法
- $\lim_{ n \to \infty }n\left( \frac{a_{n}}{a_{n+1}}-1 \right)=l$，如果 $l<1$ 级数发散，$l>1$ 级数收敛
简单感受一下
$\frac{u_{n+1}}{u_{n}}=\frac{n}{n+\alpha}=\frac{1}{1+\frac{\alpha}{n}}\sim \frac{1}{\left( 1+\frac{1}{n} \right)^{\alpha}}=\left( \frac{n}{n+1} \right)^{\alpha}$


> [!example] $\sum_{n=1}^{\infty} \frac{n^{n-2}}{e^{ n }n!}$ 的敛散性
> $\frac{u_{n+1}}{u_{n}}=\frac{1}{e}\cdot\left( \frac{n+1}{n} \right)^{n-2}\to1$
> 但是由于 $\left( 1+\frac{1}{n} \right)^{n}$ 关于 n 单调增，所以这个小于 e $\implies \frac{u_{n+1}}{u_{n}}<\left( \frac{n+1}{n} \right)^{-2}$ 
> 所以可以判断 u 是以一个 n 方速度减小，于是收敛

**Cauchy 积分判别法**
若 $\exists c\in \mathbb{Z}_{+}$ 以及定义在 $[c,+\infty]$ 上的一个单调递减的非负函数 f 使得 $f(n)=u_{n}$
则 
$$
\sum_{n=1}^{\infty} u_{n}\text{收敛} \iff \int_{c}^{\infty} f(x) \, dx\text{收敛}
$$
证明：
考虑
$$
u_{k+1}=\int_{k}^{k+1} f(k+1) \, dx \leq \int_{k}^{k+1} f(x) \, dx \leq \int_{k}^{k+1} f(k) \, dx =u_{k}
$$
于是
$$
\sum_{k=1}^{n-1}u_{k+1}\leq \int_{1}^{n} f(x) \, dx  \leq \sum_{k=1}^{n-1} u_{k}
$$
利用极限的有界性进行控制即可得到结论

利用这个我们可以研究下面级数的敛散性
$$
\sum \frac{1}{n(\ln n)^{p}(\ln \ln n)^{q}\cdots}
$$

#### 2 **任意项级数**
定理：
若 $\sum_{n=1}^{\infty}|u_{n}|$ 收敛，则 $\sum_{n=1}^{\infty}u_n$ 收敛，此时我们称**绝对收敛**
- 反之若 $\sum_{n=1}^{\infty}u_{n}$ 收敛, 但绝对值不收敛，则称**条件收敛**
- 用 Cauchy 积分定理+绝对值不等式证明
- 反过来是不对的
- 注：判断一般收敛性，应该先判断绝对收敛再看条件收敛

> [!example] $\sum_{n=1}^{\infty}n\sin \frac{(-1)^{n}}{n^{\alpha}}$ 

绝对收敛级数的性质
1. 可改变顺序求和，结果不变
2. 可以拆成几个子级数求和，每个子级数都绝对收敛
3. 两个绝对收敛的级数之积仍然绝对收敛
4. 并且两个级数可以按照任意次数相乘求和

绝对（或条件）收敛的性质
1. 将级数以任意形式重排后，得到的新级数绝对收敛，且和不变
2. 若条件收敛，则对于 $\forall S\in \mathbb{R}$，则都存在一个此级数的一个重排使得 $\sum_{k}u_{\sigma (k)}=S$

证明思路：

1）为了证明上面第一个命题，我们先给出两个引理

**引理Ⅰ**：（先考虑一个简单的情况——正项级数）
若正项级数 $\sum u_{k}$ 收敛，则对任意重排 $\sigma:\mathbb{Z}_{+}\to \mathbb{Z}_{+}$ 双射，$\sum_{k=1}^{\infty}u_{\sigma(k)}$ 收敛且和不变
证明：
①先证明收敛
设 $S=\sum_{k=1}^{\infty}u_{k},\quad S_{n}=\sum_{k=1}^{n}u_{k}$，由于正项级数，故 $S_{n}$ 单调递增，
令 $\tilde{S}_{n}=\sum_{k=1}^{n}u_{\sigma(k)}，\quad f(n)=max\left\{ \sigma(1),\cdots,\sigma(n) \right\}$
故可知 $\tilde{S}_{n}\leq S_{f(n)}\leq S,\quad \forall n\in \mathbb{Z}_{+}$（第一个不等号由正项可以得到，第二个由 $S_{n}$ 的单调且收敛可以得到）
所以 $\tilde{S}_{n}$ 单调且有界 $\implies$ $\tilde{S}_{n}$ 收敛
②证明极限相等
由①可知，$\tilde{S}\leq S$，又由于 $\sigma(k)$ 是一个双射，所以此时 $\tilde{S}$ 和 $S$ 的地位是相等的（定义一个 $\sigma^{-1}$ 以后）, 那么交换一下就有 $S\leq \tilde{S}$，则命题得证

**引理 2**：（将绝对收敛级数的正负项分开讨论）
若 $\sum u_{n}$ 绝对收敛，记和为 $S$，则 $u_{n}$ 中所有正项构成的级数收敛，记和为 $P$；所有负项构成的级数收敛，记和为 $N$；且 $S=P+N$
证明：
首先我们要构造一个正项负项组成的序列，为了不改变相对排序，我们可以令
$$
v_{n}=max\left\{ u_{n},0 \right\} =(u_{n})_{+},\quad w_{n}=-min\left\{ u_{n},0 \right\}= -(u_{n})_{-}
$$
则显然
$$
u_{n}=v_{n}-w_{n},\quad |u_{n}|=v_{n}+w_{n}
$$
则有 $0\leq v_{n},w_{n}\leq|u_{n}|$，由比较判别可以知道 $\sum v_{n},u_{n}$ 是绝对收敛的
所以，$\sum u_{n}=\sum v_{n}-w_{n}=\sum v_{n}-\sum w_{n}=P+N$
**整理**
于是我们将 $v_{n},w_{n}$ 分别重排，根据引理①和②他们分别绝对收敛，就有
$$
\sum_{n=1}^{\infty} u_{\sigma(n)}=\sum_{n=1}^{\infty} v_{\sigma(n)}-w_{\sigma(n)}=\sum_{n=1}^{\infty} v_{\sigma(n)}-\sum_{n=1}^{\infty} w_{\sigma(n)}=P+N=S
$$

2）定理②的证明思路
**引理**
条件收敛级数 $\sum u_{n}$ 的正项和负项分别构成的级数和均发散，但通项都收敛到 0
**证明**
我们先将通项 $\left\{ u_{n} \right\}$ 分成两部分，一部分是正项的 $\left\{ a_{n} \right\}$，一部分是负项的 $\left\{ b_{n} \right\}$
那么，这些正负项的集合我们可以看成可以使用的弹药，我们设计这样一个算法
给定 $S\in[-\infty,+\infty]$ ，设 $S_{0}=0$
1. 如果 $S_{n}\leq S$ 则从 $\left\{ a_{n} \right\}$ 中选取下一项作为重排的下一项
2. 反之，则从 ${b_{n}}$ 中选取下一项作为重排下一项
由于正负项都是发散的，所以这个算法一定能交替继续下去，并且由于通项趋于 0，所以会收敛



法五：交错级数——莱布尼茨判别法
如果交错级数 $\sum_{n=1}^{\infty}(-1)^{n+1}u_{n}$ 满足 ① $\lim_{ n \to \infty }u_{n}=0$ ，② $u_{n}$ 单调下降，那么级数收敛
证明：
通过图像可以看出，每隔两项构成了一组波峰（谷），并且对于波峰是单调减的，波谷是单调增的
严格论证就是 
$S_{2n+2}=S_{2n}+u_{2n+1}-u_{2n+2}\geq S_{2n}$ , $S_{2n+1}=S_{2n-1}-u_{2n}+u_{2n+1}\leq S_{2n-1}$
又 $S_{1}\geq S_{2n+1}=S_{2n}+u_{2n+1}\geq S_{2n}\geq 0$，所以两个级数都是收敛的，
我们对上面等式取极限就得到 $\lim_{ n \to \infty }S_{2n+1}=\lim_{ n \to \infty }S_{2n}=S$
- 这个证明的本质还是来自于图像：忽上忽下，振荡趋势变小直至收敛
- 如果是两项正两项负之类的级数，要注意的是虽然我们可以加括号用莱布尼茨判别法证明收敛，但这仅仅是证明了 $\lim_{ n \to \infty }S_{2n}$ 收敛，还需要对奇数项讨论





法六：Dirichlet-Abel判别法
用于判断级数 $\sum_{n=1}^{\infty}a_{n}b_{n}$ 的收敛性

|                              | Dirichlet                             | Abel                          |     |
| ---------------------------- | ------------------------------------- | ----------------------------- | --- |
| $\left\{ a_{n} \right\}$ 的性质 | $\lim_{ n \to \infty }a_{n}\to 0$ 且单调 | $a_{n}$ 有界且单调                 |     |
| $\left\{ b_{n} \right\}$ 的性质 | $\sum_{n=1}^{\infty}b_{n}$ 部分和有界      | $\sum_{n=1}^{\infty}b_{n}$ 收敛 |     |
- 莱布尼茨判别法是 dirichlet 的特例，因为 $(-1)^{n}$ 对应级数部分和有界
- 一些常见的 $b_{n}$ 选取：$(-1)^{n}$ 和 $\cos(n\theta)(\theta\neq{2}k\pi)$ 是两类满足部分和有界但不收敛的级数
- $\frac{(-1)^{n}}{n^{p}}$ 和 $\frac{\cos(n\theta)}{n^{p}}$ 确定两类收敛级数
$$
\sum_{k=1}^{n} \cos k\varphi=\frac{1}{2\sin \frac{\varphi}{2}}\sum_{k=1}^{n} 2\sin \frac{\varphi}{2}\cos k\varphi=\frac{1}{2\sin \frac{\varphi}{2}}\sum_{k=1}^{n}\sin\left( k+\frac{1}{2} \right)\varphi-\sin\left( k-\frac{1}{2} \right)\varphi
$$

> [!example] $\sum_{n=1}^{\infty} \frac{\sin n\varphi}{n^{\alpha}}$ 的敛散性和绝对收敛性



证明：
①（Dirichlet）
考虑部分和
$$
\left| \sum_{k=n+1}^{n+p}a_{k}b_{k}  \right| =\left| a_{n+p}B_{n+p}-a_{n}B_{n}-\sum_{k=n+1}^{n+p-1} (a_{k+1}-a_{k})B_{k} \right| \leq 2|a_{n+p}|M+2|a_{n+1}|M
$$
②（Abel）
利用 Dirichlet 判别法，
我们可以令 $L=\lim_{ n \to \infty }a_{n}$，$\tilde{a}_{n}=a_{n}-L\implies \lim_{ n \to \infty }\tilde{a}_{n}=0$
由 Dirichlet 判别法，$\sum_{k=1}^{\infty}\tilde{a}_{k}b_{k}$ 收敛
$$
\sum_{k=1}^{\infty} a_{k}b_{k}=\sum_{k=1}^{\infty} Lb_{k}+\tilde{a}_{k}b_{k}
$$
故级数和收敛

附录：Abel 变换（分部求和公式）
令 $B_{k}=\sum_{l=1}^{k}b_{l}$，则
$$
\sum_{k=1}^{n} a_{k}b_{k}=-\sum_{k=1}^{n-1} (a_{k+1}-a_{k})B_{k}+a_{n}B_{n}
$$
- 可以类比分部积分

 #### 3 **函数序列和函数项级数**
序列：$\left\{ f_{n} \right\},\quad f_{n}:D\to \mathbb{R}$；
函数项级数：$\sum_{n=1}^{\infty}u_{n}(x),\quad u_{n}:D\to \mathbb{R}$

定义：
1）若 $x_{0}\in D$ 使得 $\lim_{ n \to \infty }f_{n}(x_{0})$ 存在，则称 $\left\{ f_{n} \right\}$ 在 $x_{0}$ 上收敛， $x_{0}$ 是 $\left\{ f_{n} \right\}$ 上的收敛点
2）对 $\sum u_{n}(x)$ 令 $S_{n}(x)=\sum_{k=1}^{\infty}u_{k}(x)$，若 $x_{0}\in D$ 使得 $\lim_{ n \to \infty }S_{n}$ 存在，则称...
- 注：以上的收敛性称作点态收敛/逐点收敛

抛出一个问题：$\left\{ f_{n} \right\}$ 在 D 处满足某些条件和性质（连续，可导，可积等），且在 D 上 $\lim_{ n \to \infty }f_{n}=f$，那么 $f$ 是否能继承这些性质？
> [!example] 几个例子
> ① $f_{n}(x)=x^{n},\quad D=[0,1]$ （极限不连续）
> ② $\sum u_{n},\quad u_{n}=\frac{1}{1+nx^{2}}\quad D=[0,1]$（极限不可导）

- 这些例子说明我们当前定义的点态收敛性还不够好，于是引出了我们接下来的讨论的—— 一致收敛性

一致收敛性
定义：设 $\left\{ f_{n}(x) \right\}$ 与 $f(x)$ 在 $D$ 上有定义，若 $\forall\varepsilon>0,\quad \exists N_{\varepsilon}>0\quad s.t.\,n\geq N_{\varepsilon}$ 时总有
$$
|f_{n}(x)-f(x)|\leq\varepsilon,\quad (\forall x\in D)
$$
则称 $\left\{ f_{n} \right\}$ 在 $D$ 上一致收敛到 $f(x)$，记作 $f_{n}\rightrightarrows f$
- 注：和逐点收敛的差别在于，这里的 N 与 x 无关，只与 $\varepsilon$ 有关（相当于整段函数曲线都能被 $\varepsilon$ 控制住）
- 若想证明不一致收敛，则需要找到一个 $x_{n}$ 使得对于任意大的 n，都不等于收敛的那个函数值
- 一致收敛 $\iff sup_{x\in D}|f_{n}(x)-f(x)|\leq\varepsilon$

命题：$f_{n}\rightrightarrows f,\quad x\in D \iff \exists \left\{ a_{n} \right\}(\lim_{ n \to \infty }a_{n}=0)\quad s.t.\,|f_{n}(x)-f(x)|\leq a_{n},\quad(x\in D)$

为了之后讨论方便，我们把一致收敛用到函数项级数的部分和序列上
$$
\sum_{n=1}^{\infty} u_{n}(x)\rightrightarrows S(x)\iff S_{n}(x)\rightrightarrows S(x)
$$
怎么判别一致收敛呢？

级数一致收敛的**必要条件**是通项一致收敛到 0
- 可以用于证明不一致收敛

1）Cauchy 判别法
一致收敛 $\iff\,\forall\varepsilon>0,\exists N_{\varepsilon}>0,s.t.\forall n>N_{\varepsilon}\,\forall p\in \mathbb{Z}_{+}$
$$
\left| \sum_{k=n+1}^{n+p} u_{k}(x) \right| \leq\varepsilon,\quad \forall x\in D
$$
2）Weierstrauss 判别法
若 $\forall n\in \mathbb{Z}_{+}$ 都有 $|u_{n}(x)|\leq a_{n}$ 且正项级数 $\sum_{n=1}^{\infty}a_{n}$ 收敛
$\implies \sum_{n=1}^{\infty}u_{n}(x)$ 在 $D$ 上一致收敛（更强一点 $\sum_{n=1}^{\infty}|u_{n(x)}|$ 一致收敛）

> [!example] 证明 $\sum_{n=1}^{\infty}n^{2}x^{2}e^{ -n^{2}x }\sin nx$ 在 $[0,+\infty)$ 一致收敛

3）Dirichlet & Abel 判别
首先为了移植过来我们需要定义有界性
定义一致有界：设 $f_{n}: D\to \mathbb{R},\quad \exists M>0\quad s.t.\forall n\in \mathbb{Z}_{+},\forall x\in D$ 都有 $|f_{n}(x)|\leq M$，则称 $\left\{ f_{n} \right\}$ 在 $D$ 上**一致有界**

|                                 | Dirichlet                                                                                     | Abel                                                                                       |
| ------------------------------- | --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| $\left\{ a_{n} (x)\right\}$ 的性质 | $\forall x_{0}\in D,\left\{ a_{n}(x_{0}) \right\}$ 关于 n 单调，且 $\left\{ a_{n} \right\}$ 一致收敛到 0 | $\forall x_{0}\in D,\left\{ a_{n}(x_{0}) \right\}$ 关于 n 单调，且 $\left\{ a_{n} \right\}$ 一致有界 |
| $\left\{ b_{n} (x)\right\}$ 的性质 | $\sum_{n=1}^{\infty}\left\{ b_{n} \right\}$ 部分和一致有界                                           | $\sum_{n=1}^{\infty}b_{n}$ 一致收敛                                                            |



> [!example] 按 k+l=n 的大小顺序排列
> $$
> \sum_{k=0}^{\infty} u_{k}\cdot \sum_{l=1}^{\infty} v_{l}=\sum_{n=0}^{\infty} w_{n},\quad w_{n}=\sum_{k=0}^{\infty} u_{k}v_{n-k}
> $$

#### 4 **一致收敛级数的性质**

连续性的推广：
定理：设 $\sum_{n=1}^{\infty}u_{n}(x)$ 在 $[a,b]$ 上一致收敛到 $S(x)$ 且 $u_{n}(x)\in C[a,b],\quad \forall n\in \mathbb{Z}_{+}$ ，则 $S(x)\in C[a,b]$
证明：
$$
|S(x)-S(x_{0})|\leq|S(x)-S_{n}(x)|+|S_{n}(x)-S_{n}(x_{0})|+|S_{n}(x_{0})-S(x_{0})|
$$
注：此定理结论也可写为
$$
\lim_{ x \to x_{0} } \sum_{n=1}^{\infty} u_{n}(x)=\sum_{n=1}^{\infty} \lim_{ x \to x_{0} } u_{n}(x)
$$
- 无穷求和其实暗含了一个极限（部分和），所以这两个极限一般不能交换
考虑他的逆反定理：
设 $D\subset \mathbb{R}$，若 $u_{n}(x)\in C(D)$ 且 $S(x)$ 在 $D$ 上不连续，则 $\sum_{n=1}^{\infty}u_{n}$ 在 $D$ 上不一致收敛到 $S(x)$

可积性：
条件同上，由于 $S(x)\in C[a,b]$ 那么 $S(x)$ 在 $[a,b]$ 上可积，此外
$$
\int_{a}^{b} S(x) \, dx =\sum_{n=1}^{\infty} \int_{a}^{b} u_{n}(x) \, dx 
$$
- 连续性条件可以换为黎曼可积条件

可导性：
定理：设 $\sum_{n=1}^{\infty}u_{n}(x)$ 在 $[a,b]$ 某一点 $x_{0}$ 处收敛，$\sum_{n=1}^{\infty}u_{n}^{\prime}(x)$，在 $[a,b]$ 上一致收敛，且 $u_{n}^{\prime}(x)\in C[a,b]$
则 $\sum_{n=1}^{\infty}u_{n}(x)$ 在 $[a,b]$ 上一致收敛，且 $S(x)$ 在 $[a,b]$ 上可导 $S^{\prime}(x)=\sum_{n=1}^{\infty}u^{\prime}_{n}(x)$
- 这个可导性是闭区间的性质，为了把他延拓到开区间，可以取任意大的内闭证明
> [!example] 证明 $\ln(1+x)=\sum_{n=1}^{\infty}(-1)^{n-1} \frac{x^{n}}{n}\quad x\in(-1,1)$
> 可以通过导数来判断





#### **5 幂级数**

考察幂级数的收敛域
引理：
①若 $\sum_{n=0}^{\infty}a_{n}x^{n}$ 在 $x_{1}\neq0$ 处收敛，则 $\forall x\in(-|x_{1}|,|x_{1}|)$，级数绝对收敛
②若 $\sum_{n=0}^{\infty}a_{n}x^{n}$ 在 $x_{1}\neq0$ 处发散，则 $\forall x\in(-\infty,-|x_{1}|)\cup(|x_{1}|,+\infty)$，级数发散
证明：
首先 $a_{n}x_{1}^{n}$ 是有界的，所以
$$
\sum_{n=0}^{\infty} a_{n}x^{n}=\sum_{n=0}^{\infty} a_{n}x_{1}^{n}\left( \frac{x}{x_{1}} \right)^{n}
$$
由强级数判别，可得原级数收敛

求收敛域分为两步
1. 计算收敛半径
2. 判断端点处的敛散性
注：收敛区间为开区间，收敛域为开区间+边界

求幂级数的**收敛半径**常用以下两种方法：
1. 根据 Cauchy 判别法可得
$$
R=\underline{\lim }_{ n \to \infty }\left| \frac{1}{c_{n}} \right| ^{1/n}
$$
2. 根据达朗贝尔判别法
$$
R=\lim_{ n \to \infty } \left| \frac{c_{n}}{c_{n+1}} \right| 
$$
3. 若不是连续 n 的次方，则可以选择用比值判别法证明
**幂级数的性质**
1）四则运算
设 $\sum a_{n}x^{n}$ 和 $\sum b_{n}x^{n}$ 的收敛半径为 $R_{1},R_{2}$，令 $R=min\left\{ R_{1},R_{2} \right\}$
则在 $(-R,R)$ 中
$$
\sum_{n=0}^{\infty}a_{n}x^{n} \pm \sum_{n=0}^{\infty} b_{n}x^{n}=\sum_{n=0}^{\infty} (a_{n}\pm b_{n})x^{n}
$$
且
$$
\left( \sum_{n=0}^{\infty}a_{n}x^{n}  \right) \left( \sum_{n=0}^{\infty}b_{n}x^{n} \right)=\sum_{n=0}^{\infty} c_{n}x^{n},\quad c_{n}=\sum_{j=0}^{n} a_{j}b_{n-j}
$$
- 乘积法则证明核心：**绝对收敛**级数可交换顺序
- 对于除法则可以使用待定系数法求 $c_{n}$（此时收敛半径不能简单表示，和分母级数复平面中零点有关）

2）一致收敛性

幂级数在收敛区间中**不一定**一致收敛
> [!example] $\sum_{n=0}^{\infty}x^{n}=\frac{1}{1-x},\quad x\in(-1,1)$

定理：设 $\sum a_{n}x^{n}$ 收敛半径为 $R$，则
1. $\forall b\in(0,R)$，$\sum a_{n}x^{n}$ 在 $[-b,b]$ 中一致收敛
2. 若 $\sum a_{n}x^{n}$ 在 $x=R$ 处收敛，则 $\sum a_{n}x^{n}$ 在 $[0,R]$ 上一致收敛
综上，$\sum a_{n}x^{n}$ 在其收敛域的内闭一致收敛

证明：
1. 由于 $\sum a_{n}x^{n}$ 在收敛区间绝对收敛，所以 $\sum |a_{n}|b^{n}$ 收敛，利用强级数判别
2. 只需令 $\sum a_{n}x^{n}=\sum a_{n}R^{n}\left( \frac{x}{R} \right)^{n}$，利用 Abel 判别

3）连续性
令 $S(x)=\sum a_{n}x^{n}$，则 $S(x)$ 在 $(-R,R)$ 上连续，特别的如果在边界处收敛，则单侧连续
证明：$\forall x_{0}\in(-R,R)$ 我总可以找到一个 $b\in(0,R)\,s.t.\,x_{0}\in[-b,b]$

4）可积性
$S(x)$ 在 $(-R,R)$ 中的任意闭区间中可积且可逐项积分，即
$$
\int_{0}^{x} S(t) \, dt=\sum_{n=0}^{\infty} \int_{0}^{x} a_{n}t^{n} \, dt=\sum_{n=0}^{\infty} \frac{a_{n}}{n+1}x^{n+1}  
$$

5）可导性
$S(x)$ 在 $(-R,R)$ 中可导且可逐项求导
证明：
主要证明求导后得到的级数
$$
\sum_{n=1}^{\infty} na_{n}x^{n-1}
$$
（形式上的）是在 $(-R,R)$ 中的任意闭区间中一致收敛

任取 $b\in(0,R)$，此时我们想证在 $[-b,b]$ 上一致收敛
再任取 $r\in(b,R)$（为了构造一个小于 1 的级数因子），$\sum a_{n}r^{n}$ 收敛，我们可以得到
$$
\sum_{n=1}^{\infty} na_{n}x^{n-1}=\sum_{n=1}^{\infty} a_{n}r^{n}\left( \frac{x}{r} \right)^{n-1}\cdot \frac{n}{r}\leq \sum_{n=1}^{\infty} M\left( \frac{b}{r} \right)^{n-1}\cdot \frac{n}{r}
$$
- 推论：设原级数收敛半径为 $R$，求导后得到的级数收敛半径为 $R_{1}$，积分后为 $R_{2}$，则 $R_{1},R_{2}\geq R$，交换一下可以得到 $R=R_{1}=R_{2}$
- 由上，求导不改变收敛半径，所以可以求任意阶导
- 但是端点处的效应可能会改变

一般解题思路：
1. 判断级数收敛半径，端点收敛性
2. 在开区间运用上述性质
3. 如端点收敛，则可以用连续性拓展

#### **6 Taylor 级数**
问题：
1. 给定 $y=f(x)$，如果 $f$ 可以展成一个幂级数，那么 $f$ 应该满足什么性质
2. 反过来，满足什么样条件的 $f$ 可以展开为幂级数

1）设 $f$ 可展成幂级数，即 $\forall x_{0}\in \mathbb{R}$，有 $f(x)=\sum_{n=0}^{\infty}a_{n}(x-x_{0})^{n},\quad x\in(x_{0}-R,x_{0}+R)$，可证 $f\in C^{\infty}$

其次我们可以求 $a_{n}$
$$
a_{n}=\frac{f^{(n)}(x_{0})}{n!},\quad \forall n\in \mathbb{N}
$$
- 幂级数的唯一性

命题：（换心公式）
任取 $x_{1}\in(x_{0}-R,x_{0}+R)$ ，对 $R^{\prime}=R-|x_{0}-x_{1}|$，我们可以将 $f$ 重新展开
$$
f(x)=\sum_{n=0}^{\infty} b_{n}(x-x_{1})^{n},\quad b_{k}=\frac{1}{k!}\sum_{n=k}^{\infty} n(n-1)\cdots(n-k)\cdot \frac{f^{(n)}(x_{0})}{n!}(x-x_{0})^{n-k}
$$
- 核心是绝对收敛的级数可交换次序

2）
首先看必要条件：$f\in C^{\infty}$，这时候 $f$ 构造出一个 Taylor 级数
但可以划等号嘛？
- 实际上，Taylor 级数不一定在 $x_{0}$ 的一个邻域内收敛，且即使收敛，也不一定收敛到 $f$

（实解析函数）定义：
给定 $f:(a,b)\to \mathbb{R}$，如果 $\forall x_{0}\in(a,b)$，$f$ 都在 $x_{0}$ 附近能展开为幂级数，则称 $f$ 是 $(a,b)$ 上的**实解析函数**，此外我们将 $(a,b)$ 上全体解析函数构成的集合 $C^{\omega}(a,b)$
- 注意：$C^{\omega}(a,b)\subsetneqq C^{\infty}(a,b)$
- 解析意味着：单点包含全体函数性质（刚性），而 $C^{\infty}$ 的函数可以通过磨光的操作变化成（具有柔性）

此时我们就想知道：何时 $f$ 的 Taylor 级数收敛到 $f$？
记级数部分和
$$
S_{n}(x)=\sum_{k=0}^{n} \frac{f^{(k)}(x_{0})}{k!}(x-x_{0})^{k}
$$
于是我们可以把证明收敛转化为证明 $\lim_{ n \to \infty }R_{n}(x)=f(x)-S_{n}(x)=0$
进而，我们想要用简单形式表达余项
用 Lagrange 形式表达余项：
$$
\forall x,\quad \exists \theta=\theta_{x,n}\in(0,1),\quad s.t.\quad R_{n}(x)=\frac{1}{(n+1)!}f^{(n+1)}(x_{0}+\theta(x-x_{0}))(x-x_{0})^{n+1}
$$
用 Cauchy 形式表达余项：
$$
R_{n}(x)=\frac{(1-\theta)^{n}}{n!}f^{(n+1)}(x_{0}+\theta(x-x_{0}))(x-x_{0})^{n+1}
$$
解决思路：
1. 直接求出余项，证明趋于零
2. 对一个已知收敛性的级数，积分/求导
3. 级数相乘

## I 广义积分
本章我们研究两类积分
1. 无穷积分——积分区域无界
2. 瑕积分——被积函数无界


### 1 无穷积分
定义：
$$
\int_{a}^{\infty} f(x) \, dx =\lim_{ A \to \infty } \int_{a}^{A} f(x) \, dx 
$$
如果为两侧极限则
$$
\int_{-\infty}^{\infty}  f(x)\, dx =\lim_{ b \to \infty } \int_{c}^{b} f(x) \, dx +\lim_{ a \to -\infty } \int_{a}^{c} f(x) \, dx 
$$
- 需要两个极限都存在积分才收敛（但是要左右单独考虑），即使是奇函数也有可能发散 (如 $f(x)=\frac{x}{1+x^{2}}$)

敛散性：
如果 $f,g:[a,\infty]\to \mathbb{R}$，且 $\exists b\geq a\quad s.t.\quad f\equiv g,x\in[b,\infty]$，则 $\int_{a}^{\infty} f(x) \, dx$ 和 $\int_{a}^{\infty} g(x) \, dx$ 敛散性相同
- 无穷积分收敛只与无穷处取值有关

同函数级数，无穷积分也有 Cauchy 收敛原理
$$
\sum_{i=n}^{n+p} \iff \int_{A}^{A^{\prime}}  \, dx 
$$
- 注：无穷积分收敛无法推出 $\lim_{ x \to \infty }f(x)=0$，甚至无法推出 $f(x)$ 有界
- 但是只要 $\lim_{ x \to \infty }f(x)$ 存在，它的值就一定为 0

我们会发现很多广义积分的性质也和级数相同
1. $\int_{0}^{\infty} |f(x)| \, \mathrm{d}x$ 收敛 $\implies \int_{0}^{\infty} f(x) \, \mathrm{d}x$ 收敛
2. 可以引入绝对收敛和条件收敛
3. 于是我们开始先关注正项积分
	1. 引理：$f\geq0$，则 $\int_{0}^{\infty} f(x) \, \mathrm{d}x$ 收敛 $\iff \int_{a}^{A} f(x) \, \mathrm{d}x$ 关于 $A$ 有界
	2. （比较判别）若 $\exists A\geq a$，$s.t.\,0\leq f(x)\leq g(x),\quad \forall x\geq A$，则
	   积分 $g$ 收敛 $\implies$ 积分 $f$ 收敛，积分 $f$ 发散 $\implies$ 积分 $g$ 发散
		1. 用于比较的标准函数：
		   ① $\int_{1}^{\infty} e^{ -\alpha x } \, \mathrm{d}x,(\alpha>0)$
		   ② $\int_{1}^{\infty} \frac{1}{x^{p}}  \, \mathrm{d}x$：$p>1$ 收敛、$0<p\leq1$ 发散
		   ③ $\int_{2}^{\infty} \frac{1}{x(\ln x)^{q}} \, \mathrm{d}x$：$p>1$ 收敛、$0<p\leq1$ 发散
	3. 推论：如果 $\lim_{ x \to \infty } \frac{f(x)}{g(x)}=k$ 则
	   ①若 $k\geq 0$，积分 $g$ 收敛 $\implies$ 积分 $f$ 收敛
	   ②若 $k\in(0,\infty)$，则积分 $g$ 发散 $\implies$ 积分 $f$ 发散
4. 被积函数变号的情形

|                             | Dirichlet                                                | Abel                                       |
| --------------------------- | -------------------------------------------------------- | ------------------------------------------ |
| $\left\{ f (x)\right\}$ 的性质 | $\int_{a}^{A} f(x) \, \mathrm{d}x$ 对 $A\in[a,\infty)$ 有界 | $\int_{a}^{\infty}f(x)  \, \mathrm{d}x$ 收敛 |
| $\left\{ g (x)\right\}$ 的性质 | $g(x),x\in[a,\infty)$ 单调，且 $\lim_{ x \to \infty }g(x)=0$ | $g(x),x\in[a,\infty)$ 单调有界                 |
> [!example] $\int_{1}^{\infty} \frac{\sin x }{x^{p}} \, \mathrm{d}x,\quad p\in R$ 的敛散性
- 可以推出 $\int_{1}^{\infty} \sin(x^{2}) \, \mathrm{d}x$ 收敛

### 2 瑕积分

想法：在瑕点附近积分再趋于瑕点

定义：
1. （瑕点）设 $f:(a,b]\to \mathbb{R}$，且 $\forall\varepsilon\in(0,b-a)$，$f$ 在 $[a+\varepsilon,b]$ 上可积，但当 $x\to a^{+}$ 时 $f$ 无界，则称 $a$ 是 $f$ 的瑕点
2. （瑕积分）如果 $\lim_{ \varepsilon \to 0^{+} }\int_{a+\varepsilon}^{b} f(x) \, \mathrm{d}x$ 存在，则称瑕积分 $\int_{a}^{b} f(x) \, \mathrm{d}x$ 收敛，并定义 $\int_{a}^{b} f(x) \, \mathrm{d}x=\lim_{ \varepsilon \to 0^{+} }\int_{a+\varepsilon}^{b} f(x) \, \mathrm{d}x$
	1. 右端点瑕点/内部有瑕点类似上面定义
	2. 左右都为瑕点，则这个积分收敛仍需要两侧瑕积分都收敛

敛散性：
（Cauchy 收敛原理）
若 $a$ 为瑕点，则 $\int_{a}^{b} f(x) \, \mathrm{d}x$ 收敛 $\iff \forall\varepsilon>0,\exists \delta>0,\quad s.t.\forall \delta_{1},\delta_{2}\in(0,\delta)$ 都有
$$
 \left|  \int_{a+\delta_{1}}^{a+\delta_{2}} f(x) \, \mathrm{d}x\right| \leq\varepsilon
$$
其他性质都同广义积分
用于比较的标准函数：
1. $\int_{0}^{1} \ln x \, \mathrm{d}x$ 收敛
2. $\int_{0}^{1} \frac{1}{x^{p}} \, \mathrm{d}x$：$p\in(0,1)$ 收敛；$p\geq 1$ 发散

注：瑕积分与无穷积分转换 （变量替换得到）

### 3 含参变量积分
问题：$f:[a,b]\times[c,d]\to \mathbb{R}$ 连续，考虑 $\int_{a}^{b} f(x,y) \, \mathrm{d}x$ 可积（关于 $x$ 连续性所保证的）
定义 $g:y\to \int_{a}^{b} f(x,y) \, \mathrm{d}x$，问此时这个 $g(y)$ 有什么性质？

定理（连续性）：设 $f:[a,b]\times[c,d]\to \mathbb{R}$ 连续，则 $g(y)=\int_{a}^{b} f(x,y) \, \mathrm{d}x$ 在 $[c,d]$ 上连续
证明：（主要想法）
首先以上结论可写为 $\forall y_{0}\in[c,d],\lim_{ y \to y_{0} }g(y)=g(y_{0})$，即
$$
\lim_{ y \to y_{0} } \int_{a}^{b} f(x,y) \, \mathrm{d}x=\int_{a}^{b} \lim_{ y \to y_{0} } f(x,y) \, \mathrm{d}x  
$$
- 即极限和积分号交换顺序，这种操作是需要**一定的一致性保证**的（“一致连续”）

（引理）$f$ 在 $D=[a,b]\times[c,d]$ 上关于 $y$ 一致连续, 即 $\forall(x,y_{1}),(x,y_{2})\in D,$$\quad \forall\varepsilon>0,\exists \delta_{\varepsilon}>0,\quad s.t.$ 只要 $|(x,y_{1})-(x,y_{2})|<\delta$ 就有 $|f(x,y_{1})-f(x,y_{2})|<\varepsilon$
- 这样的性质在一个紧集上都是成立的

有了这样的性质，连续性也是显然的

定理（可积性）：由上条件，$g(y)$ 自然可积，且积分可以表示为
$$
\int_{c}^{d} g(y) \, \mathrm{d}y =\int_{[a,b]\times[c,d]}f(x,y)  \, \mathrm{d}x \mathrm{d}y=\int_{a}^{b} \left( \int_{c}^{d} f(x,y) \, \mathrm{d}x  \right) \, \mathrm{d}x 
$$
- 积分交换也代表了一种极限交换，也是需要一致性保证的

> [!example] $\int_{0}^{1} \frac{x^{2}-x }{\ln x}\, \mathrm{d}x$
> 注意到 $\int_{1}^{2} x^{y} \, \mathrm{d}y=\frac{x^{2}-x }{\ln x}$
> 但是被积函数在 $0,1$ 处没有定义，于是我们要补充定义 $g(0)=0,g(1)=1$
> 
> 或者我们可以令 $f(x,y)=\frac{x^{y}-x}{\ln x}$




定理（可导性）：
设 $f:[a,b]\times[c,d]\to \mathbb{R}$ 连续，且 $\frac{ \partial f }{ \partial y }$ 在 $[a,b]\times[c,d]$ 上存在且连续，则 $g(y)=\int_{a}^{b} f(x,y) \, \mathrm{d}x$ 在 $[c,d]$ 上可微，且
$$
g^{\prime}(y)=\int_{a}^{b} \frac{ \partial f }{ \partial y } (x,y) \, \mathrm{d}x
$$
- 即积分和求导可以交换顺序，关键在于偏导数连续

证明：
$$
g(y)=\int_{a}^{b} f(x,y) \, \mathrm{d}x =\int_{a}^{b} \left( \int_{c}^{y} \frac{ \partial f }{ \partial z }(x,z)  \, \mathrm{d}z +f(x,c)  \right) \, \mathrm{d}x 
$$
由于连续性，积分可交换次序
$$
=\int_{c}^{y} \left( \int_{a}^{b} \frac{ \partial f }{ \partial z } (x,z) \, \mathrm{d}x  \right) \, \mathrm{d}z +\int_{a}^{b} f(x,c) \, \mathrm{d}x 
$$
对于变上限积分求导，要求积分内是连续的
于是可以得到结论

> [!example] 求 $I(r)=\int_{0}^{\pi} \ln(1-2r\cos x+r^{2}) \, \mathrm{d}x$
- 注：
$$
P_{r}(x)=\frac{1}{2\pi} \frac{1-r^{2}}{1-2r\cos x+r^{2}}=\frac{1}{2\pi}\sum_{k\in \mathbb{Z}} r^{|k|}\cos kx
$$
称为 poisson 核，$\int_{-\pi}^{\pi} P_{r}(x)  \, \mathrm{d}x=1$

推广：我们进一步将 $g(y)$ 定义为 (设 $u,v:[c,d]\to[a,b]$ 且连续)
$$
g(y)=\int_{u(y)}^{v(y)} f(x,y) \, \mathrm{d}x 
$$
① $g\in C[c,d]$
②如果此外，$\frac{ \partial f }{ \partial y }$ 连续，且 $u,v$ 可导，则 $g(y)$ 可导，且
$$
g^{\prime}(y)=\int_{u(y)}^{v(y)} \frac{ \partial f }{ \partial y } (x,y) \, \mathrm{d}x +f(v(y),y)v^{\prime}(y)-f(u(y),y)u^{\prime}(y)
$$

### 4 含参变量的广义积分
问题的设定：
$f:[a,\infty)\times[c,d]\to \mathbb{R}$，若任取 $y\in[c,d]$，$\int_{a}^{\infty} f(x,y) \, \mathrm{d}x$ 都收敛（逐点收敛），则定义
$$
g(y):=\int_{a}^{\infty} f(x,y) \, \mathrm{d}x ,\quad y\in[c,d]
$$
那么此时，$g(y)$ 有什么性质？
- 要注意的是，此时无穷又是一种极限，所以这里面有很多极限要处理

定义：$g_{A}(y)=\int_{a}^{A} f(x,y) \, \mathrm{d}x,\quad A\geq a$，故 $g(y)=\lim_{ A \to \infty }g_{A}(y)$，相当于一个连续的函数列求极限

（一致收敛性）：若 $\forall\varepsilon>0,\exists N_{\varepsilon}>a\quad s.t.$ 当 $A\geq N_{\varepsilon}$ 时，就有
$$
\left| \int_{A}^{\infty} f(x,y) \, \mathrm{d}x  \right| <\varepsilon,\quad \forall y\in Y
$$
则称该积分在 $Y$ 上一致收敛

> [!example] $g(t)=\int_{0}^{\infty} t^{2}e^{ -t^{2}x } \, \mathrm{d}x$
> 1. $g_{A}(t)$ 在 $[0,\infty)$ 上不一致收敛
> 2. $\forall \delta>0$，则在 $[\delta,\infty)$ 上一致收敛

一致收敛的判别：
（Cauchy 判别）$\forall\varepsilon>0,\quad \exists N_{\varepsilon}>0,\quad s.t.\forall A,A^{\prime}>N_{\varepsilon}$ 总有
$$
|g_{A}(y)-g_{A^{\prime}}(y)|=\left| \int_{A}^{A^{\prime}} f(x,y) \, \mathrm{d}x \right|  \leq\varepsilon,\quad \forall y\in Y
$$
（比较判别，M—判别法）
如果 $\exists \varphi:[a,\infty]\to \mathbb{R},\quad s.t.\forall(x,y),|f(x,y)|\leq \varphi(x)$ 且 $\int_{a}^{\infty} \varphi(x) \, \mathrm{d}x$ 收敛，则含参积分绝对一致收敛

（Dirichlet/Abel）
> [!example] $\int_{0}^{\infty} e^{ -tx }\frac{\sin x}{x} \, \mathrm{d}x,\quad t\in[0,a]$ 的收敛性

性质：
当一致收敛的时候，$g(y)$ 就有一些比较好的性质
1. $g\in C[c,d]$
2. $g\in R[c,d]$ 且积分可交换顺序
3. 当 $g$ 满足以下条件时，$g(y)$ 在 $[c,d]$ 上一致收敛且可微
	1. $\frac{ \partial f }{ \partial y }$ 在 $[a,\infty]\times[c,d]$ 上连续
	2. $g(y)$ 在 $[c,d]$ 上逐点收敛
	3. $\int_{a}^{\infty}\frac{ \partial f }{ \partial y }  \, \mathrm{d}x$ 在 $[c,d]$ 上一致收敛


> [!example] Laplace 变换
> 设 $f:[0,\infty)\to \mathbb{R}$，$\int_{0}^{\infty} f(x) \, \mathrm{d}x$ 收敛，
> 定义: $F(t):=\int_{0}^{\infty} e^{ -tx }f(x) \, \mathrm{d}x$ 
> 则 $F(t)$ 在 $[0,\infty)$ 上连续，且在 $(0,\infty)$ 上可导
> - 事实上，如果 $F(t_{0})$ 收敛，则 $F(t)\in C[t_{0},\infty),\in D(t_{0},\infty)$

利用这种思想，可以求得积分 $\int_{0}^{\infty} \frac{\sin x}{x} \, \mathrm{d}x$ 的值

## J 傅里叶级数

### 1 基本概念

引入：圆盘热传导方程，边界条件总能被通解表示

问题：给定一个 $2\pi$ 周期的函数 $f(x)$ 他是否总能被表示为
$$
f(x)=\frac{a_{0}}{2}+\sum_{n=1}^{\infty} (a_{n}\cos nx+b_{n}\sin nx)
$$

定理（正交性）：在内积
$$
\langle f,g \rangle =\frac{1}{\pi}\int_{-\pi}^{\pi} f(x)g(x) \, \mathrm{d}x 
$$
下，$\left\{ \frac{1}{\sqrt[]{ 2 }},\cos nx,\sin nx \right\}_{n\geq1}$ 是一个标准正交基（orthonormal family）
- 如果要说明是基，还要知道他的完备性，这个后面讨论

于是当我们想计算展开系数的时候，就可以
$$
a_{n}=\langle f,\cos nx \rangle ,\quad b_{n}=\langle f,\sin nx \rangle 
$$
通过上面的系数，我们就可以显式地定义出 Fourier 级数

但是这个级数会遇到问题
1. 收敛性问题，什么时候右侧的级数能收敛到 $f(x)$
2. 什么函数能被这样展开

我们先讨论第一个：
$f(x)$ 满足什么条件，我们才能有对于部分和序列收敛
$$
(S_{N}f)(x)=\frac{a_{0}}{2}+\sum_{n=1}^{N} (a_{n}\cos nx+b_{n}\sin nx)\to f(x)(N\to \infty),\quad \forall x\in D
$$
- 一个我们能想到的是加强 $f(x)$ 的条件
- 另一个是我们可以弱化求和收敛的定义

我们可以定义这几个求和：
1. （summerable）$S_{k}:=\sum_{k=0}^{n}a_{k}$ 有极限
2. （Cesaro）$\sigma_{k}:=\frac{1}{n}\sum_{k=0}^{n-1}S_{k}$ 有极限
3. （Abel）$A_{k}:=\sum_{k=0}^{n}a_{k}r^{k},\quad r\in(0,1)$ 有极限，然后取 $r\to1$

这三个求和要求都是依次递减的，即 1 推出 2，2 推出 3

（关于收敛的定理）：如果 $f$ 是在 $[0,2\pi]$ 上连续的且以 $2\pi$ 为周期，定义 $\sigma_{k}$（同上），那么 $\sigma_{n}f$ 在 $[0,2\pi]$ 上一致收敛到 $f$

证明：
$$
(S_{n}f)(x)=\frac{a_{0}}{2}+\sum_{k=1}^{n} \left( \frac{1}{\pi}\int_{-\pi}^{\pi} f(y)\cos ny \, \mathrm{d}y \right) \cos nx+\left( \frac{1}{\pi}\int_{-\pi}^{\pi} f(y)\sin ny \, \mathrm{d}y \right)\sin nx
$$
$$
=\frac{a_{0}}{2}+\sum_{k=1}^{n} \frac{1}{\pi}\int_{-\pi}^{\pi}f(y)\cos(n(y-x))  \, \mathrm{d}y=\int_{-\pi}^{\pi} f(y)D_{n}(x-y) \, \mathrm{d}y  
$$
我们有
$$
D_{n}(y)=\frac{1}{\pi}\left( \frac{1}{2}+\sum_{k=1}^{n} \cos(ky) \right)=\frac{1}{2\pi} \frac{\sin\left( \frac{2n+1}{2}y \right)}{\sin\left( \frac{y}{2} \right)}
$$
- 这个称为 **Dirichlet 核**
可以先讨论它的性质：
1. $D_{n}(x)$ 是 $2\pi$ 周期，且 $D_{n}(x)\in C^{\infty}$
2. $\int_{-\pi}^{\pi} D_{n}(t) \, \mathrm{d}t=1$
3. $\int_{-\pi}^{\pi}|D_{n}(t)|  \, \mathrm{d}t \sim O(\ln n)$

对于 Cesero 和
$$
(\sigma_{n}f)(x)=\int_{-\pi}^{\pi} f(y)F_{n}(x-y) \, \mathrm{d}y ,\quad F_{n}(y)=\frac{1}{n}\sum_{k=0}^{n-1}D_{k}(y)=\frac{1}{2\pi n} \frac{\sin^{2}\left( \frac{ny}{2} \right)}{\sin^{2}\left( \frac{y}{2} \right)} 
$$
- 其中 $F_{n}(y)$ 被称为 fejer 核
这个函数满足几个很好的性质：
1.  $F_{n}\geq 0$ 以及 $\int_{-\pi}^{\pi} F_{n}(y) \, \mathrm{d}y=1$
2.  $\forall \delta>0,\quad \lim_{ n \to \infty }\int_{\delta<|y|<\pi}|F_{n}(y)|\,\mathrm{d}y=0$

于是我们可以估计误差
$$
|(\sigma_{n}f)(x)-f(x)|\leq \frac{1}{2\pi}\int_{-\pi}^{\pi} |f(x-t)-f(x)|F_{n}(t) \, \mathrm{d}t
$$
我们可以分为两部分，一部分用一致连续性控制，一部分用 $F_{n}$ 控制
$$
=\int_{-\delta}^{\delta} |f(x-y)-f(x)|F_{n}(y) \, \mathrm{d}y+\int_{other}|f(x-y)-f(x)|F_{n}(y)  \, \mathrm{d}y  
$$

> [!tip] 为什么 $S_{k}$ 不一定一致收敛？

原因还是因为绝对值不是有界的
（定理）总是存在一个 $2\pi$ 周期的连续函数，使得其 Fourier 级数在至少一点发散


我们可以对比一下这两个核

| 性质           | Dirichlet 核 $D_n(t)$                                           | Fejér 核 $F_n(t)$                                                     |
| ------------ | -------------------------------------------------------------- | -------------------------------------------------------------------- |
| **定义**       | $D_n(t) = \frac{\sin\left((n+\frac{1}{2})t\right)}{\sin(t/2)}$ | $F_n(t) = \frac{1}{n} \left( \frac{\sin(nt/2)}{\sin(t/2)} \right)^2$ |
| **归一性**      | $\int_{-\pi}^{\pi} D_{n}(t) \, \mathrm{d}t=1$                  | $\int_{-\pi}^{\pi} F_{n}(t) \, \mathrm{d}t=1$                        |
| **非负性**      | ❌ 振荡（正负交替）                                                     | ✅ 始终非负（平方项保证）                                                        |
| **$L^1$-范数** | ❌ 无界（$\|D_n\|_{L^1} \sim \log n$）                              | ✅ 有界（$\|F_n\|_{L^1} = 1$）                                            |
| **Gibbs 现象** | ❌ 存在（间断点过冲约 9%）                                                | ✅ 不存在（平滑消除过冲）                                                        |
| **连续函数收敛性**  | ❌ 需额外条件（如 Dini 条件）                                             | ✅ 一致收敛（Fejér 定理）                                                     |
| **逐点收敛性**    | ❌ 可能发散（Du Bois-Reymond 反例）                                     | ✅ 在连续点收敛                                                             |
| **计算稳定性**    | ❌ 差（正负抵消导致数值不稳定）                                               | ✅ 好（算术平均抑制振荡）                                                        |
| **适用场景**     | 理论分析（需高光滑性）                                                    | 实际逼近（连续/分段连续函数）                                                      |
| **数学操作**     | 直接累加高频成分                                                       | 对部分和取平均（Cesàro 平均）                                                   |
| **核心问题**     | 高频振荡累加导致不稳定                                                    | 平滑平均改善收敛性                                                            |

上面的推导我们都用到了两个函数的乘积再积分
**卷积**：如果 $f,g:\mathbb{R}\to \mathbb{R}$ 以 $2\pi$ 为周期，则定义
$$
(f*g)(x)=\int_{-\pi}^{\pi} f(y)g(x-y) \, \mathrm{d}y=\int_{-\pi}^{\pi} f(x-y)g(y) \, \mathrm{d}y  
$$
- 加权平均，加权采样
- $S_{n}=f*D_{n},\quad \sigma_{n}=f*F_{n}$

推广：恒同元的近似
一族 $2\pi$ 周期的函数 $\left\{ K_{n}(x) \right\}$，满足
1. $\int_{-\pi}^{\pi} K_{n}(x) \, \mathrm{d}x=1$
2. $\exists M>0,\quad s.t.\int_{-\pi}^{\pi} |K_{n}(x)| \, \mathrm{d}x\leq M$
3. $\forall \delta\in(0,\pi),\quad \lim_{ n \to \infty }\int_{\delta<|x|<\pi}|K_{n}(x)|  \, \mathrm{d}x=0$
则称 $\left\{ K_{n} \right\}$ 为一族好核（good ker）

定理：对于上述的好核，设 $f:\mathbb{R}\to \mathbb{R}$，$2\pi$ 周期
1. 若 $f$ 在 $x_{0}$ 处连续，则 $\lim_{ n \to \infty }(K_{n}*f)(x_{0})=f(x_{0})$
2. 若 $f\in C(\mathbb{R})$，则 $\lim_{ n \to \infty }K_{n}*f\rightrightarrows f$


### 2 部分和收敛性再讨论
那么什么情况下部分和 $S_{n}$ 是收敛到原函数的呢？

我们先引入几个概念，为接下来证明做准备

1）分段连续
在除了有限多个第一类间断点之外连续
2）分段单调
仅有有限多个单调区间
3）分段可微
设 $f$ 在 $[a,b]$ 分段连续，且存在有限多个点：$a<x_{0}<x_{1}<\cdots<x_{n}<b$，使得 $f$ 在 $(x_{i},x_{i+1})$ 上可微，且在各个间断点上左右广义导数都存在

定理（Dirichlet）
$f$ 在 $[-\pi,\pi]$ 上分段连续且分段单调，则 $f$ 的 Fourier 级数逐点收敛，其和函数
$$
S(x)=\frac{1}{2}(f(x^{+})+f(x^{-}))
$$
- 把上面的分段连续和分段光滑换成分段可微，结论也是成立的

对于一致收敛性，我们给出一个充分条件: 
定理：若 $f\in C^{2}$ 且以 $2\pi$ 为周期 则他的 Fourier 级数一致收敛到 $f$
证明：$\forall n\in Z^{+}$，对以下积分进行两次分部积分
$$
a_{n}=\frac{1}{\pi}\int_{-\pi}^{\pi} f(x)\cos nx \, \mathrm{d}x =-\frac{1}{n^{2}\pi}\int_{-\pi}^{\pi} \cos nx f^{\prime\prime}(x) \, \mathrm{d}x 
$$
于是可以推出
$$
|a_{n}|\leq \frac{1}{n^{2}\pi}\int_{-\pi}^{\pi} |f^{\prime\prime}(x)| \, \mathrm{d}x 
$$
$b_{n}$ 同理，那么就有
$$
|a_{n}\cos nx+b_{n}\sin nx|\leq|a_{n}|+|b_{n}|\leq \frac{2}{n^{2}\pi}\int_{-\pi}^{\pi} |f^{\prime\prime}(x)| \, \mathrm{d}x 
$$
由强级数定理，原 Fourier级数收敛
- $a_{n},b_{n}$ 的衰减性与 $f$ 的光滑性有关，$f\in C^{k}(\mathbb{R})\implies|a_{n}|\sim O(n^{-k})$

定理（Riemann-Lebesgue）
若 $f\in R[-\pi,\pi]$，则
$$
\lim_{ n \to \infty } \int_{-\pi}^{\pi} f(x)\cos nx \, \mathrm{d}x =0,\quad \lim_{ n \to \infty } \int_{-\pi}^{\pi} f(x)\sin nx \, \mathrm{d}x
$$

对于一般周期函数 $f$，以 $2l$ 为周期的，我可以定义 $t=\frac{\pi x}{l}$，则 $F(t)=f\left( \frac{lt}{\pi} \right)$ 那么 $F$ 是以 $2\pi$ 为周期的

### 3 Fourier 级数的均方收敛性

问题：给定一个可积函数 $f$，想找一个三角多项式
$$
T_{n}(x)=\frac{a_{0}}{2}+\sum_{k=1}^{n} \alpha_{k}\cos kx+\sum_{k=1}^{n} \beta_{k}\sin kx
$$
使之与 $f$ 最接近

那么第一个问题，怎么刻画远近程度？
1）最大偏差
$$
sup_{x\in[-\pi,\pi]}|f(x)-T_{n}(x)|
$$
2）平均偏差
$$
\frac{1}{2\pi}\int_{-\pi}^{\pi} |f(x)-T_{n}(x)| \, \mathrm{d}x 
$$
3）均方偏差
$$
\frac{1}{2\pi}\int_{-\pi}^{\pi} |f(x)-T_{n}(x)|^{2} \, \mathrm{d}x 
$$

注：对于 $f\in R[a,b]$，$R[a,b]$ 是一个线性空间，我们可以定义一个**范数**
$$
||f||_{p}:=\begin{cases}
sup_{x\in[a,b]}|f(x)|  & p=\infty \\
\left( \int_{a}^{b} |f(x)|^{p} \, \mathrm{d}x  \right)^{1/p} & p\in[1,\infty)
\end{cases}
$$

于是**范数诱导度量**
$$
d_{p}(f,g)=||f-g||_{p}
$$
**度量诱导出收敛性**
如果 $\lim_{ n \to \infty }d(f_{n},f)=0$，则称 $f_{n}\to f$

今天只讨论均方距离，考虑
$$
\frac{1}{2\pi}\int_{-\pi}^{\pi} |f(x)-T_{n}(x)|^{2} \, \mathrm{d}x =\frac{1}{2\pi}\int_{-\pi}^{\pi} |f(x)|^{2}-2f(x)T_{n}(x)+|T_{n}(x)| ^{2}\, \mathrm{d}x 
$$
对于后两项可以得到
$$
\frac{1}{\pi}\int_{-\pi}^{\pi} f(x)T_{n}(x) \, \mathrm{d}x =\frac{\alpha_{0}}{2}a_{0}+\sum_{k=1}^{n} \alpha_{k}a_{k}+\beta_{k}b_{k}
$$
$$
\frac{1}{2\pi}\int_{-\pi}^{\pi} T_{n}(x)^{2} \, \mathrm{d}x =\left( \frac{\alpha_{0}}{2} \right)^{2}+\frac{1}{2}\sum_{k=1}^{n}(\alpha_{k}^{2}+\beta_{k}^{2}) 
$$
于是可以化简为
$$
\implies \frac{1}{2\pi}\int_{-\pi}^{\pi} f(x)^{2}-\left( \frac{a_{0}}{2} \right)^{2}-\frac{1}{2}\sum_{k=1}^{n} (a_{k}^{2}+b_{k}^{2}) \, \mathrm{d}x +\left( \frac{a_{0}-\alpha_{0}}{2} \right)^{2}+\frac{1}{2}\sum_{k=1}^{n} (\alpha_{k}-a_{k})^{2}+(\beta_{k}-b_{k})^{2}
$$

于是我们发现，想要这个式子取到最小，当且仅当
$$
\alpha_{k}=a_{k},\quad \beta_{k}=b_{k}
$$
- 我们可以发现，这个取到最值的 $T_{n}$ 就是我们前面的 Fourier 级数部分和 $S_{n}f$
- 于是我们证明了 Fourier 级数在均方收敛下是最优的

定理（Bessel 不等式）
$f:[-\pi,\pi]\to \mathbb{R}$ ，可积，则其 Fourier 系数满足
$$
\frac{a_{0}^{2}}{2}+\sum_{k=1}^{n} a_{k}^{2}+b_{k}^{2}\leq \frac{1}{\pi}\int_{-\pi}^{\pi} f(x)^{2} \, \mathrm{d}x 
$$
证明：
由之前推导
$$
\frac{1}{2\pi}\int_{-\pi}^{\pi} f(x)^{2}-\left( \frac{a_{0}}{2} \right)^{2}-\frac{1}{2}\sum_{k=1}^{n} (a_{k}^{2}+b_{k}^{2}) \, \mathrm{d}x=\frac{1}{2\pi}\int_{-\pi}^{\pi}  |f(x)-S_{n}f(x)|^{2}\, \mathrm{d}x \geq 0
$$
$$
\implies\frac{a_{0}^{2}}{2}+\sum_{k=1}^{n} a_{k}^{2}+b_{k}^{2}\leq \frac{1}{\pi}\int_{-\pi}^{\pi} f(x)^{2} \, \mathrm{d}x 
$$
令 $n\to \infty$ 即证

注 1：我们可以发现
$$
\frac{a_{0}^{2}}{2}+\sum_{k=1}^{n} a_{k}^{2}+b_{k}^{2}=\frac{1}{\pi}\int_{-\pi}^{\pi} |S_{n}f(x)|^{2} \, \mathrm{d}x 
$$
故 
$$
||f||^{2}=||S_{n}f||^{2}+||f-S_{n}f||^{2}
$$
- 看成向量的勾股定理
- 那么其实 $S_{n}f$ 就是 $f$ 向所有至多 n 次的三角多项式构成的空间进行**投影**
- 进一步的可以看作是**最小二乘法**，而这个方法的使用是依赖于**内积结构**的 （此处依赖于 2 范数是因为基底是在这个内积下正交的  ）

注 2：
以上推导可推广到 $f$ 有瑕点，但 $f^{2}$ 的瑕积分有限的情况


问题：由以上推导，我们自然的就好奇收敛性，即
$n\to \infty$ 时，是否有 $||f-S_{n}f||^{2}\to0$

答案是肯定的

定理（均方收敛性）：$f:[-\pi,\pi]\to \mathbb{R}$ ，可积，则
$$
\lim_{ n \to \infty } \frac{1}{2\pi}\int_{-\pi}^{\pi} |f(x)-S_{n}f(x)|^{2} \, \mathrm{d}x =0
$$
推论：我们可以得到 Bessel 不等式的取等条件（$n\to \infty$）于是得到了
Parseval 等式
$$
\frac{a_{0}^{2}}{2}+\sum_{k=1}^{\infty} a_{k}^{2}+b_{k}^{2}= \frac{1}{\pi}\int_{-\pi}^{\pi} f(x)^{2} \, \mathrm{d}x
$$
- 体现了 $\left\{ \frac{1}{\sqrt[]{ 2 }},\cos kx,\sin kx \right\}$ 是一个完备的正交单位基，这些向量张成了整个空间（平方可积空间 $L^{2}$）而未漏掉任何一个维度
- 完备性的定义，若 $\left\langle  f, \frac{1}{\sqrt[]{ 2 }}  \right\rangle=\langle f,\cos kx \rangle=\langle f,\sin kx \rangle=0$ 则 $f\equiv0$  
证明思路：
记上面的代求极限为 $\varepsilon_{n}^{2}$，首先，$\varepsilon_{n}^{2}$ 关于 n 单调递减

想法：给定 $f$，$\forall\varepsilon>0$ 找一个三角多项式 $T(x)$ 使得他们的 2 范数度量 $<\varepsilon$
那么此时 $\varepsilon_{n}^{2}\leq\varepsilon$

怎么找 $T(x)$？
1）找一个连续函数 $g(x)$ 使得 $(f,g)\leq\varepsilon/4$，“ $f$ 可积，$f$ 可被分片常函数逼近”
2）$g\in C(\mathbb{R})$，考虑 $g$ 的 Cesaro 平均 $\sigma_{m}g$ 已知 $\sigma_{m}g\rightrightarrows g$，故可取 $m\gg1$ 使得 $|\sigma_{m}g-g|\leq \sqrt[]{ \varepsilon }/2$
3）取 $T(x)=\sigma_{m}g(x)$ 于是

应用：
1. 可以算一些特殊的级数和
2. 作为一种对 Fourier 系数衰减性的刻画

命题：$f\in R[-\pi,\pi]$，$2\pi$ 周期，则
$$
\lim_{ n \to \infty } a_{n}=0,\quad \lim_{ n \to \infty } b_{n}=0
$$
- 利用 Parseval 等式收敛即可证明
- 这也是黎曼——勒贝格引理

利用这个等式，我们还能再给出一个 Fourier 级数一致收敛性的更精确的条件：

定理：设 $f:\mathbb{R}\to \mathbb{R}$，$2\pi$ 周期，$f\in C^{1}(\mathbb{R})$ 则 Fourier 级数在 $\mathbb{R}$ 上一致收敛到 $f$

证明：
$$
a_{n}=-\frac{1}{n\pi}\int_{-\pi}^{\pi} f^{\prime}(x)\sin nx \, \mathrm{d}x ,\quad b_{n}=\frac{1}{n\pi}\int_{-\pi}^{\pi} f^{\prime}(x)\cos nx \, \mathrm{d}x 
$$
我们发现，等号右边是和 $f^{\prime}(x)$ 的 Fourier 系数有关，我们记为 $\tilde{a_{n}},\tilde{b_{n}}$
又由于 $f^{\prime}(x)\subset C[-\pi,\pi]\subset R[-\pi,\pi]$，故由 Parseval 等式
$$
\sum_{n=1}^{N} |a_{n}|+|b_{n}|=\sum_{n=1}^{N} \left| \frac{\tilde{b_{n}}}{n} \right| +\left| \frac{\tilde{a_{n}}}{n} \right|\leq \left( \sum_{n=1}^{N} |\tilde{b}_{n}|^{2} \right) ^{1/2}\left( \sum_{n=1}^{N} \frac{1}{n^{2}} \right) ^{1/2}+\left( \sum_{n=1}^{N} |\tilde{a}_{n}|^{2} \right) ^{1/2}\left( \sum_{n=1}^{N} \frac{1}{n^{2}} \right) ^{1/2}
$$
由强级数判别法，原 Fourier 级数一致收敛，又由于原级数逐点收敛，所以一致收敛到 $f$


对于连续函数 $f$，若 $a_{n}=0,\quad b_{n}=0$，则 $f\equiv0$
- 用 $\sigma_{n}f$ 和傅里叶系数关系证明


## 复习

用比较判别相关的时候一定要想一下是否是正项级数
1）数项级数
1. 各种判别法的使用+证明
2. 回归本质，了解放缩和利用基本准则判定收敛
3. 收敛性：条件收敛+绝对收敛

2）函数级数
1. 区分函数项级数的一致收敛判别和函数序列的一致收敛判别
2. 函数序列判别
	1. 能找到一个与 x 无关的序列控制住 f，且序列极限为 0
	2. 反之，如果能构造一个点列 xn 使得极限 $f_{n}(x_{n})-f(x_{n})$ 不趋于 0
	3. 同样的数项级数的判别法也都能用
3. 函数项级数一致收敛判别
	1. 强级数判别
	2. 能找到一个点列 xn 使得 $\lim_{ n \to \infty }u_{n}(x_{n})\neq0$，则不一致收敛
	3. 如果通项一致收敛到 0，我们可以通过连续性来判断一致收敛
4. 一致收敛的性质
	1. 对于开区间的退而求其次的方法（用闭区间逼近）
5. 幂级数
	1. Abel 定理，以及内闭一致收敛的推广（连续性可以传递）
	2. 在做操作（求导、积分）的时候一定要说明收敛域
	3. 我们可以利用逐项求导/逐项求积分计算一些难算的级数
	4. 单侧连续一定要验证边界收敛性
	5. 泰勒级数不要忘了分母的阶乘

3）广义积分
1. 广义积分收敛性
	1. 求极限
	2. 比较判别
	3. Dirichlet 和 Abel
		1. 注意可能有多次使用的情况
	4. 小心两个瑕点的情况
2. 广义积分计算
	1. 分部积分、换元（对称性的把我）
	2. 特殊积分、特殊函数
	3. 含参变量积分
3. 含参变量积分
	1. 利用连续性一定要指明范围
	2. 利用求导求出积分值
	3. 强级数判别——大 M 判别（一致收敛只针对广义积分定义）
		1. 连续性
		2. 可积性
	4. 证明不一致收敛：选取合适的 $y_{n}$ 证明 Cauchy 收敛不成立
	5. D-A
4. 复杂积分计算总结
	1. 常规方法
	2. 转化为 Gauss 或 Dirichlet
	3. 借助含参变量求导法则
	4. 借助含参变量积分换序

4）Fourier 级数
1. Paserval 等式一定要小心 $a_{0}$ 的选取
