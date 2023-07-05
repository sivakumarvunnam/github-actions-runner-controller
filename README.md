# github-actions-runner-controller
step-by-step process to implement automatic scaling with GitHub Actions and self-hosted runners on an existing Amazon EKS cluster

Set up self-hosted runners:
a. Launch EC2 instances or provision virtual machines that will act as your self-hosted runners within your existing EKS cluster. Ensure these instances have the necessary resources and configurations.
b. Install and configure the self-hosted runners on each EC2 instance or virtual machine. You can follow GitHub's documentation for detailed instructions on setting up self-hosted runners.

Configure runner groups:
a. Identify logical units or categories for your self-hosted runners based on your infrastructure and requirements. For example, you could have different groups for different machine types, such as small, medium, and large.
b. Define runner groups within your GitHub repository settings. Specify the number of concurrent jobs that each group can handle. This will determine the scaling behavior of your runners.

Assign labels to runners:
a. Assign labels to your self-hosted runners based on their characteristics. For example, you could use labels like "small", "medium", "large", or other relevant tags.
b. Label each runner based on its capabilities, available resources, or geographical location. Labels will be used to categorize and identify runners for specific workflows.

Create or modify workflows:
a. In your GitHub Actions workflows, specify the runner groups and labels that should be used for each job. This can be done in the YAML file defining your workflow.
b. Update your workflows to utilize the self-hosted runner groups and labels, allowing GitHub Actions to select the appropriate runners for each job.

Adjust runner group concurrency:
a. Determine the desired concurrency settings for each runner group. This depends on your workload and available resources.
b. Configure the concurrency settings for each runner group in the repository settings on GitHub. Adjust the concurrency to increase or decrease the number of jobs that can run simultaneously in each group.

Monitor and adjust:
a. Monitor the performance and utilization of your self-hosted runners, both within the EKS cluster and on the EC2 instances or virtual machines.
b. Utilize GitHub's monitoring and metrics to understand resource usage and identify potential bottlenecks or areas for improvement.
c. Based on your observations, make adjustments to the scaling settings, such as increasing or decreasing the concurrency or adding/removing runners from a group.

By following these steps, you can implement automatic scaling with GitHub Actions and self-hosted runners on your existing EKS cluster. This allows you to leverage your own infrastructure efficiently and adapt to varying workloads while utilizing the benefits of GitHub Actions
