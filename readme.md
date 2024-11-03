# Zero-Knowledge.ai

## Project Background

AI algorithms, once trained, are powerful tools that may be extremely valuable or challenging to reproduce, raising a need for security in many aspects of AI inference and ownership.

**Zero-Knowledge.ai** is a set of tools for parties seeking to run sensitive AI applications trustlessly and assert ownership of Intellectual Property.

## Proposal Overview

The **Zero-Knowledge.ai** app leverages zero-knowledge proofs to tackle today's problems with **the lack of trust in AI model providers (fraudulent benchmarks, data mining, IP theft, etc.)** and **the lack of trust in the user** by:

- Ensuring intellectual property (IP) owership of a private model.
- Ensuring privacy for the end user.
- Ensuring full, non-fraudulent, model execution in multiple scenarios.

Here is a recap of the application use cases for the different themes & stakeholders:

| Category     | Model Provider | Model User                       | Law Enforcement                |
|:------------:|:--------------:|:---------------------------------:|:-------------------------------:|
| **Intellectual Property (IP)**       | Prove ownership of a model | Ensure data is provided to the correct entity  | Ensure IP and ownership |
| **Inference**| Prove model inference without revealing the parameters (e.g., benchmarks) | Run an AI model without revealing the weights | Diverse applications |

Note that users can also be from educational and research backgrounds.

## **Zero-Knowledge.ai**: A Services-Based Solution (Architecture & Design)

The **Zero-Knowledge.ai** app will be divided into different services provided to users:

### 1: An Intellectual Property Tool for Everyone

#### Proving Ownership

The first service, and the simplest to implement, will be based on intellectual property assistance for everyone (companies, educational institutions, research, individuals, etc.).

The idea behind this service is to let the user use a smart contract to generate a signature of the model's weights. This computation will be proven and available on-chain. Other parties will then be able to verify ownership by using the AI provider's PublicKey on a piece of known data asoociated with the public TX.

If the need to verify ownership of a model arises, the AI provider can use the smart contract to run the signature computation, prove they ran the said computation, and by comparing the two signatures, we can confirm the provider knows the secret weights (i.e., private intellectual property) without ever revealing them.

### 2: Proving AI Inference

#### For the User

For sensitive AI applications requiring inputs that users would prefer to keep private, a powerful way to ensure privacy is zk-inference. This is the basic concept of zero-knowledge AI: **run provable AI off-chain and then prove inference by only providing the results!**

![AI inference img](https://image.noelshack.com/fichiers/2024/44/5/1730466190-capture-d-cran-du-2024-11-01-14-02-38.png)

This idea is advantageous as it offloads the chain and the data centers of computation, although ther prrof can be costly in terms of computing power.

A future (and **huge**) improvement would involve running an **activation analyzer** based on machine learning after inference (which is ```O(n)``` with _n_ as the number of individual activations, rather than ```O(k*l)``` applied to each AI layer) to prove ML inference and output analysis, rather than the entire inference.

> This idea is still experimental but could be a valuable asset to prove any large computation **from which we know the normal statistical behavior** (*assuming one exists*).

![ML inference proof img](https://image.noelshack.com/fichiers/2024/44/5/1730466475-capture-d-cran-du-2024-11-01-14-07-43.png)

#### For the AI Provider

When the data is not as sensitive, an AI provider may still want to prove AI inference to:

- Support benchmark claims (to satisfy clients and investors).
- Prove state-of-the-art model inference to paid tier users (ensuring transparency about the model running on the server).

The AI provider will be able to do this **without revealing the trained parameters** by agreeing on a template architecture in a smart contract.

The concept is similar to that described for the user but focuses on keeping the AI provider's data private to prevent IP theft and reverse-engineering.

## Vision

The vision is straightforward: this project will bring a **variety of useful tools** for AI providers and users seeking privacy.

It will act as a **platform** to use **Web3 tools **as a way to tackle today's issues with the fast-moving AI world.

The first services I plan to implement are the **IP-based services**, as they are the simplest and provide a powerful tool for anyone wanting to enforce IP rights on AI ownership.

The **other services** (Provable Inference based services) will be introduced to the platform, converting curious users by providing demos. However, due to the larger computational costs and potential deployment challenges of inference services, I plan to begin developing these after the IP services are established.

> This proposal separates each services in milestones in order to attribue each service a budget for deployement.

## Budget & Milestones

**Requested Budget**: 32,500 MINA.

> Note: This estimate includes potential **hiring** of teammates if the workload becomes too large, especially for the inference services.

- **Deliverables & Budget**:
  - 12,500 MINA => IP Services, including:
    - 7,500 MINA => IP services protocols
    - 5,000 MINA => App deployment (frontend) & (B2B mainly) marketing
  - 20,000 MINA => AI Inference development, including:
    - 15,000 MINA => Inference services protocols (Can be less if not hiring)
    - 5,000 MINA => App deployment (frontend) & additional marketing (B2B & B2C)
  - OPTIONAL (depending ont time and test results) : 20,000 MINA => AI Anomaly prover :
    - 15,000 MINA => Inference services protocols (Can be less if not hiring)
    - 5,000 MINA => App deployment (frontend) & additional marketing (B2B & B2C)
    - I anounce this milestone with reserve, as I first need to conducts tests, and make sure the time factor is not an issue. The budget can also change heavily based on, still unknown, challenges.
    So the budget is set to a high range by default.

- **Mid-Point Milestones**:
  1. AI IP services : contracts.
  2. AI IP services : frontend. (First milestone)
  3. Working AI zk inference.
  4. AI zk inference : backend.
  5. AI zk inference : frontend. (Second milestone)
  6. AI zk ML Prover : backend. 
  7. AI zk ML Prover : frontend. (Third milestone)

- **Project Timeline**: 3 months

- **Wallet Address**: B62qnjaMyWLw11bJDxu2isck8GLmACQK9Ax1VUZNCLt58dv3A9bZar8

## Team Info

- **Proposer GitHub & Achievements**: [GitHub](https://github.com/0BAB1)
- **Proposer Experience**:
  - Previous MINA project : [MINA Punchy Clock](https://github.com/0BAB1/MINA-Punchy-Clock)
  - Previous AI Experience :
  [Lectures as a freelance for inference on FPGA's](https://www.linkedin.com/posts/hugo-babin-riby-79aa89235_course-slides-activity-7245405085604749312-Vhwr?utm_source=share&utm_medium=member_desktop)
  //
  [RISC-V AI accelerator : digital hardware deisgn](https://www.linkedin.com/posts/hugo-babin-riby-79aa89235_cva6-risc-v-report-activity-7196059232499097600-iCbC?utm_source=share&utm_medium=member_desktop)
  //
  [AI on FPGA public tutorials](https://0bab1.github.io/BRH/posts/PY2FPGA/)
- **Team Members**
  - Hugo BRH (aka [0BAB1](https://www.linkedin.com/in/hugo-babin-riby-79aa89235/))

> Using my budget, I may hire additional team members, particularly for the second phase of the project: developing inference services.

## Risks & Mitigations

- The ML anomaly detector might not work as expected if the AI's statistical distribution is not suitable for an ```O(n)``` ML-based anomaly detector. (Solution: Extensive testing in a Python environment with an SVM-based algorithm or similar anomaly detector).
- There may not be enough time to complete the inference service on schedule. (Solution: Hiring additional team members).
- There may not be enough time to complete the ML anomaly prover service on schedule. (Solution: Hiring additional team members).
