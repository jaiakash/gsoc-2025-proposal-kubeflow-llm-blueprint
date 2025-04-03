
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

* Experience
    * Application Developer 1 at **Oracle India** [Linkedin](https://www.linkedin.com/posts/akashjaiswal03_delighted-to-share-that-ive-joined-oracle-activity-7209836874788474880-kg-g?utm_source=share&utm_medium=member_desktop&rcm=ACoAACT2QEUBNmtS9VZzx95JA1g7ebYXa-oO4uM) (June 2024 - Present)
    * Project Intern at **Oracle India** [Linkedin](https://www.linkedin.com/posts/akashjaiswal03_internlife-oracleindia-releasemanagement-activity-7070348281314258944-uSjM?utm_source=share&utm_medium=member_desktop&rcm=ACoAACT2QEUBNmtS9VZzx95JA1g7ebYXa-oO4uM) (May 2023 - Junly 2023) 
    * **GSoC 2022 contributor** at CC Extractor [Linkedin](https://www.linkedin.com/posts/akashjaiswal03_humansofopensource-gsoc-opensource-activity-6933613937011617792-iVXw?utm_source=share&utm_medium=member_desktop&rcm=ACoAACT2QEUBNmtS9VZzx95JA1g7ebYXa-oO4uM) (May 2022 - Oct 2022)
    * Translation Contributor for the **p5.js (Processing Foundation)** [Website](https://p5js.org/events/stf-2024/)
    * 3x startup intern
    * Contributor to **KubeFlow**, **Volcano**, **OWASP,** **Processing Foundation**, **Oppia**, **Keploy**, **Google** and **HackerRank** [Github](https://github.com/jaiakash)

* Community/Leadership/Certification

	* Community

	    * [KubeCon India Blog on CNCF Website](https://www.cncf.io/blog/2025/03/17/kubecon-cloudnativecon-india-2024-from-dreams-to-reality-journey/)
	    * [Micorosft Student Summit, Bangalore](https://www.linkedin.com/posts/akashjaiswal03_microsoft-india-experience-activity-6986299246236872704-C49v?utm_source=share&utm_medium=member_desktop&rcm=ACoAACT2QEUBNmtS9VZzx95JA1g7ebYXa-oO4uM)
	    * [KubeCon India 2024](https://www.linkedin.com/posts/akashjaiswal03_kubeconindia-cloudnative-opensource-activity-7276191568426844160-IgRO?utm_source=share&utm_medium=member_desktop&rcm=ACoAACT2QEUBNmtS9VZzx95JA1g7ebYXa-oO4uM)
	    * [Hack This Fall Community meetup in Hyderabad](https://www.linkedin.com/posts/akashjaiswal03_hackthisfall-htfhyderabad-htflearnings-activity-7086369170346418176-4hiT?utm_source=share&utm_medium=member_desktop&rcm=ACoAACT2QEUBNmtS9VZzx95JA1g7ebYXa-oO4uM)
	    * [WikMedia and IIIT Hyderabad Scholarship](https://www.linkedin.com/posts/akashjaiswal03_wikimediasummit-iiithyderabad-wikimediafoundation-activity-7038195971473686528-t-Ld?utm_source=share&utm_medium=member_desktop&rcm=ACoAACT2QEUBNmtS9VZzx95JA1g7ebYXa-oO4uM)

	* University Leadership
	    * Lead [TeCOS](https://www.instagram.com/tecos.nitt/), the open-source community in college with 1000+ participants to help college juniors about open source and realted programs.
	    * [Technical Secretary, 2023 -2024 NIT Trichy ](https://www.instagram.com/p/Csi7KNXLBAG/?hl=en) (Managing 27 technical club, south-India largest techno-managerical fest [Pragyan](https://pragyan.org/) and [ helping 7000+ student community](https://www.nitt.edu/home/students/clubsnassocs/techclubs/))

	* Certification

	    * [Introduction to KubeFlow Introduction to AI/ML Toolkits with Kubeflow LFS147](https://training.linuxfoundation.org/training/introduction-to-ai-ml-toolkits-with-kubeflow-lfs147/)
	    * [Oracle Cloud Infrastructure 2025 Foundations Associate](https://education.oracle.com/oracle-cloud-infrastructure-2024-foundations-associate/pexam_1Z0-1085-25)
	    * [Certified Kubernetes Application Developer (CKAD)](https://www.coursera.org/account/accomplishments/specialization/WR11U0UCNE52)
	    * [Jenkins - From Zero to Hero Specialization](https://www.coursera.org/specializations/jenkins-zero-to-hero)

* Availability
	I am committed to dedicating **30-35 hours per week** during the GSoC period. My working hours will be: Weekdays (Mon-Fri **4 hours per day**) and Weekends (Sat-Sun **6.5 hours per day**)
	Regular working time slots:
	- 07:00 - 09:00 IST
	- 19:30 - 24:00 IST
	  
	I will have limited availability from August 5th to August 8th due to [KubeCon India](https://events.linuxfoundation.org/kubecon-cloudnativecon-india/). _I have also volunteered to help KubeFlow set up their booth in KubeCon India. 🤞🤞_
	
	I have kept a buffer time to cover any backlog and blockers. Besides this, I have no other prior commitments. If any emergency commitments arise, I will promptly inform mentors to find a suitable workaround.


* Motivation
	I have been active in open soruce since my college days and likes to experiment and contribtuing to open source in my free time. I have been past GSoCer as well. In my my work at Oracle, internally i was tasked to develop a PoC to leverage k8s to run CI/CD pipeline. We were looking to eficiently configure/allocate resource in OKE to run CI/CD pipeline, thats where i got to know about [Volcano's batch scheduling](https://www.cncf.io/blog/2022/06/30/why-spark-chooses-volcano-as-built-in-batch-scheduler-on-kubernetes/). I started reading about Volcano and in turn KubeFlow. I started reading and contributing about MLOps and KubeFlow. 

	Then I started joining community calls of KubeFlow, thats where I told **Chase Christensen** that I work at Oralce. He motivated me to learn and contiribute to Oracle distro of KubeFlow. I also had meet with Andrey, Francisco and Victor, about plan of Oracle donating GPU infra to KubeFlow.
	
	 After my little [experimentation](https://github.com/kubeflow/trainer/issues/2432#issuecomment-2766243340) and research on [trainer/issues/2432](https://github.com/kubeflow/trainer/issues/2432), I am confident to contribute to ths project as GSoC contrbutotr.

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

### TechStack

GitHub Actions (and ACR), Kubernetes, Oracle Cloud, PyTorch, Python, Nvidia drivers, Linux

### Setup LLM Blueprint (Milestone 1 (June 2 - June 10))
To set up the LLM blueprint that can triggered based on admin approval. We have already one sample on in trainer repo, [here](https://github.com/kubeflow/trainer/blob/master/examples/deepspeed/text-summarization/T5-Fine-Tuning.ipynb)
I have tested a sample project for running on my local system. I will adding 2-3 base models of different requirements for our testing.

Here is the branch - [test-self-runner](https://github.com/jaiakash/trainer/tree/test-runner)

Screenshot: ![Screenshot](https://github.com/user-attachments/assets/2e8630fd-8785-499b-a484-d00d9d0aa4e3)

### Github Action (Milestone 2 (June 11 - June 20))
Create a GitHub action for checking changes in files in `trainer/example/self-runner` and wait to trigger the self-runner after approval from the maintainers. Once the maintainer approves the scan, the code is executed in the self-runner (that is OKE infra). Assuming it takes some time and resources, we will implement queuing so that resources don't get flooded with requests. We will maintain a queue for requests, and report the result back to CI accordingly.

![image](https://github.com/user-attachments/assets/6cd595fe-4191-49f2-a897-cb8895d86438)

```
name: Check llm changes and run on self-runner infra

on:
  pull_request:
    paths:
      - 'examples/self-runner/**'

jobs:
  request-approval:
    runs-on: ubuntu-latest
    steps:
      - name: Request maintainer approval
        uses: hmarr/auto-approve-action@v3
        if: github.event.pull_request.user.login == 'jaiakash'
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}

  wait-for-approval:
    needs: request-approval
    runs-on: ubuntu-latest
    steps:
      - name: Wait for maintainer approval
        uses: hmarr/auto-approve-action@v3
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}

  run-llm-code-on-oke-infra:
    needs: wait-for-approval
    runs-on: self-runner
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Run LLM code on OKE Infra
        run: |
          echo "Running on OKE infra"
```

### Setup OKE Cluster with GPU (Milestone 3 (June 21 - July 6))

Here in this milestone I will setting up OKE Cluster with GPU node. 

One good thing about OKE is that it has GPU image preinstalled

Accessing Cluster
- OKE can be accessed with `kubeconfig` file
- Or via Bastian

![image](https://github.com/user-attachments/assets/35e1134a-0ce6-4b02-a732-c16a8f9efece)

System: Ubuntu 22.04

> The GPU image has the GPU drivers pre-installed.

**Images for NVIDIA shapes**

- [GPU driver 570 & CUDA 12.8](https://objectstorage.ca-montreal-1.oraclecloud.com/p/ts6fjAuj7hY4io5x_jfX3fyC70HRCG8-9gOFqAjuF0KE0s-6tgDZkbRRZIbMZmoN/n/hpc_limited_availability/b/images/o/Canonical-Ubuntu-22.04-2024.10.04-0-OCA-OFED-24.10-1.1.4.0-GPU-570-CUDA-12.8-2025.03.26-0)

- [GPU driver 560 & CUDA 12.6](https://objectstorage.ca-montreal-1.oraclecloud.com/p/ts6fjAuj7hY4io5x_jfX3fyC70HRCG8-9gOFqAjuF0KE0s-6tgDZkbRRZIbMZmoN/n/hpc_limited_availability/b/images/o/Canonical-Ubuntu-22.04-2024.10.04-0-OCA-OFED-24.10-1.1.4.0-GPU-560-CUDA-12.6-2025.03.26-0)

- [GPU driver 550 & CUDA 12.4](https://objectstorage.ca-montreal-1.oraclecloud.com/p/ts6fjAuj7hY4io5x_jfX3fyC70HRCG8-9gOFqAjuF0KE0s-6tgDZkbRRZIbMZmoN/n/hpc_limited_availability/b/images/o/Canonical-Ubuntu-22.04-2024.10.04-0-OCA-OFED-24.10-1.1.4.0-GPU-550-CUDA-12.4-2025.03.26-0)

* Reference 
	* https://github.com/oracle-quickstart/oci-hpc-oke
	* https://blogs.oracle.com/java/post/create-k8s-clusters-and-deply-to-oci-from-vscode

### Buffer period (Buffer period (July 7 - July 13))
This buffer period is for covering any backlogs and blockers. This time, I will utilise it to cover any pending changes and fixes. I will also try to demo in of community call.
One of the agendas in this buffer period is to write a blog about the progress and status of the current project. Till this time, the main project would have been completed.

### Setup GitHub Actions Runner Controller (ACR) (Milestone 4 (July 19 - July 27))
[Actions Runner Controller (ARC)](https://docs.github.com/en/actions/hosting-your-own-runners/managing-self-hosted-runners-with-actions-runner-controller/about-actions-runner-controller) is a Kubernetes operator that orchestrates and scales self-hosted runners for GitHub Actions. This is advanced phase of our project where we use k8s operator that is useful to scale and orchetrates pods based on the action CI.

ACR architecture
![Diagram Export Apr 3 2025](https://github.com/user-attachments/assets/9d97113a-a007-458d-b22c-1a0e9be11974)

### OKE Monitoring (Milestone 5 (July 28 - August 10))
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

### AI Playground (Milestone 6 (August 11 - August 24))
This is the final phase of the project, with LLM CI deployment, as in various KubeCons various users wanted to deploy a model quick to test and run KubeFlow. The idea to setup sample models where user can Open Kubeflow Jupyter Notebook -> select Kubeflow LLM blueprint -> fine-tune model with Kubeflow Trainer -> serve it with Kubeflow KServe. We will set up similar GitHub action for it during events. 


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
