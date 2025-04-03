#  Project #7: GPU Testing for LLM Blueprints

Project Page: [GPU Testing for LLM Blueprints](https://www.kubeflow.org/events/gsoc-2025/#project-7-gpu-testing-for-llm-blueprints)

Issue: https://github.com/kubeflow/trainer/issues/2432

Mentors:  [@andreyvelich](https://github.com/andreyvelich), [@varodrig](https://github.com/varodrig)

Project Size:  350 hrs

## Summary

This project aims to use self-hosted runners for running intensive tasks like LLM blueprint or planned AI Playground. The original idea is to use Oracle Kubernetes Engine (OKE) with NVIDIA GPUs for this task. Any code or sample that requires GPU-intensive resources will be transferred to OKE infra instead of generic GitHub infra for faster and more efficient execution. 
For now, the idea is to have a specific policy where Jupiter notebook code will be added to a `trainer/example/self-runner` folder (e.g., in trainer/example/self-runner/sample.ipynb) for running in OKE infra. In the PR, it requires approval from one of the maintainers to trigger the self-runner build. I will set up the GitHub workflow for checking the changes in the respective folder. As soon as that is approved, the CI action runs the code using GitHub self-runner on the OKE infra. I will also set up a dashboard for monitoring and metrics to understand usage and bottlenecks.
The scope of this project is set up on OKE, but theoretically, this is platform-agnostic; it can be deployed on any Kubernetes cluster with sufficient GPU resources.

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

2024 SDE at Oracle India, working on PoC for using k8s for running pipelines on OKE
2023 Project Intern at Oracle
2022 GSoC 2022 at CC Extractor
Contributor to OWASP, Volcano, Processing, Oppia, Keploy, Google and HackerRank

Blogs – KubeCon India Blog https://www.cncf.io/blog/2025/03/17/kubecon-cloudnativecon-india-2024-from-dreams-to-reality-journey/
Rooting blog - https://medium.com/delta-force/rooting-custom-roms-part-1-56aff6094388 
Leadership - Lead the open source community in college, 
Technical Secretary, 2023 -2024 NIT Trichy 

Certification:
Introduction to KubeFlow Introduction to AI/ML Toolkits with Kubeflow LFS147
Oracle Cloud foundation
[Certified Kubernetes Application Developer (CKAD)](https://www.coursera.org/account/accomplishments/specialization/WR11U0UCNE52)
Jenkins

[Highlight your relevant skills, experiences, and qualifications that make you a suitable candidate for this project. Mention any previous work, open-source contributions, or academic achievements that showcase your capabilities. List any/all contributions to Kubeflow community so far.]

### Availability
I am committed to dedicating 30-35 hours per week during the GSoC period.
    
Regular working time slots:
- 07:00 - 09:00 IST
- 19:30 - 24:00 IST

My working hours will be:
- Weekdays (Mon-Fri): 4 hours per day
- Weekends (Sat-Sun): 6.5 hours per day
  
I will have limited availability from August 5th to August 8th due to [KubeCon India](https://events.linuxfoundation.org/kubecon-cloudnativecon-india/). I have also volunteered to help KubeFlow set up their booth. 🤞🤞
I have kept a buffer time to cover any backlog and blockers. Besides this, I have no other prior commitments. If any new commitments arise, I will promptly inform my mentor to find a suitable workaround.

[motivation about why you are interested in working on the project.]
I like experimentastion and contribtuing to oepn sopruce in my free time, from my work at oracle i started using k8s and jenkins. I was looking for anything to contribute to that, then I got Kubeflow.

## Goals
- Setup sample LLM Blueprint 
- Setup GPU nodes on OKE
- Setup ACR on OKE Cluster for deploying the llm
- Setup GitHub Action for manual trigger and runner on OKE cluster
- Metrics and analytics for the GPU Cluster
- [Optional] AI Playground on OKE


## Non-Goals

- Cluster with GPU should be provided by Oracle for prod deployment. For testing, I have my decent enough personal machine (Ryzen 7 8600G, 32GB RAM, Nvidia RTX 4060) to test this.
- Once the infra for self-runner is set up, running AI Playground requires minimal setup. The main scope of this project is to set infra for running the LLM blueprint on OKE infra. AI Playground is 2nd priority for this GSoC project, but I will continue if it's not complete within the GSoC period.

## Technical Details

TechStack: GitHub Actions (and ACR), Kubernetes, Oracle Cloud, PyTorch, Python, Nvidia drivers, Linux

- Setup LLM Blueprint
To setup llm blueprint that that can triggered based on admin approval. We have already one sample which i asked from @andrey, 

I have tested a sample project for running on my local system. Here is the branch - https://github.com/jaiakash/trainer/tree/test-runner
Screenshots: ![image](https://github.com/user-attachments/assets/6cd595fe-4191-49f2-a897-cb8895d86438)

- Github Action
Create a GitHub action for checking changes in files in `trainer/example/self-runner` and wait to trigger the self-runner after approval from the maintainers. Once the maintainer approves the scan, the code is executed in the self-runner (that is OKE infra). Assuming it takes some time and resources, we will implement queuing so that resources don't get flooded with requests. We will maintain a queue for requests, and report the result back to CI accordingly.

![image](https://github.com/user-attachments/assets/6cd595fe-4191-49f2-a897-cb8895d86438)

- Setup OKE Cluster
Refrence - https://github.com/oracle-quickstart/oci-hpc-oke

Trigger only on specifc file for eg example/blueprint/


- Setup GitHub Actions Runner Controller (ACR)
Actions Runner Controller (ARC) is a Kubernetes operator that orchestrates and scales self-hosted runners for GitHub Actions. This is advanced version of k8s operator that is useful for our requirments to scale and orchetrates pods based on the action CI. 

ACR architecture
![Diagram Export Apr 3 2025](https://github.com/user-attachments/assets/9d97113a-a007-458d-b22c-1a0e9be11974)


- OKE Monitoring
For admins, we also need to maintain monitoring to see the metrics and resource utilisation of the OKE infra. Oracle already provides an open-source sample for [OKE Monitoring](https://github.com/oracle-quickstart/oci-kubernetes-monitoring), so we can leverage that. 
Out of various options, installation via [Helm](https://github.com/oracle-quickstart/oci-kubernetes-monitoring#helm) is sufficient for our basic needs.

Estimated monthly cost: $0/month

    Metrics needed
    - Avg CPU usage
    - Avg GPU usage
    - Peak GPU usage
    - Avg queue timing
    - Avg build timing


![OKE monitoring](https://github.com/oracle-quickstart/oci-kubernetes-monitoring/blob/main/logan/images/kubernetes-cluster-summary-dashboard.png)

- AI Playground
Setup sample playground where user can deploy llm models and fine tune quicky using KubeFlow and OKE infra.


## Test Plan

[Describe how you plan to test your code to ensure its quality and correctness.]

Local machine with 32GB RAM, 1640ti GPU, Ryzen 7 8700G

## Estimation of Deliverables

- **Milestone 0 (May 8 - June 1)**: Community Bonding Period

- **Milestone 1 (June 2 - June 10)**: Setup sample LLM Blueprint

- **Milestone 2 (June 11 - June 20)**: Setup Github Action for manual trigger and runner on OKE cluster
    
- **Milestone 3 (June 21 - July 6 )**: Setup GPU nodes on OKE

- **Buffer Period (July 7 - July 13 )**: Buffer period for any backlogs and blogs

- **Midterm Evaluation (July 14 - July 18)**: Midterm Evaluation for the project

- **Milestone 4 (July 19 - July 27)**: Setup ACR on OKE Cluster for deploying the llm

- **Milestone 5 (July 28 - August 10)**: Metrics and analytics for the GPU Cluster

- **Milestone 6 (August 11 - August 24)**: [Optional] AI Playground on OKE

- **Final Submission (Aug 25 - Sept 1)**: Final Submission for the project

## Reference

Oracle Docs https://oracle.github.io/fmw-kubernetes/wccontent-domains/oracle-cloud/prepare-oke-environment/
https://github.com/oracle/weblogic-kubernetes-operator/blob/main/kubernetes/hands-on-lab/tutorials/setup.oke.ocishell.md

KubeFlow Docs https://www.kubeflow.org/docs/components/trainer/getting-started/
https://www.kubeflow.org/docs/started/architecture/

GitHub ACR Docs https://docs.github.com/en/actions/hosting-your-own-runners/managing-self-hosted-runners-with-actions-runner-controller/about-actions-runner-controller

GitHub Self Runner Docs https://docs.github.com/en/actions/hosting-your-own-runners/managing-self-hosted-runners/adding-self-hosted-runners

Cloude 3.5 Sonnet - For formatting text and improving this proposal

Diagram - https://app.eraser.io/

Thanks for helping and guidance [@andreyvelich](https://github.com/andreyvelich), [@varodrig](https://github.com/varodrig) [@thesuperzapper](https://github.com/thesuperzapper), [@chasecadet](https://github.com/chasecadet), [@varodrig](https://github.com/varodrig)
