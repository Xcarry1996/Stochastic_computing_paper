# Stochastic_computing_paper

update sc papers and relevant works..that I am interested in.lol

## Hardware architecture

- 2019 TCS-I: Efficient CMOS Invertible Logic Using Stochastic Computing. (McGill University, Canada/ Tohoku University, Japan)

  - Invertible logic can operate in one of two modes: 1) a forward mode, in which inputs are presented and a single, correct output is produced, and 2) a reverse mode, in which the output is fixed and the inputs take on values consistent with the output. It is possible to create invertible logic using various Boltzmann machine configurations. Such systems have been shown to solve certain challenging problems quickly, such as fac- torization and combinatorial optimization. In this paper, we show that invertible logic can be implemented using simple spiking neural networks based on stochastic computing. We present a design methodology for invertible stochastic gates, which can be implemented using a small amount of CMOS hardware. We demonstrate that our design can not only correctly implement the basic gates with invertible capability but can also be extended to construct invertible stochastic adder and multiplier circuits. The experimental results are presented, which demonstrate the correct operation of synthesizable invertible circuitry performing both multiplication and factorization, along with fabricated ASIC measurement results for an invertible multiplier circuit.(可逆转电路的硬件和算法实现，SC做神经元的输入，加权实现一个加法器，这里是确定性计算？状态机的硬件代价不高吗？FSM对stochastic number做非线性tanh处理。ps:这篇和随机计算的关系不是很大，更倾向于概率计算而不是随机计算ORZ。BUT算法有点意思，先留着吧lol)


## In-Memory Computing

- 2018 arXiv: In-memory multiplication engine with SOT-MRAM based stochastic computing

  - Abstract: Processing-in-memory (PIM) turns out to be a promising solution to breakthrough the memory wall and the power wall. While prior PIM designs yield successful implemen- tation of bitwise Boolean logic operations locally in memory, it is difficult to accomplish the multiplication (MUL) instruction in a fast and efficient manner. In this paper, we propose a new stochastic computing (SC) design to perform MUL with in-memory operations. Instead of using the stochastic number generators (SNGs), we harness the inherent stochasticity in the memory write behavior of the magnetic random access memory (MRAM). Each memory bit serves as an SC engine, performs MUL on operands in the form of write voltage pulses, and stores the MUL outcome in-situ. The proposed design provides up to 4x improvement in performance compared with conversational SC approaches, and achieves 18x speedup over implementing MUL with only in-memory bitwise Boolean logic operations.
Index Terms—Stochastic computing, PIM, SOT-MRAM


## Neural Networks

- 2019 arXiv: Progressive Stochastic Binarization of Deep Networks. (Johannes Gutenberg-University of Mainz, Germany)

  - A plethora of recent research has focused on improving the memory footprint and inference speed of deep networks by reducing the complexity of (i) numerical representations (for example, by deterministic or stochastic quantization) and (ii) arithmetic operations (for example, by binarization of weights).
We propose a stochastic binarization scheme for deep networks that allows for efficient inference on hardware by restricting itself to additions of small integers and fixed shifts. Unlike previous approaches, the underlying randomized approxi- mation is progressive, thus permitting an adaptive control of the accuracy of each operation at run-time. In a low-precision setting, we match the accuracy of previous binarized approaches. Our representation is unbiased — it approaches continuous computation with increasing sample size. In a high-precision regime, the compu- tational costs are competitive with previous quantization schemes. Progressive stochastic binarization also permits localized, dynamic accuracy control within a single network, thereby providing a new tool for adaptively focusing computational attention.
We evaluate our method on networks of various architectures, already pretrained on ImageNet. With representational costs comparable to previous schemes, we obtain accuracies close to the original floating point implementation. This includes pruned networks, except the known special case of certain types of separated convolutions. By focusing computational attention using progressive sampling, we reduce inference costs on ImageNet further by a factor of up to 33% (before network pruning).

