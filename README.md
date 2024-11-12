# Home Lab - Google Cloud Platform (GCP) VPC Network Setup

This project demonstrates the setup of a Virtual Private Cloud (VPC) network on Google Cloud Platform (GCP) with network segmentation, access control, and monitoring configurations. This setup emulates a secure, scalable network environment, making it ideal for learning cloud network management and showcasing skills in cloud-based infrastructure and security.

## Project Overview

The VPC network is segmented into two subnets:
- **Internal Subnet**: Hosts private resources with no direct internet access, suitable for sensitive internal services.
- **DMZ Subnet**: Hosts public-facing resources with controlled internet access, ideal for web servers or other public services.

Network traffic is controlled through custom firewall rules, and monitoring is configured to ensure network security and performance.

## Features

- **Custom VPC and Subnets**: A VPC with custom subnets (`internal-subnet` and `dmz-subnet`) to simulate a real-world corporate network structure.
- **Firewall Rules**: Configured firewall rules to control SSH, HTTP, and HTTPS access, implementing a least-privilege model.
- **Virtual Machine Deployment**: Separate VMs deployed in each subnet to demonstrate network isolation and controlled external access.
- **Private Google Access**: Configured for the internal subnet, allowing VMs without external IPs to securely access Google services.
- **Monitoring and Logging**: Enabled VPC Flow Logs and created monitoring dashboards and alerts for real-time network traffic and performance visibility.

## Project Structure

This project includes the following setup steps:

1. **VPC Creation**: Configuring a custom VPC for secure, segmented network infrastructure.
2. **Subnet Configuration**: Adding `internal` and `dmz` subnets with specific IP ranges and regions.
3. **Firewall Rules**: Creating rules for SSH access (internal only) and HTTP/HTTPS access (DMZ only).
4. **Virtual Machines**: Deploying VMs in each subnet to simulate internal and public resources.
5. **Private Google Access**: Enabling secure access to Google services for internal VMs.
6. **Monitoring & Alerts**: Setting up custom dashboards, VPC Flow Logs, and alerting policies for network health and security.

## Setup Instructions

### Prerequisites

- Google Cloud Platform account with billing enabled
- Basic familiarity with GCP Console and networking concepts

### Step-by-Step Guide

1. **Set Up the Project**: 
   - Create a new GCP project and enable billing to access full GCP features.

2. **Create a VPC Network**:
   - In the GCP Console, navigate to **VPC Network** > **Create VPC**.
   - Choose **Custom Mode** and configure IP ranges and regions for `internal-subnet` and `dmz-subnet`.

3. **Configure Firewall Rules**:
   - Go to **VPC Network** > **Firewall** and set up rules to control SSH, HTTP, and HTTPS access.

4. **Deploy VMs in Each Subnet**:
   - Use **Compute Engine** > **VM instances** to deploy VMs:
     - **Internal VM**: Assign to `internal-subnet` without an external IP.
     - **DMZ VM**: Assign to `dmz-subnet` with an external IP for public access.

5. **Enable Private Google Access**:
   - For the internal subnet, enable **Private Google Access** to allow secure API access without an external IP.

6. **Set Up Monitoring and Alerts**:
   - Enable **Google Cloud Operations Suite**.
   - Create a custom dashboard for key metrics and set up alerts for unusual traffic patterns or high CPU usage.

## Testing and Validation

- **Internal VM Access**: Confirm SSH access is restricted based on firewall settings.
- **DMZ VM Public Access**: Test HTTP/HTTPS accessibility from a public IP to validate DMZ subnet rules.
- **Monitoring**: Verify that the dashboard displays real-time metrics, and trigger test alerts to confirm notifications.

## Key Takeaways

This project highlights critical skills in:
- Network segmentation and security best practices on Google Cloud Platform.
- Implementing least-privilege access with firewall rules.
- Monitoring and alerting for proactive network management.

## Future Enhancements

- **Advanced IAM Policies**: Apply specific IAM roles to control access at a finer-grained level.
- **Automated Infrastructure with IaC**: Use Terraform or Deployment Manager to automate this setup.
- **Enhanced Security**: Integrate Google Cloud Armor or Cloud Identity for additional security layers.

## License

This project is open-source and available under the MIT License.

---

This `README.md` provides an overview and instructions for replicating a secure, segmented VPC network setup on Google Cloud Platform, ideal for both educational purposes and cloud portfolio projects.
