---
title: "Blog 1"
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---
### **Accelerating the Quantum Toolbox for Python (QuTiP) with cuQuantum on AWS**

**by Boris Varbanov, Benchen Huang, Éric Giguère, Jin-Sung Kim, Khaldoon Ghanem, Tyler Takeshita, and Timothy Brown | AUGUST 9, 2025 | in [Amazon Braket](https://aws.amazon.com/blogs/quantum-computing/category/quantum-technologies/amazon-braket/), [Quantum Technologies](https://aws.amazon.com/blogs/quantum-computing/category/quantum-technologies/)**

Simulating quantum systems on classical computers remains a computational challenge. In fact, the resources required for such simulations grow exponentially with the size of the system. This reality is central to the motivation for building quantum computers. Quantum computers have the potential to outperform even the most powerful supercomputers when simulating quantum systems found in nature. They are also expected to speed up the solution of certain complex problems, with applications ranging from cryptography to large-scale optimization. However, solving real-world problems of interest will require algorithms that perform billions of operations on hundreds of thousands of qubits. Current quantum hardware is far from meeting these demands: the number of qubits is still limited, and gate error rates remain high. Scientists and engineers worldwide are working to improve device design and operation to enable large-scale quantum computing.

Designing high-performance classical simulations for quantum devices is an active research field at the intersection of experimental science and computational science. Researchers often simulate a small portion of the system to obtain results within a reasonable time—for example, focusing on low-lying excited states and a few qubits or couplers. However, scientists increasingly recognize that a more comprehensive understanding of underlying physical systems is needed to improve hardware performance and reduce error rates. This requires incorporating more complex physical effects, such as interactions with other qubits on the device or the impact of higher energy states. Yet these more realistic simulations are computationally expensive.

In this post, researchers from the Superconducting Quantum Device Theory group at the Institut quantique, Université de Sherbrooke, NVIDIA, and Amazon Web Services (AWS) collaborated to accelerate open-quantum-system simulations using classical compute resources. The team achieved this by integrating [NVIDIA cuQuantum](https://developer.nvidia.com/cuquantum-sdk) with the [Quantum Toolbox in Python (QuTiP)](https://qutip.org/), enabling GPU-accelerated simulation of quantum device dynamics. Leveraging Amazon Elastic Compute Cloud (Amazon EC2) instances powered by NVIDIA GPUs, we demonstrate simulation speedups of up to 4000×, enabling large-scale multi-qubit system modeling with improved performance.

## **The qutip-cuquantum Plugin**

QuTiP is an open-source software toolbox for simulating the dynamics of open quantum systems. It aims to provide efficient and user-friendly numerical simulations for a variety of Hamiltonians, including arbitrarily time-dependent ones commonly found in quantum optics, trapped ions, superconducting circuits, and quantum nanomechanical resonators. NVIDIA cuQuantum is a software development kit (SDK) containing optimized libraries and tools designed to accelerate quantum computing simulations at both the circuit and device levels.

To expand the range of computational experiments, our team integrated cuQuantum with QuTiP through the [qutip-cuquantum](https://github.com/qutip/qutip-cuquantum) plugin, available on [PyPI](https://pypi.org/project/qutip-cuquantum/0.1.1/). This plugin leverages NVIDIA’s new cuQuantum library, [cuDensityMat](https://docs.nvidia.com/cuda/cuquantum/latest/cudensitymat/index.html), designed to accelerate analog quantum dynamics solvers and provide GPU-accelerated time evolution for the Schrödinger equation and the Lindblad master equation. cuDensityMat provides primitives that accelerate existing dynamics frameworks such as [NVIDIA CUDA-Q Dynamics](https://developer.nvidia.com/cuda-q) and now QuTiP, as well as accelerating custom-built solvers. It offers low-level functionality to define arbitrary pure or mixed quantum states, specify multi-body operators and superoperators, and compute their action on states. It also supports gradients, multi-GPU, and multi-node simulations for easy scaling.

## **Results**

To evaluate the performance of the qutip-cuquantum plugin, we simulated a superconducting transmon qubit capacitively coupled to a resonator and driven by a microwave pulse. The system operates in the dispersive regime, where the qubit-resonator coupling strength is much smaller than their detuning. This configuration is a standard approach for qubit readout in superconducting processors. In principle, increasing the microwave drive amplitude can shorten measurement time. In practice, however, it often induces unwanted qubit state transitions, pushing the system beyond the computational subspace. Accurately capturing these effects requires modeling many qubit and resonator states, dramatically increasing the size of the Hilbert space and making the dynamics simulation computationally demanding. Here, we report results for systems with 512 resonator states and 32 or 64 qubit states, with the full Hamiltonian constructed in QuTiP.

<p align="center">
  <img src="/images/1.png"
       alt="Circuit diagram of the simulated system"
       style="max-width: 320px;">
</p>

<p style="font-size: 0.9rem; font-style: italic; text-align: center;">
  Figure 1 – Circuit diagram of the simulated system, where the transmon qubit
  (green) is capacitively coupled to the resonator (blue) with an external drive.
</p>

The team ran simulations on AWS using P4de, P5, and P5en EC2 instances powered by [NVIDIA A100](https://www.nvidia.com/en-us/data-center/a100/), [NVIDIA H100](https://www.nvidia.com/en-us/data-center/h100/), and [NVIDIA H200](https://www.nvidia.com/en-us/data-center/h200/) GPUs, respectively. Benchmarks show reduced runtime for the 32-qubit-state system, with a speedup of 725× on a single H200 GPU compared to a CPU-only simulation on an Hpc7a instance. Scaling to multiple H200 GPUs yields additional speedups of 1.2×, 2.2×, and 3.7× for 2, 4, and 8 GPUs, respectively. The 64-qubit-state simulation requires 8 H200 GPUs due to memory needs and achieved a 4000× speedup on the P5en instance with 8 GPUs. Finally, we observed GPU-generation improvements, with speedups of 1.5× and 1.9× when moving from P4de to P5 and P5en.

These advancements open new opportunities for studying multi-qubit dynamics and interactions involving highly excited states, which are crucial for optimizing operations such as readout and two-qubit gates. With these new tools, the research team can now explore transmon physics at scales previously out of reach—marking an important step toward next-generation quantum hardware. Integrating GPU acceleration into QuTiP also ensures these capabilities are broadly accessible to the research community.

TAGS: [Amazon Braket](https://aws.amazon.com/blogs/quantum-computing/tag/amazon-braket/), [NVIDIA](https://aws.amazon.com/blogs/quantum-computing/tag/nvidia/), [quantum computing](https://aws.amazon.com/blogs/quantum-computing/tag/quantum-computing/), [quantum research](https://aws.amazon.com/blogs/quantum-computing/tag/quantum-research/), [quantum technologies](https://aws.amazon.com/blogs/quantum-computing/tag/quantum-technologies/)

---

<div style="display:flex; align-items:flex-start; gap:1.75rem; margin:2rem 0;">

  <div style="flex:0 0 220px;">
    <img src="/images/boris.jpg"
         alt="Boris Varbanov"
         style="max-width:100%; height:auto; display:block;">
  </div>

  <div>
    <h3 style="margin-top:0; margin-bottom:0.5rem;">Boris Varbanov</h3>
    <p style="margin:0;">
      Boris Varbanov is a postdoctoral researcher at the Institut quantique,
      Université de Sherbrooke, where he studies how superconducting qubits
      can be excited outside their computational subspace. His work includes
      simulating the impact of such errors on quantum error-correction codes
      and developing methods or hardware design improvements to mitigate
      these errors. He received his Ph.D. in Physics from Delft University of
      Technology. His research focuses on enabling quantum error correction
      in superconducting processors, and he often collaborates closely with
      experimental teams working toward this goal.
    </p>
  </div>

</div>
<hr/>

<div style="display:flex; align-items:flex-start; gap:1.75rem; margin:2rem 0;">

  <div style="flex:0 0 220px;">
    <img src="/images/BenchenHuang.png"
         alt="Benchen Huang"
         style="max-width:100%; height:auto; display:block;">
  </div>

  <div>
    <h3 style="margin-top:0; margin-bottom:0.5rem;">Benchen Huang</h3>
    <p style="margin:0;">
      Benchen Huang is a Specialist Solutions Architect for Quantum Computing
      at AWS, working with customers to develop hybrid quantum-classical
      solutions on the cloud. He holds a Ph.D. in Chemistry from the
      University of Chicago. His research focuses on applying quantum
      computing to chemistry problems.
    </p>
  </div>

</div>
<hr/>

<div style="display:flex; align-items:flex-start; gap:1.75rem; margin:2rem 0;">

  <div style="flex:0 0 220px;">
    <img src="/images/eric.png"
         alt="Éric Giguère"
         style="max-width:100%; height:auto; display:block;">
  </div>

  <div>
    <h3 style="margin-top:0; margin-bottom:0.5rem;">Éric Giguère</h3>
    <p style="margin:0;">
      Éric Giguère is a Research Specialist at the Université de Sherbrooke.
      He is a maintainer of the open-source QuTiP project. He holds a Ph.D.
      from Hokkaido University, where he studied theoretical particle physics.
    </p>
  </div>

</div>

<hr/>

<div style="display:flex; align-items:flex-start; gap:1.75rem; margin:2rem 0;">

  <div style="flex:0 0 220px;">
    <img src="/images/jin-sung.jpg"
         alt="Jin-Sung Kim"
         style="max-width:100%; height:auto; display:block;">
  </div>

  <div>
    <h3 style="margin-top:0; margin-bottom:0.5rem;">Jin-Sung Kim</h3>
    <p style="margin:0;">
      Jin-Sung Kim is a Quantum Developer Relations Manager at NVIDIA,
      overseeing strategic partnerships and alliances. Before joining NVIDIA,
      he was a Research Staff Member at IBM Quantum. Jin-Sung holds a Ph.D.
      in Electrical Engineering and Materials Science from Princeton
      University and is currently based in San Francisco.
    </p>
  </div>

</div>

<hr/>

<div style="display:flex; align-items:flex-start; gap:1.75rem; margin:2rem 0;">

  <div style="flex:0 0 220px;">
    <img src="/images/image004-1.jpg"
         alt="Khaldoon Ghanem"
         style="max-width:100%; height:auto; display:block;">
  </div>

  <div>
    <h3 style="margin-top:0; margin-bottom:0.5rem;">Khaldoon Ghanem</h3>
    <p style="margin:0;">
      Khaldoon Ghanem is a Senior Development Technology Engineer at NVIDIA,
      specializing in quantum computing. He holds a Ph.D. in computational
      quantum physics from RWTH Aachen University, in collaboration with the
      Jülich Supercomputing Centre. Prior to NVIDIA, he was a researcher at
      Quantinuum, developing quantum algorithms for condensed-matter physics
      applications. He also spent several years at the Max Planck Institute
      in Stuttgart, working on large-scale parallel quantum Monte Carlo
      simulations.
    </p>
  </div>

</div>

<hr/>

<div style="display:flex; align-items:flex-start; gap:1.75rem; margin:2rem 0;">

  <div style="flex:0 0 220px;">
    <img src="/images/tyle.png"
         alt="Tyler Takeshita"
         style="max-width:100%; height:auto; display:block;">
  </div>

  <div>
    <h3 style="margin-top:0; margin-bottom:0.5rem;">Tyler Takeshita</h3>
    <p style="margin:0;">
      Tyler Takeshita is a Senior Applied Scientist for Quantum Computing at
      AWS. Before joining AWS, he was Head of Quantum Technology at the
      Mercedes-Benz Research and Development North America, a subsidiary of
      Daimler. Tyler received his Ph.D. in Chemistry in 2015 from the
      University of Illinois at Urbana-Champaign, specializing in theoretical
      quantum chemistry. He later conducted postdoctoral research in the
      Department of Chemistry at the University of California, Berkeley.
    </p>
  </div>

</div>

<hr/>

<div style="display:flex; align-items:flex-start; gap:1.75rem; margin:2rem 0;">

  <div style="flex:0 0 220px;">
    <img src="/images/timo.png"
         alt="Timothy Brown"
         style="max-width:100%; height:auto; display:block;">
  </div>

  <div>
    <h3 style="margin-top:0; margin-bottom:0.5rem;">Timothy Brown</h3>
    <p style="margin:0;">
      Timothy Brown is a Principal Solutions Architect for Computing & HPC at
      AWS. He has worked in High-Performance Computing for the past 15 years,
      serving in various roles involving simulation and optimization,
      particularly in numerical weather prediction. Timothy holds a Master’s
      and a Bachelor’s (Honors) degree from the University of Western
      Australia (UWA).
    </p>
  </div>

</div>