- 2019 ISCAS: Stochastic Computing for Low-Power and High-Speed Deep Learning on FPGA. (James Cook University, Australia)

  - Stochastic Computing (SC) presents a low-cost and low-power alternative to conventional binary computing. In SC, continuous values are represented by stochastically generated bit streams. By performing simple hardware-friendly bit-wise operations on these streams, complex calculations can be realized very efficiently. However, the inherent randomness and approxi- mation used in SC can result in undesirable computational errors. As Convolutional Neural Networks (CNNs) are inherently error- tolerant, SC could be embedded in them to gain higher speed and lower power without significant accuracy loss. In this paper, we propose using SC techniques to approximate multiplication operations on fixed-point weights and biases during training of CNNs. By employing such techniques, we demonstrate near state- of-the-art learning performance for the MNIST and CIFAR- 10 datasets, while achieving significant resource and speed improvements when implementing the deep networks on a Field Programmable Gate Array (FPGA). For MNIST, we demonstrate that SC compared to conventional computing, will result in almost 3 times increase in learning speed with only 1.37% degradation in validation accuracy. Similarly, for CIFAR-10, training is accelerated 3.5 times with a degradation of 3.39%. We also show that our FPGA implementations of CNNs adopting stochastic multipliers consume over 17 times less power than their GPU counterparts.（FPGA加速用SC实现的CNNs，精度损失/速度提升）

- 2019 LASCAS: ASC-FFT: Area-Efficient Low-Latency FFT Design--Based on Asynchronous Stochastic Computing. (University of Virginia, Charlottesville, USA)

  - Asynchronous Stochastic Computing (ASC) is a new paradigm that addresses Synchronous Stochastic Computing (SSC) drawbacks, expensive stochastic number generation (SNG) and long latency, by using continuous time streams (CTS). To go beyond the basic operations of addition and multiplication in ASC we need to incorporate a memory element. Although for SSC the natural memory element is a clocked-flip-flop, using the same approach with no synchronized data leads to unacceptable large error. In this paper, we propose to use a capacitor embedded in a feedback loop as the ASC memory element. Based on this idea, we design a low-error asynchronous adder that stores the carry information in the capacitor. Our adder enables the implementation of more complex computation logic. As an example, we implement an asynchronous stochastic Fast Fourier Transform (ASC-FFT) using a FinFET1X1 technology. The proposed adder requires 76%-24% less hardware cost compared against conventional and SSC adders respectively. Besides, the ASC-FFT shows 3X less latency when compared with SSC-FFT approaches and significant improvements in latency and area over conventional FFT architectures with no degradation of the computation accuracy measured by the FFT Signal to Noise Ratio (SNR).(创造了针对FFT加速的方法，从传统的SSC-FFT到现在的ASC-FFT，增加电容来存储加法器中的进位信息，FinFET1x1实现)


- 2019 DAC: SkippyNN: An Embedded Stochastic-Computing Accelerator for Convolutional Neural Networks. (Univ. of Tehran, Minnesota)

  - In this work, we propose a novel architecture, called SkippyNN, that reduces the computation time of SC-based multiplications in the convolutional layers of CNNs. Each convolution in a CNN is composed of numerous multiplications where each input value is multiplied by a weight vector. Producing the result of the first mul- tiplication, the following multiplications can be performed by multiplying the input and the differences of the successive weights. Leveraging this property, we develop a differential Multiply-and- Accumulate unit, called DMAC, to reduce the time consumed by convolutions in SkippyNN. We evaluate the efficiency of SkippyNN using four modern CNNs. On average, SkippyNN offers 1.2x speedup and 2.7x energy saving compared to the binary implementation of CNN accelerators.


- 2019 DAC: Successive Log Quantization for Cost-Efficient Neural Networks Using Stochastic Computing. (UNIST)

  - Despite the multifaceted benefits of stochastic computing (SC) such as low cost, low power, and flexible precision, SC-based deep neural networks (DNNs) still suffer from the long-latency problem, especially for those with high precision requirements. While log quantization can be of help, it has its own accuracy-saturation problem due to uneven precision distribution. In this paper we propose successive log quantization (SLQ), which extends log quantization with significant improvements in precision and accuracy, and apply it to state-of-the-art SC-DNNs. SLQ reuses the existing datapath of log quantization, and thus retains its advantages such as simple multiplier hardware. Our experimental results demonstrate that our SLQ can significantly extend both the accuracy and efficiency of SC-DNNs over the state-of-the-art solutions, including linear-quantized and log-quantized SC-DNNs, achieving less than 1⇠1.5%p accuracy drop for AlexNet, SqueezeNet, and VGG-S at mere 4⇠5-bit weight resolution.


