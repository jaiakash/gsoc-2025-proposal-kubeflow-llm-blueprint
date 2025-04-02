
#  Project 7: GPU Testing for LLM Blueprints

Project Page: [GPU Testing for LLM Blueprints](https://www.kubeflow.org/events/gsoc-2025/#project-7-gpu-testing-for-llm-blueprints)

Issue: https://github.com/kubeflow/trainer/issues/2432

Mentors:  [@andreyvelich](https://github.com/andreyvelich), [@varodrig](https://github.com/varodrig)

Project Size:  350 hrs

## Summary

The aim of this project is to use self-hosted runners for running GPU intensive tasks like LLM blueprint. The idea is to use Oracle Kubernetes Engine (OKE) with NVIDIA GPUs for this task. Any code or sample which require GPU intensive resource will be transferred to OKE infra instead of generic git-hub infra for faster and efficient execution. Here for now, the idea to have a specific policy where Jupiter notebook code will be added (for eg in trainer/example/self-runner/sample.ipynb), in the PR it requires approval from one of the maintainer to trigger the self runner build. As soon as that is approved. the CI action run the code on the OKE infra. Also plan for including infra metric is there for monitoring and metrics.
Scope of this project is on OKE, but theoretically this can be executed on any k8s cluster with sufficient GPU resource.

## Personal Information

- **Full Name**: Akash Jaiswal
- **Email Address**: akashjaiswal3846@gmail.com
- **GitHub**: https://github.com/jaiakash
- **LinkedIn**: https://www.linkedin.com/in/akashjaiswal03/
- **CNCF Slack**: https://cloud-native.slack.com/team/U02JS2NFSBF
- **University/College**: NIT Trichy, India
- **Degree Program**: B.Tech
- **Year of Study**: Graduated in May 2024
- **Country of Residence**: India
- **Timezone**: IST, UTC+05:30

## Qualifications; Motivation?

SDE at Oracle India, working on POC for using k8s for running pipelines on OKE
Project Intern at Oracle
GSoC 2022 at CC Extractor
Contributior to Google, HackerRank, OWASP

Blogs - KubeCon India Blog, Rooting blog, open source community in college, Technical Secretary 

Certification: Introduction to KubeFlow
Oracle cloud foundation
CKAD
Jenkins

[Highlight your relevant skills, experiences, and qualifications that make you a suitable candidate for this project. Mention any previous work, open-source contributions, or academic achievements that showcase your capabilities. List any/all contributions to Kubeflow community so far.]

Availability - I will dedicate 

[Be clear about your availability and time commitment. State the number of hours per week you plan to dedicate to the project (recommended: 30-40 hours). Mention any potential conflicts (e.g., exams, vacations) and how you plan to address them. It is important to manage expectations upfront and explain how you will manage your time effectively to meet the project deadlines.]

[motivation about why you are interested in working on the project.]

## Goals
- Setup sample LLM Blueprint 
- Setup GPU nodes on OKE
- Setup ACR on OKE Cluster for deploying the llm
- Setup Github Action for manual trigger and runner on OKE cluster
- Metrics and analytics for the GPU Cluster
- [Optional] AI Playground on OKE


## Non-Goals

[Clearly state what is *out* of scope for this project. This helps manage expectations. Example: This project will not include integration with service A., Example: We will not be addressing issue B during this GSoC project.]

- Setup of Cluster with GPU
- I am assuming this will be provided by Oracle
- 

## Technical Details

[Provide an in-depth description of your project's technical aspects. This should include the technologies, programming languages, frameworks, and tools you plan to use. Discuss any potential challenges and how you intend to address them.]

TechStack: GitHub Actions. ACT, Kubernetes, Oracle Cloud, PyTorch, Python, Nvidia drivers, Linux

- Setup LLM Blueprint
To setup llm blueprint that that can triggered based on admin approval

- Setup OKE Cluster
Refrence - https://github.com/oracle-quickstart/oci-hpc-oke

Trigger only on specifc file for eg example/blueprint/

- AI Playground
Setup sample playground where user can deploy llm models and fine tune quicky using KubeFlow and OKE infra.

- Setup ACR
- OKE Monitoring

![OKE monitoring](https://github.com/oracle-quickstart/oci-kubernetes-monitoring/blob/main/logan/images/kubernetes-cluster-summary-dashboard.png)
- Github Action


## Test Plan

[Describe how you plan to test your code to ensure its quality and correctness.]

Local machine with 32gb ram, 1640ti GPU, Ryzen 7 8700G

## Estimation of Deliverables

- **Milestone 0 (May 8 - June 1)**: Community Bonding Period

- **Milestone 1 (June 2 - June 15)**: Setup sample LLM Blueprint

- **Milestone 2 (June 16 - June 29)**: Setup GPU nodes on OKE
    
- **Milestone 3 (June 30 - July 13 )**: Setup ACR on OKE Cluster for deploying the llm

- **Midterm Evaluation (July 14 - July 18)**: Midterm Evaluation for the project

- **Milestone 4 (July 19 - July 27)**: Setup Github Action for manual trigger and runner on OKE cluster

- **Milestone 5 (July 28 - August 10)**: Metrics and analytics for the GPU Cluster

- **Milestone 6 (August 11 - August 24)**: [Optional] AI Playground on OKE

- **Final Submission (Aug 25 - Sept 1)**: Final Submission for the project

## Additional Notes (Optional)

Refrenance: Oracle Docs

KubeFlow Docs

Github ACR Docs

ChatGPT/Google

Thnaks for helping and guidance [@andreyvelich](https://github.com/andreyvelich), [@varodrig](https://github.com/varodrig) [@thesuperzapper](https://github.com/thesuperzapper), [@chasecadet](https://github.com/chasecadet)
