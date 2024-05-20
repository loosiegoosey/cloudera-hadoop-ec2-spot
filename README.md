# Cloudera Hadoop EC2 Spot

## Overview

The Cloudera Hadoop EC2 Spot project provides tools and scripts for managing Hadoop clusters on Amazon EC2 spot instances. This setup allows for significant cost savings when running large-scale Hadoop workloads by taking advantage of the lower pricing of spot instances compared to on-demand instances.

## Features

- **Setup and Management**: Handy scripts and utilities for setting up Hadoop clusters on EC2 spot instances.
- **Cost Efficiency**: Leverages EC2 spot instances for cost savings.
- **Easy Configuration**: Modular design for customizing the setup according to user needs.

## Installation Instructions

To install and set up the Cloudera Hadoop EC2 Spot project, follow the steps below:

1. **Clone the Repository**:
    ```bash
    git clone https://github.com/yourusername/cloudera-hadoop-ec2-spot.git
    cd cloudera-hadoop-ec2-spot
    ```

2. **Install Required Dependencies**:
    - Ensure that you have Python installed. You can download it from [python.org](https://www.python.org/).
    - Install the required Python packages:
      ```bash
      pip install -r requirements.txt
      ```

3. **Set Up Your AWS Credentials**:
    - If you don't already have AWS CLI configured, run:
      ```bash
      aws configure
      ```

4. **Run the Setup Script**:
    - Execute the setup script to initialize the Hadoop cluster:
      ```bash
      python setup.py
      ```

## Usage Examples

Here are some examples of how to use the project:

1. **Launching a Cluster**:
    ```python
    from hadoop.cloud import cluster

    cluster.create_cluster(
        cluster_name="my-hadoop-cluster",
        instance_type="m5.xlarge",
        spot_price="0.05",
        num_instances=5
    )
    ```

2. **Listing Active Clusters**:
    ```python
    from hadoop.cloud import cli

    cli.list_clusters()
    ```

3. **Stopping a Cluster**:
    ```python
    from hadoop.cloud import cluster

    cluster.stop_cluster(cluster_name="my-hadoop-cluster")
    ```

## Code Summary

Here's a brief overview of the main files in the project:

- **setup.py**: Main setup script for initializing the project.
- **hadoop/\_\_init\_\_.py**: Initialization script for Hadoop-related components.
- **hadoop/cloud/cli.py**: Command-line interface for managing Hadoop clusters.
- **hadoop/cloud/cluster.py**: Handles creation, deletion, and management of clusters.
- **hadoop/cloud/service.py**: Contains services required for Hadoop cluster operations.
- **hadoop/cloud/storage.py**: Manages cloud storage resources.
- **hadoop/cloud/util.py**: Utility functions for cloud operations.
- **hadoop/cloud/providers/\_\_init\_\_.py**: Initialization script for cloud providers.
- **hadoop/cloud/providers/dummy.py**: Dummy provider for testing purposes.
- **hadoop/cloud/providers/ec2.py**: Amazon EC2 provider implementation.
- **hadoop/cloud/providers/ec2spot.py**: EC2 Spot instances provider implementation.

## Contributing Guidelines

We welcome contributions! If you'd like to contribute to the project, please follow these guidelines:

1. **Fork the Repository**: Create a personal fork of the project on GitHub.
2. **Clone Your Fork**: Clone your forked repository to your local machine.
    ```bash
    git clone https://github.com/yourusername/cloudera-hadoop-ec2-spot.git
    cd cloudera-hadoop-ec2-spot
    ```
3. **Create a Branch**: Create a branch for your feature or bugfix.
    ```bash
    git checkout -b my-feature-branch
    ```
4. **Make Your Changes**: Implement your changes or additions.
5. **Submit a Pull Request**: Push your changes to your forked repository and submit a pull request to the main repository.

Please ensure that your code follows the project's coding style and includes appropriate tests.

## License

This project is licensed under the Apache License, Version 2.0. You may obtain a copy of the License at
[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0).

Feel free to use, modify, and distribute this project in compliance with the License.