- 2019 DATE: Energy-Efficient Convolutional Neural Networks with Deterministic Bit-Stream Processing. (University of Minnesota, University of Louisiana)

  - Stochastic computing (SC) has been used for low cost and low power implementation of neural networks. Inherent inaccuracy and long latency of processing random bit-streams have made prior SC-based implementations inefficient compared to conventional fixed-point designs. Random or pseudo-random bitstreams often need to be processed for a very long time to produce acceptable results. This long latency leads to a significantly higher energy consumption than binary design counterparts. Low-discrepancy sequences have been recently used for fast-converging deterministic computation with stochastic constructs. In this work, we propose a low-cost, low-latency, and energy-efficient implementation of convolutional neural networks based on low-discrepancy deterministic bit-streams. Experimental results show a significant reduction in the energy consumption compared to previous random bitstream-based implementations and to the optimized fixed-point design with no quality degradation.



- 2019 ASP-DAC: Log-Quantized Stochastic Computing for Memory and Computation Efficient DNNs. (UNIST)(No paper)

  - For energy efficiency, many low-bit quantization methods for deep neural networks (DNNs) have been proposed. Among them, logarithmic quantization is being highlighted showing acceptable deep learning performance. It also simplifies high-cost multipliers as well as reducing memory footprint drastically. Meanwhile, stochastic computing (SC) was proposed for low-cost DNN acceleration and the recently proposed SC multiplier improved the accuracy and latency significantly which are main drawbacks of SC. However, in their binary-interfaced system which yet costs much less than storing all stochastic stream, quantization is basically linear as same as conventional fixed-point binary. We applied logarithmically quantized DNNs to the state-of-the-art SC multiplier and studied how it can benefit. We found that SC multiplication on logarithmically quantized input is more accurate and it can help fine-tuning process. Furthermore, we designed the much low-cost SC-DNN accelerator utilizing the reduced complexity of inputs. Finally, while logarithmic quantization benefits data flow, proposed architecture achieves 40% and 24% less area and power consumption than the previous SC-DNN accelerator. Its area X latency product is smaller even than the shifter based accelerator.


- 2019 TACS-I: Efficient CMOS Invertible Logic Using Stochastic Computing. (McGill University, Tohoku University)

  - Invertible logic can operate in one of two modes: 1) a forward mode, in which inputs are presented and a single, correct output is produced, and 2) a reverse mode, in which the output is fixed and the inputs take on values consistent with the output. It is possible to create invertible logic using various Boltzmann machine configurations. Such systems have been shown to solve certain challenging problems quickly, such as factorization and combinatorial optimization. In this paper, we show that invertible logic can be implemented using simple spiking neural networks based on stochastic computing. We present a design methodology for invertible stochastic gates, which can be implemented using a small amount of CMOS hardware. We demonstrate that our design can not only correctly implement the basic gates with invertible capability but can also be extended to construct invertible stochastic adder and multiplier circuits. The experimental results are presented, which demonstrate the correct operation of synthesizable invertible circuitry performing both multiplication and factorization, along with fabricated ASIC measurement results for an invertible multiplier circuit.


- 2019 TCAD: SPINBIS: Spintronics based Bayesian Inference System with Stochastic Computing. (Beihang, University of South California, Duke)

  - Bayesian inference is an effective approach for solving statistical learning problems, especially with uncertainty and incompleteness. However, Bayesian inference is a computing-intensive task whose efficiency is physically limited by the bottlenecks of conventional computing platforms. In this work, a spintronics based stochastic computing approach is proposed for efficient Bayesian inference. The inherent stochastic switching behaviors of spintronic devices are exploited to build stochastic bitstream generator (SBG) for stochastic computing with hybrid CMOS/MTJ circuits design. Aiming to improve the inference efficiency, an SBG sharing strategy is leveraged to reduce the required SBG array scale by integrating a switch network between SBG array and stochastic computing logic. A device-to-architecture level framework is proposed to evaluate the performance of spintronics based Bayesian inference system (SPINBIS). Experimental results on data fusion applications have shown that SPINBIS could improve the energy efficiency about 12× than MTJ-based approach with 45% design area overhead and about 26× than FPGA-based approach.


