# Grafana Dashboards

Welcome to the repository for CCE Grafana dashboards. Here you will find a collection of pre-configured dashboards designed to help you monitor and visualize various aspects of your infrastructure and applications.

## Getting Started

Follow the instructions below to import and use the Grafana dashboards from this repository.

### Prerequisites

- A running Grafana instance (you can check out `./helm/` directory for a basic deployment)
- Appropriate data sources configured in Grafana (e.g., Prometheus, InfluxDB, etc.)

### Importing a Dashboard

1. **Log in to Grafana**:
   - Open your Grafana instance and log in with your credentials.

2. **Access the Import Dashboard Feature**:
   - In the top right corner, click on the **+** icon and then select **Import**.

3. **Get the Dashboard JSON**:
   - Browse through the repository and find the JSON file for the dashboard you want to import.
   - Copy the raw JSON content of the file.

4. **Import the JSON**:
   - In Grafana, paste the JSON into the **Import via panel JSON** section.

5. **Configure the Dashboard**:
   - Select which folder you want to place the dashboard in.
   - Map the dashboard to the appropriate data source if prompted.
   - Click **Import** to complete the process.

## Available Dashboards

Here are some of the dashboards you can find in this repository:

- **Kube-API Monitoring Dashboard**: A comprehensive dashboard for monitoring Kubernetes API server performance and health. [location](https://github.com/opentelekomcloud-community/cce-grafana-dashboards/tree/main/kube-api)

## Contributing

We welcome contributions! If you have created a useful dashboard and would like to share it, please follow these steps:

1. Fork the repository.
2. Create a new branch: `git checkout -b feature/my-new-dashboard`.
3. Add your dashboard JSON file to the repository.
4. Commit your changes: `git commit -m 'Add new dashboard'`.
5. Push to the branch: `git push origin feature/my-new-dashboard`.
6. Submit a pull request.

## License

This repository is licensed under the GNU General Public License Version 3. See the [LICENSE](LICENSE) file for more information.

---

For more information on Grafana dashboards, visit the official [Grafana Documentation](https://grafana.com/docs/grafana/latest/dashboards/).

