## Key metrics used in SRE.

1. **Service Level Objectives (SLOs):** SLOs define specific targets for system reliability and availability.

2. **Service Level Indicators (SLIs):** SLIs are metrics that quantify the behavior of the system or service, serving as
   the basis for defining SLOs.

3. **Error Budgets:** An error budget represents the acceptable amount of downtime or errors a service can experience
   without violating its SLOs.

4. **Incident Management Metrics:** These metrics track the number of incidents, their severity, and the time it takes
   to resolve them, helping in incident analysis and response improvement.

5. **Mean Time Between Failures (MTBF):** MTBF measures the average time between one failure and the next, indicating
   the system's reliability.

6. **Mean Time to Recover/Repair (MTTR):** MTTR is the average time taken to recover from a failure or resolve an issue,
   influencing system availability.

7. **Traffic Patterns:** Understanding traffic variations, including peak usage hours and seasonal trends, assists in
   capacity planning and performance optimization.

8. **Request Rate and Throughput:** Tracking the number of incoming requests and the system's ability to handle them
   helps gauge performance.

9. **Latency:** Latency measures the time it takes for a request to traverse the system and receive a response,
   affecting user experience.

10. **Resource Utilization:** Monitoring CPU, memory, disk space, and network bandwidth usage provides insights into
    resource efficiency.

## Service Level Agreements (SLAs) or publicly available reliability metrics of two companies

1. **Amazon Web Services (AWS)**:

    * AWS is a leading cloud computing provider, offering a wide range of services to individuals, businesses, and
      governments.
    * AWS has historically published SLAs for some of its services, outlining the guaranteed level of availability and
      performance.
    * For instance, AWS might provide a 99.99% uptime commitment for its Amazon EC2 (Elastic Compute Cloud) instances in
      a
      specific region. This means that AWS guarantees that EC2 instances will be available and responsive for at least
      99.99%
      of the time in that region.
    * Specific services SLAs:
        1. Amazon EC2 (Elastic Compute Cloud) SLA:

           AWS has historically provided a 99.99% uptime commitment for Amazon EC2 instances in a region.
           This SLA guarantees that EC2 instances will be available and operational for at least 99.99% of the time
           within a given region, excluding planned maintenance.
        2. Amazon S3 (Simple Storage Service) SLA:

           AWS has offered a 99.99% uptime commitment for Amazon S3 in the past.
           This means that AWS guarantees the durability of objects stored in S3, and they will be available for
           retrieval 99.99% of the time.
        3. Amazon RDS (Relational Database Service) SLA:

           AWS has provided a 99.99% uptime commitment for Amazon RDS Multi-AZ deployments.
           This SLA ensures that RDS Multi-AZ database instances will be available for at least 99.99% of the time in a
           given
           month.
        4. Amazon CloudFront SLA:

           AWS has historically offered a 99.9% uptime commitment for Amazon CloudFront.
           This SLA ensures that the CloudFront content delivery network will be operational and available for at least
           99.9% of
           the time.
        5. AWS Lambda SLA:

           AWS has provided a 99.95% uptime commitment for AWS Lambda within a region.
           This SLA guarantees that AWS Lambda functions will be available for invocation at least 99.95% of the time
           within a
           region.

2. **Microsoft Azure**:
    * Microsoft Azure is another major cloud computing platform, offering a wide range of services and solutions for
      various business needs.
    * Azure likely has SLAs for several of its services as well, detailing the expected level of reliability and
      availability.
    * As an example, Microsoft Azure might provide a 99.95% uptime commitment for its Virtual Machines service. This
      means
      Azure guarantees that Virtual Machines will be available for at least 99.95% of the time in a specific region.
    * Azure's SLAs might also cover services such as Azure Blob Storage, Azure SQL Database, and others, with
      specific
      commitments for each service.
    * Specific services SLAs:
        1. Virtual Machines SLA:
           Azure has historically provided a 99.95% uptime commitment for Virtual Machines (VMs).
           This SLA guarantees that Azure VMs will be available for at least 99.95% of the time within a specific
           region.
        2. Azure Blob Storage SLA:
           Azure has offered a 99.9% uptime commitment for Azure Blob Storage service in the past.
           This SLA ensures that Azure Blob Storage containers and blobs will be available for at least 99.9% of the
           time.
        3. Azure App Service SLA:
           Azure has provided a 99.95% uptime commitment for Azure App Service.
           This SLA guarantees that the Azure App Service will be available for at least 99.95% of the time within a
           specific region.
        4. Azure SQL Database SLA:
           Azure has historically offered a 99.99% uptime commitment for the Azure SQL Database service.
           This SLA ensures that the Azure SQL Database will be available for at least 99.99% of the time within a
           specific region.
        5. Azure Kubernetes Service (AKS) SLA:
           Azure has provided a 99.95% uptime commitment for Azure Kubernetes Service (AKS) clusters.
           This SLA guarantees that AKS clusters will be available for at least 99.95% of the time within a specific
           region.