- 2019 JETC: Low-Cost Stochastic Hybrid Multiplier for Quantized Neural Networks. (Minnesota, University of Louisiana at Lafayette)(No paper)

  - With increased interests of neural networks, hardware implementations of neural networks have been investigated. Researchers pursue low hardware cost by using different technologies such as stochastic computing (SC) and quantization. More specifically, the quantization is able to reduce total number of trained weights and results in low hardware cost. SC aims to lower hardware costs substantially by using simple gates instead of complex arithmetic operations. However, the advantages of both quantization and SC in neural networks are not well investigated. In this article, we propose a new stochastic multiplier with simple CMOS transistors called the stochastic hybrid multiplier for quantized neural networks. The new design uses the characteristic of quantized weights and tremendously reduces the hardware cost of neural networks. Experimental results indicate that our stochastic design achieves about 7.7x energy reduction compared to its counterpart binary implementation while maintaining slightly higher recognition error rates than the binary implementation. Compared to previous stochastic neural network implementations, our work derives at least 4x, 9x, and 10x reduction in terms of area, power, and energy, respectively.


- 2019 JETC: Neural Network Classifiers Using a Hardware-Based Approximate Activation Function with a Hybrid Stochastic Multiplier. (Minnesota, Rutgers University)(No paper)

  - Neural networks are becoming prevalent in many areas, such as pattern recognition and medical diagnosis. Stochastic computing is one potential solution for neural networks implemented in low-power back-end devices such as solar-powered devices and Internet of Things (IoT) devices. In this article, we investigate a new architecture of stochastic neural networks with a hardware-oriented approximate activation function. The newly proposed approximate activation function can be hidden in the proposed architecture and thus reduce the whole hardware cost. Additionally, to further reduce the hardware cost of the stochastic implementation, a new hybrid stochastic multiplier is proposed. It contains OR gates and a binary parallel counter, which aims to reduce the number of inputs of the binary parallel counter. The experimental results indicate the newly proposed approximate architecture without hybrid stochastic multipliers achieves more than 25%, 60%, and 3x reduction compared to previous stochastic neural networks, and more than 30x, 30x, and 52% reduction compared to conventional binary neural networks, in terms of area, power, and energy, respectively, while maintaining the similar error rates compared to the conventional neural networks. Furthermore, the stochastic implementation with hybrid stochastic multipliers further reduces area about 18% to 80%, power from 15% to 113.1%, and energy about 15% to 131%, respectively.


- 2019 VLSI System: Design of FSM-Based Function With Reduced Number of States in Integral Stochastic Computing. (National Kaohsiung University of Science and Technology)

  - Stochastic computing (SC) is a promising computing paradigm with low power hardware circuitry. This brief proposes a new finite state machine (FSM)-based function implementation in the SC designs. The new architecture allows multiple input stochastic bitstreams to improve the processing latency and precision loss. As compared to previous integral SC design, the proposed algorithm reduces the total number of states needed in the FSM, while maintaining good accuracy performance. The proposed FSM-based construction is also verified by the mathematical analysis. Synthesized results of hardware implementation reveal that the proposed method has competitive advantages over the previous counterparts in terms of area and power consumption. The presented techniques can be applied in a lot of activation function implementations of the deep neural networks.


- 2019 arXiv: From Stochastic to Bit Stream Computing: Accurate Implementation of Arithmetic Circuits and Applications in Neural Networks. (Istanbul Technical University)

  - In this study, we propose a novel computing paradigm “Bit Stream Computing” that is constructed on the logic used in stochastic computing, but does not necessarily employ randomly or Binomially distributed bit streams as stochastic computing does. Any type of streams can be used either stochastic or deterministic. The proposed paradigm benefits from the area advantage of stochastic logic and the accuracy advantage of conventional binary logic. We implement accurate arithmetic multiplier and adder circuits, classified as asynchronous or synchronous; we also consider their suitability of processing successive streams. The proposed circuits are simulated using the Cadence Genus tool with TSMC 0.18μm CMOS technology. We thoroughly compare the proposed adders and multipliers with their predecessors in the literature, individually and in a neural network application. Comparisons are made in terms of area, speed, power, and accuracy. We believe that this study opens up new horizons for computing that enables us to implement much smaller yet accurate arithmetic circuits compared to the conventional binary and stochastic ones.

## Circuit Synthesis

- 2019 DAC: In-stream Stochastic Division and Square Root via Correlation. (Wisconsin)

  - Stochastic Computing (SC) is designed to minimize hardware area and power consumption compared to traditional binary-encoded computation, stemming from the bit-serial data representation and extremely straightforward logic. Though existing Stochastic Com- puting Units mostly assume uncorrelated bit streams, recent works find that correlation can be exploited for higher accuracy. We pro- pose novel architectures for SC division and square root, which leverage correlation via low-cost in-stream mechanisms that elim- inate expensive bit stream regeneration. We also introduce new metrics to better evaluate SC circuits relying on equilibrium via feedback loops. Experiments indicate that our division converges 46.3% faster with both 43.3% lower error and 45.6% less area.
  
