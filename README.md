# InfraPulse

Infrastructure monitoring and alerting on AWS EC2 using Docker Compose, Prometheus, Grafana and Node Exporter.

## Features
- Dashboard with CPU, memory, disk and network panels
- Three alert rules: CPU above 80%, memory above 85%, disk above 80%
- Email alerts through Gmail SMTP
- Persistent storage with Docker named volumes
- Grafana and Prometheus bound to localhost and reached through an SSH tunnel

## Stack
AWS EC2 (t3.micro, RHEL 10.2), Docker, Docker Compose, Prometheus, Grafana 12.3.0, Node Exporter, Gmail SMTP

## Setup
> The configuration files are a reference setup based on the deployed project. The original EC2 instance has since been deleted.

1. Create a `.env` file with your Grafana admin and SMTP credentials (not included in this repo).
2. Start the stack: `docker compose up -d`
3. Open an SSH tunnel: `ssh -i <key>.pem -L 3000:127.0.0.1:3000 -L 9090:127.0.0.1:9090 ec2-user@<EC2-PUBLIC-IP>`
4. Open Grafana at `http://localhost:3000` and Prometheus at `http://localhost:9090`.

## Full Report
See [InfraPulse_Report.pdf](InfraPulse_Report.pdf) for the full walkthrough with screenshots.

## Author
Mohammed Sanjid, Cloud & DevOps Trainee
