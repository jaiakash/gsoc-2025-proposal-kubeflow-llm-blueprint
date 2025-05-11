#  Project #7: GPU Testing for LLM Blueprints

GSoC Page https://summerofcode.withgoogle.com/programs/2025/projects/fwZkvPr0

Project Page: [GPU Testing for LLM Blueprints](https://www.kubeflow.org/events/gsoc-2025/#project-7-gpu-testing-for-llm-blueprints)

Issue: https://github.com/kubeflow/trainer/issues/2432

Mentors:  [@andreyvelich](https://github.com/andreyvelich), [@varodrig](https://github.com/varodrig)

Project Size:  350 hrs

## Summary

This project aims to use self-hosted runners to run GPU-intensive tasks like LLM blueprint or (planned) AI Playground. The necessary infra is provided by Oracle, plan is to use Oracle Kubernetes Engine (OKE) with NVIDIA GPUs for this task. Any code or sample that requires GPU-intensive resources will be transferred to OKE infra instead of generic GitHub infra for faster and more efficient execution.

For now, the idea is to have a specific policy that whenever any Jupyter Notebook code will be added to a trainer/examples/pytorch/** folder (e.g., in trainer/example/pytorch/image-generation/sample.ipynb), that action is transferred to OKE infra by the GitHub self runner. For security reasons, this process will require manual approval from one of the maintainers to trigger the self-runner build. I will set up the GitHub workflow to monitor changes in the respective folder. Once approved, the CI action will execute the code using the GitHub self-runner on the OKE infrastructure. Additionally, we will set up a dashboard for monitoring and metrics to understand usage patterns and identify bottlenecks.

The scope of this project is set up on OKE, but theoretically, this is platform-agnostic; it can be deployed on any Kubernetes cluster with sufficient GPU resources.