- 2019 TCAD: Simultaneous Area and Latency Optimization for Stochastic Circuits by D Flip-flop Insertion (University of Michigan–Shanghai Jiao Tong University Joint Institute)

  - Stochastic computing (SC) is an unconventional computing technique using digital circuits. It performs arithmetic computation on stochastic bit streams, which encode real values through the ratios of ones in the streams. Despite its advantages such as simple arithmetic units and strong error tolerance, SC faces two big challenges: long computation latency and large hardware overhead to generate independent stochastic bit streams. A recent work proposes to insert D flip-flops (DFFs) into the stochastic circuit to reduce the overhead to generate stochastic bit streams. In this work, observing that DFFs can also be exploited to reduce circuit delay, we propose a novel method to insert DFFs into a stochastic circuit to simultaneously reduce the computation latency of the circuit and the overhead of generating stochastic bit streams, thus addressing both challenges at the same time. Experimental results showed that compared to the state-of-the-art method in optimizing stochastic circuits with DFF insertion, our method can reduce the computation latency by 14.3% and the number of DFFs by 48.1%.


## SNG （Stochastic Number Generator)

- 2018 ICCAD: Deterministic Methods for Stochastic Computing Using Low-Discrepancy Sequences (University of Louisiana at Lafayette)

  - Recently, deterministic approaches to stochastic computing (SC) have been proposed. These compute with the same constructs as stochastic computing but operate on deterministic bit streams. These approaches reduce the area, greatly reduce the latency (by an exponential factor), and produce completely accurate results. However, these methods do not scale well. Also, they lack the property of progressive precision enjoyed by SC. As a result, these deterministic approaches are not competitive for applications where some degree of inaccuracy can be tolerated. In this work we introduce two fast-converging, scalable deterministic approaches to SC based on low-discrepancy sequences. The results are completely accurate when running the operations for the required number of cycles. However, the computation can be truncated early if some inaccuracy is acceptable. Experimental results show that the proposed approaches significantly improve both the processing time and area-delay product compared to prior approaches.

- 2018 Microprocessors and Microsystems: S-Box-Based Random Number Generation for Stochastic Computing (University of Passau; University of Michigan, Ann Arbor)

  - Stochastic circuits (SCs) offer tremendous area and power-consumption benefits at the expense of computational inaccuracies. They require random number sources (RNSs) to implement stochastic number generators (SNGs) for all of their inputs. It is common for an SC to have a large number of primary and auxiliary inputs. Often the associated SNGs take up as much as 80% of the entire circuit area, so sharing RNSs is a very important goal in stochastic computing. Such sharing often leads to large correlation errors that have to be resolved via costly decorrelation methods. Linear feedback shift registers (LFSRs) are typically used as RNSs. However, we show that their deterministic and linear behavior can interfere with commonly used decorrelation methods, causing systematic computation errors, and limiting the possibilities of sharing LFSRs between SNGs. We therefore propose a novel pseudo-random number generator SBoNG for stochastic circuits that combines an LFSR with a non-linear S-box function. An SBoNG does not interfere with decorrelation and can be shared efficiently by multiple SNGs. Consequently, SBoNGs scale very well in SCs with large numbers of inputs.

- 2018 TVLSI: Toward Energy-Efficient Stochastic Circuits Using Parallel Sobol Sequences (University of Alberta)

  - Stochastic computing (SC) often requires long stochastic sequences and, thus, a long latency to achieve accurate computation. The long latency leads to an inferior performance and low energy efficiency compared to most conventional binary designs. In this paper, a type of low-discrepancy sequences, the Sobol sequence, is considered for use in SC. Compared to the use of pseudorandom sequences generated by linear feedback shift registers (LFSRs), the use of Sobol sequences improves the accuracy of stochastic computation with a reduced sequence length. The inherent feature in Sobol sequence generators enables the parallel implementation of random number generators with an improved performance and hardware efficiency. In particular, the underlying theory is formulated and circuit design is proposed for an arbitrary level of parallelization in a power of 2. In addition, different strategies are implemented for parallelizing combinational and sequential stochastic circuits. The hardware efficiency of the parallel stochastic circuits is measured by energy per operation (EPO), throughput per area (TPA) and run time. At a similar accuracy, the 8× parallel stochastic circuits using Sobol sequences consume approximately 1% of the EPO of the conventional LFSR-based non-parallelized circuits. Meanwhile, an average of 70 (up to 89) times improvements in TPA and less than 1% run time are achieved. A sorting network is implemented for a median filter (MF) as an application. For a similar image processing quality, a higher energy efficiency is obtained for an 8× parallelized stochastic MF compared to its binary counterpart.

- 2018 ISVLSI: Towards Theoretical Cost Limit of Stochastic Number Generators for Stochastic Computing (University of Michigan–Shanghai Jiao Tong University Joint Institute)

  - Stochastic number generator (SNG) is one important component of stochastic computing (SC). An SNG usually consists of a random number source (RNS) and a probability conversion circuit (PCC). The SNGs occupy a large portion of the total area and power of a stochastic circuit. Thus, it is critical to lower the area and power of the SNGs. The existing methods only focused on simplifying the RNSs inside the SNGs, such as sharing the RNSs and using emerging devices. However, how to reduce the area and power of PCCs is never studied. In this work, we explore this problem and propose a solution that can effectively reduce the area and power of PCCs. We also study the theoretical limit on the cost of SNG and find that our proposed design approaches the limit. The experimental results show that our design can gain up to 2× improvement in power-delay product over the traditional SNGs.

## Accuracy Analysis

- 2015 GLSVLSI: Minimizing Error of Stochastic Computation through Linear Transformation (University of Michigan–Shanghai Jiao Tong University Joint Institute)

  - Stochastic computation is an unconventional computational paradigm that uses ordinary digital circuits to operate on stochastic bit streams, where signal value is encoded as the probability of ones in a stream. It is highly tolerant of soft errors and enables complex arithmetic operations to be implemented with simple circuitry. Prior research has proposed a method to synthesize stochastic computing circuits to implement arbitrary arithmetic functions by approximating them via Bernstein polynomials. However, for some functions, the method cannot find Bernstein polynomials that approximate them closely enough, thus causing a large computation error. In this work, we explore linear transformation on a target function to reduce the approximation error. We propose a method to find the optimal linear transformation parameters to minimize the overall error of the stochastic implementation. Experimental results demonstrated the effectiveness of our method in reducing the computation error and the circuit area.

- 2017 DATE: Framework for Quantifying and Managing Accuracy in Stochastic Circuit Design (University of Michigan, Ann Arbor)

  - Stochastic circuits (SCs) offer tremendous area and power-consumption benefits at the expense of computational inaccuracies. Managing accuracy is a central problem in SC design and has no counterpart in conventional circuit synthesis. It raises a basic question: how to build a systematic design flow for stochastic circuits? We present, for the first time, a systematic design approach to control the accuracy of SCs and balance it against other design parameters. We express the (in)accuracy of a circuit processing n-bit stochastic numbers by the numerical deviation of the computed value from the expected result, in conjunction with a confidence level. Using the theory of Monte Carlo simulation, we derive expressions for the stochastic number length required for a desired level of accuracy, or vice versa. We discuss the integration of the theory into a design framework that is applicable to both combinational and sequential SCs. We show that for combinational SCs, accuracy is independent of the circuit’s size or complexity, a surprising result. We also show how the analysis can identify subtle errors in both combinational and sequential designs.

## Algorithm 

- 2019 TCSII: A stochastic computing architecture for iterative estimation. (IEEE)

  - Stochastic computing (SC) is a promising candidate for fault-tolerant computing in digital circuits. We present a novel stochastic computing estimation architecture allowing to solve a large group of estimation problems including least squares estimation as well as sparse estimation. This allows utilizing the high fault tolerance of stochastic computing for implementing estimation algorithms. The presented architecture is based on the recently proposed linearized-Bregman-based Sparse Kaczmarz algorithm. To realize this architecture, we develop a shrink function in stochastic computing and analytically describe its error probability. We compare the stochastic computing architecture to a fixed-point binary implementation and present bit-true simulation results as well as synthesis results demonstrating the feasibility of the proposed architecture for practical implementation.(更新某种函数并描述其错误率，利用了随机计算高容错性的特点执行estimation算法)









