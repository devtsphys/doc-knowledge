# Azure to AWS and GCP Service Mapping

## AI and Machine Learning

| Azure | AWS | GCP |
| --- | --- | --- |
| **Azure AI Bot Service** | **Amazon Lex** | **Dialogflow CX** |
| **Azure AI Content Safety** | **Amazon Comprehend + Amazon Rekognition Content Moderation** | **Cloud Natural Language + Cloud Vision SafeSearch** |
| **Azure AI Custom Vision** | **Amazon Rekognition Custom Labels** | **Vertex AI AutoML Vision** |
| **Azure AI Face** | **Amazon Rekognition (Face APIs)** | **Cloud Vision Face Detection** |
| **Azure AI Immersive Reader** | **No direct equivalent (use Amazon Polly + Amazon Comprehend)** | **No direct equivalent (use Text-to-Speech + Natural Language API)** |
| **Azure AI Search** | **Amazon Kendra** | **Vertex AI Search** |
| **Azure AI Video Indexer** | **Amazon Rekognition Video** | **Video AI** |
| **Azure Databricks** | **Databricks on AWS** | **Databricks on Google Cloud** |
| **Azure Document Intelligence in Foundry Tools** | **Amazon Textract** | **Document AI** |
| **Azure Language in Foundry Tools** | **Amazon Comprehend** | **Cloud Natural Language API** |
| **Azure Machine Learning** | **Amazon SageMaker** | **Vertex AI** |
| **Azure Open Datasets** | **Registry of Open Data on AWS** | **Google Cloud Public Datasets** |
| **Azure OpenAI Service** | **Amazon Bedrock** | **Vertex AI (Gemini / Model Garden)** |
| **Data Science Virtual Machines** | **Amazon EC2 Deep Learning AMIs** | **Vertex AI Workbench** |
| **Health Bot** | **No direct equivalent (use Amazon Lex + AWS HealthLake)** | **No direct equivalent (use Dialogflow CX + Cloud Healthcare API)** |
| **Microsoft Foundry** | **Amazon Bedrock + Agents for Bedrock** | **Vertex AI Agent Builder** |
| **Azure Speech in Foundry Tools** | **Amazon Transcribe + Amazon Polly** | **Speech-to-Text + Text-to-Speech** |
| **Azure Translator in Foundry Tools** | **Amazon Translate** | **Cloud Translation** |
| **Azure Vision in Foundry Tools** | **Amazon Rekognition** | **Cloud Vision API** |

## Analytics

| Azure | AWS | GCP |
| --- | --- | --- |
| **Azure Analysis Services** | **No direct equivalent (use Amazon Redshift + Amazon QuickSight semantic models)** | **No direct equivalent (use BigQuery + Looker semantic model)** |
| **Azure Chaos Studio** | **AWS Fault Injection Service** | **No direct equivalent (use Chaos Mesh / Litmus on GKE)** |
| **Azure Data Explorer** | **Amazon OpenSearch Service** | **BigQuery** |
| **Azure Data Factory** | **AWS Glue** | **Cloud Data Fusion** |
| **Azure Data Lake Storage** | **Amazon S3 + AWS Lake Formation** | **Cloud Storage + BigLake** |
| **Azure Data Share** | **AWS Data Exchange** | **Analytics Hub** |
| **Azure Stream Analytics** | **Amazon Kinesis Data Analytics** | **Dataflow** |
| **Azure Synapse Analytics** | **Amazon Redshift + Athena + Glue** | **BigQuery** |
| **Event Hubs** | **Amazon Kinesis Data Streams** | **Pub/Sub** |
| **HDInsight** | **Amazon EMR** | **Dataproc** |
| **Microsoft Fabric** | **No direct equivalent (use Redshift + Glue + QuickSight)** | **No direct equivalent (use BigQuery + Dataflow + Looker)** |
| **Microsoft Purview** | **AWS Glue Data Catalog + Lake Formation + Macie** | **Dataplex + Data Catalog + Sensitive Data Protection** |
| **Power BI** | **Amazon QuickSight** | **Looker** |
| **Power BI Embedded** | **Amazon QuickSight Embedded** | **Looker Embedded Analytics** |

## Compute

| Azure | AWS | GCP |
| --- | --- | --- |
| **App Service** | **AWS Elastic Beanstalk** | **App Engine** |
| **Azure Compute Fleet (Preview)** | **Amazon EC2 Fleet** | **Managed Instance Groups + Reservations** |
| **Azure Container Instances** | **Amazon ECS on Fargate (task-level)** | **Cloud Run** |
| **Azure CycleCloud** | **AWS ParallelCluster** | **Google Cloud HPC Toolkit** |
| **Azure Dedicated Host** | **Amazon EC2 Dedicated Hosts** | **Compute Engine Sole-tenant nodes** |
| **Azure Functions** | **AWS Lambda** | **Cloud Functions** |
| **Azure Kubernetes Fleet Manager** | **No direct equivalent (use Amazon EKS + multi-cluster tooling)** | **GKE Fleet** |
| **Azure Kubernetes Service (AKS)** | **Amazon EKS** | **GKE** |
| **Azure Quantum** | **Amazon Braket** | **No direct equivalent (use Google Quantum AI ecosystem)** |
| **Azure Service Fabric** | **No direct equivalent (use Amazon ECS/EKS microservices stack)** | **No direct equivalent (use GKE microservices stack)** |
| **Azure Spot Virtual Machines** | **Amazon EC2 Spot Instances** | **Compute Engine Spot VMs** |
| **Azure Spring Apps** | **No direct equivalent (use AWS App Runner / ECS for Spring apps)** | **No direct equivalent (use Cloud Run / GKE for Spring apps)** |
| **Azure Virtual Desktop** | **Amazon WorkSpaces** | **No direct equivalent (use Citrix / partner VDI on GCP)** |
| **Azure VMware Solution** | **VMware Cloud on AWS** | **Google Cloud VMware Engine** |
| **Batch** | **AWS Batch** | **Cloud Batch** |
| **Cloud Services** | **Amazon EC2 Auto Scaling + Elastic Load Balancing** | **Compute Engine Managed Instance Groups** |
| **SQL Server on Virtual Machines** | **Amazon EC2 for SQL Server** | **Compute Engine for SQL Server** |
| **Static Web Apps** | **AWS Amplify Hosting** | **Firebase Hosting** |
| **Virtual Machine Scale Sets** | **Amazon EC2 Auto Scaling** | **Managed Instance Groups** |
| **Virtual Machines** | **Amazon EC2** | **Compute Engine** |

## Container

| Azure | AWS | GCP |
| --- | --- | --- |
| **App Configuration** | **AWS AppConfig** | **No direct equivalent (use Firebase Remote Config / Config Controller patterns)** |
| **Azure Container Apps** | **AWS App Runner** | **Cloud Run** |
| **Azure Container Registry** | **Amazon ECR** | **Artifact Registry** |
| **Azure Container Storage** | **Amazon EKS with EBS/EFS CSI** | **GKE with Persistent Disk/Filestore CSI** |
| **Azure Red Hat OpenShift** | **Red Hat OpenShift Service on AWS (ROSA)** | **OpenShift on Google Cloud** |
| **Web App for Containers** | **AWS App Runner / ECS on Fargate** | **Cloud Run / GKE** |

## Databases

| Azure | AWS | GCP |
| --- | --- | --- |
| **Azure Cache for Redis** | **Amazon ElastiCache for Redis** | **Memorystore for Redis** |
| **Azure confidential ledger** | **Amazon QLDB** | **No direct equivalent (use Confidential Space + immutability patterns on Spanner/BigQuery)** |
| **Azure Cosmos DB** | **Amazon DynamoDB** | **Firestore** |
| **Azure Database for MySQL** | **Amazon RDS for MySQL** | **Cloud SQL for MySQL** |
| **Azure Database for PostgreSQL** | **Amazon RDS for PostgreSQL / Aurora PostgreSQL** | **Cloud SQL for PostgreSQL / AlloyDB** |
| **Azure Database Migration Service** | **AWS Database Migration Service** | **Database Migration Service** |
| **Azure DocumentDB** | **Amazon DocumentDB** | **No direct equivalent (use MongoDB Atlas on Google Cloud)** |
| **Azure Managed Instance for Apache Cassandra** | **Amazon Keyspaces (for Apache Cassandra)** | **No direct equivalent (use Cassandra on GKE / partner offerings)** |
| **Azure Managed Redis** | **Amazon ElastiCache for Redis** | **Memorystore for Redis Cluster** |
| **Azure SQL** | **Amazon RDS + Aurora SQL portfolio** | **Cloud SQL + AlloyDB + Spanner portfolio** |
| **Azure SQL Database** | **Amazon RDS for SQL Server** | **Cloud SQL for SQL Server** |
| **Azure SQL Managed Instance** | **Amazon RDS for SQL Server** | **Cloud SQL for SQL Server** |
| **Table Storage** | **Amazon DynamoDB** | **Bigtable** |

## Developer Tools

| Azure | AWS | GCP |
| --- | --- | --- |
| **Azure Boards** | **No direct equivalent (use AWS Developer Tools + Jira integration)** | **No direct equivalent (use Cloud Build ecosystem + Jira integration)** |
| **Azure DevOps** | **AWS CodeCatalyst / AWS Developer Tools** | **Cloud Build + Cloud Deploy + Source integrations** |
| **Azure DevTest Labs** | **No direct equivalent (use AWS Service Catalog + sandbox accounts)** | **No direct equivalent (use project templates + quotas + IaC automation)** |
| **Azure Pipelines** | **AWS CodePipeline** | **Cloud Build + Cloud Deploy** |
| **Microsoft Dev Box** | **Amazon WorkSpaces** | **Cloud Workstations** |
| **Microsoft Playwright Testing (Preview)** | **No direct equivalent (use AWS Device Farm + self-hosted Playwright)** | **No direct equivalent (use Cloud Build/GKE runners for Playwright)** |
| **Visual Studio** | **No direct equivalent (desktop IDE; use JetBrains/VS ecosystem on AWS workstations)** | **No direct equivalent (desktop IDE; use Cloud Workstations + local IDE)** |
| **Visual Studio Code** | **AWS Cloud9 (browser IDE)** | **Cloud Shell Editor / Cloud Workstations** |

## DevOps

| Azure | AWS | GCP |
| --- | --- | --- |
| **Azure App Testing** | **No direct equivalent (use AWS Device Farm + load testing stack)** | **No direct equivalent (use Firebase Test Lab + load testing stack)** |
| **Azure Artifacts** | **AWS CodeArtifact** | **Artifact Registry** |
| **Azure Deployment Environments** | **AWS Proton** | **No direct equivalent (use Config Controller + templates)** |
| **Azure Managed Grafana** | **Amazon Managed Grafana** | **Managed Service for Grafana** |
| **Azure Monitor** | **Amazon CloudWatch** | **Cloud Monitoring + Cloud Logging** |
| **Azure Repos** | **AWS CodeCommit** | **Cloud Source Repositories** |
| **Azure Test Plans** | **No direct equivalent (use AWS partner test management tools)** | **No direct equivalent (use third-party test management tools)** |

## Hybrid + Multicloud

| Azure | AWS | GCP |
| --- | --- | --- |
| **Azure Arc** | **AWS Systems Manager + AWS Outposts + EKS Anywhere patterns** | **Anthos** |
| **Azure ExpressRoute** | **AWS Direct Connect** | **Cloud Interconnect** |
| **Azure IoT Edge** | **AWS IoT Greengrass** | **No direct equivalent (use edge runtime patterns on Google Distributed Cloud)** |
| **Azure Kubernetes Service Edge Essentials** | **Amazon EKS Anywhere** | **Google Distributed Cloud** |
| **Azure Local** | **AWS Outposts** | **Google Distributed Cloud** |
| **Azure Operator Nexus** | **No direct equivalent (use AWS telco network solutions + partners)** | **No direct equivalent (use Google Cloud telecom solutions + partners)** |
| **Azure Operator Service Manager** | **No direct equivalent (use AWS telco orchestration stacks)** | **No direct equivalent (use Google Cloud telecom orchestration stacks)** |
| **Azure Stack Edge** | **AWS Snowball Edge** | **No direct equivalent (use Google Distributed Cloud Edge appliances)** |
| **Azure Stack Hub** | **AWS Outposts** | **Google Distributed Cloud Hosted** |
| **Microsoft Defender for Cloud** | **AWS Security Hub + GuardDuty + Inspector** | **Security Command Center** |
| **Microsoft Sentinel** | **No direct equivalent (use Security Lake + partner SIEM)** | **Chronicle SIEM** |

## Identity

| Azure | AWS | GCP |
| --- | --- | --- |
| **Azure Information Protection** | **No direct equivalent (use Amazon Macie + KMS + IAM controls)** | **No direct equivalent (use Sensitive Data Protection + Cloud KMS)** |
| **Microsoft Entra Domain Services** | **AWS Directory Service for Microsoft Active Directory** | **Managed Microsoft AD** |
| **Microsoft Entra External ID** | **Amazon Cognito** | **Identity Platform** |
| **Microsoft Entra ID** | **AWS IAM Identity Center** | **Cloud Identity** |

## Integration

| Azure | AWS | GCP |
| --- | --- | --- |
| **API Management** | **Amazon API Gateway** | **Apigee / API Gateway** |
| **Azure API for FHIR** | **AWS HealthLake** | **Cloud Healthcare API (FHIR)** |
| **Azure Data Manager for Agriculture (Preview)** | **No direct equivalent (use AWS agriculture data lake patterns)** | **No direct equivalent (use Earth Engine + BigQuery agriculture patterns)** |
| **Azure Health Data Services** | **AWS HealthLake** | **Cloud Healthcare API** |
| **Azure Web PubSub** | **API Gateway WebSocket APIs / AppSync subscriptions** | **No direct equivalent (use Pub/Sub + WebSockets on Cloud Run)** |
| **Event Grid** | **Amazon EventBridge** | **Eventarc** |
| **Logic Apps** | **AWS Step Functions** | **Workflows** |
| **Microsoft Azure Data Manager for Energy (Preview)** | **No direct equivalent (use AWS energy data platform patterns)** | **No direct equivalent (use BigQuery-based energy data patterns)** |
| **Service Bus** | **Amazon SQS + Amazon SNS** | **Pub/Sub** |

## Internet of Things (IoT)

| Azure | AWS | GCP |
| --- | --- | --- |
| **Azure Digital Twins** | **AWS IoT TwinMaker** | **No direct equivalent (use partner digital twin solutions on GCP)** |
| **Azure IoT** | **AWS IoT services portfolio** | **No direct equivalent (use Pub/Sub + partner IoT platforms)** |
| **Azure IoT Central** | **AWS IoT Core + IoT Device Management** | **No direct equivalent (use partner IoT application platforms)** |
| **Azure IoT Hub** | **AWS IoT Core** | **No direct equivalent (use Pub/Sub + device gateway patterns)** |
| **Azure IoT Operations** | **No direct equivalent (use AWS IoT SiteWise + Greengrass + IoT Core)** | **No direct equivalent (use edge + Pub/Sub + Dataflow patterns)** |
| **Azure Maps** | **Amazon Location Service** | **Google Maps Platform** |
| **Azure Sphere** | **No direct equivalent (use AWS IoT Device Defender + FreeRTOS patterns)** | **No direct equivalent (use Android Things alternatives / partner secure MCU stacks)** |
| **Microsoft Defender for IoT** | **AWS IoT Device Defender** | **No direct equivalent (use SCC + partner IoT security tools)** |
| **Notification Hubs** | **Amazon SNS + Amazon Pinpoint** | **Firebase Cloud Messaging** |
| **Windows for IoT** | **No direct equivalent (use AWS IoT + Windows ecosystem tooling)** | **No direct equivalent (use partner IoT tooling on GCP)** |

## Management and Governance

| Azure | AWS | GCP |
| --- | --- | --- |
| **Azure Resource Manager templates** | **AWS CloudFormation** | **Infrastructure Manager (Terraform-based) / Deployment Manager legacy** |
| **Automation** | **AWS Systems Manager Automation** | **No direct equivalent (use Workflows + Cloud Scheduler + Automation scripts)** |
| **Azure Advisor** | **AWS Trusted Advisor** | **Recommender** |
| **Azure Backup** | **AWS Backup** | **Backup and DR Service** |
| **Azure Blueprints (Preview)** | **AWS Control Tower + Service Catalog** | **Landing Zone accelerator patterns + Organization Policy** |
| **Cloud Shell** | **AWS CloudShell** | **Cloud Shell** |
| **Azure Copilot** | **Amazon Q Developer (console assistance)** | **Gemini Cloud Assist** |
| **Azure Lighthouse** | **AWS Organizations delegated admin + AWS Systems Manager** | **No direct equivalent (use IAM + org-level delegated operations)** |
| **Azure Managed Applications** | **AWS Service Catalog** | **No direct equivalent (use Google Cloud Marketplace private offerings)** |
| **Azure Migrate** | **AWS Application Migration Service + Migration Hub** | **Migrate to Virtual Machines** |
| **Azure Policy** | **AWS Config + Organizations SCPs** | **Organization Policy Service** |
| **Azure Resource Manager** | **AWS CloudFormation** | **Infrastructure Manager** |
| **Azure Resource Mover** | **No direct equivalent (use AWS migration tooling)** | **No direct equivalent (use migration tooling + replication patterns)** |
| **Azure Service Health** | **AWS Health Dashboard** | **Google Cloud Service Health** |
| **Azure Site Recovery** | **AWS Elastic Disaster Recovery** | **Backup and DR Service** |
| **Azure Update Manager** | **AWS Systems Manager Patch Manager** | **OS patch management via VM Manager + automation** |
| **Cost Management + Billing** | **AWS Cost Explorer + AWS Budgets** | **Cloud Billing + FinOps Hub** |
| **Microsoft Azure portal** | **AWS Management Console** | **Google Cloud Console** |
| **Microsoft Defender for External Attack Surface Management** | **No direct equivalent (use ASM partner tools + AWS native security telemetry)** | **No direct equivalent (use ASM partner tools + Security Command Center)** |

## Media

| Azure | AWS | GCP |
| --- | --- | --- |
| **Azure Front Door and Content Delivery Network (CDN)** | **Amazon CloudFront** | **Cloud CDN** |

## Migration

| Azure | AWS | GCP |
| --- | --- | --- |
| **Azure Data Box** | **AWS Snowball** | **Transfer Appliance** |

## Mobile

| Azure | AWS | GCP |
| --- | --- | --- |
| **Azure Communication Services** | **Amazon Chime SDK** | **No direct equivalent (use partner CPaaS with Google Cloud)** |

## Networking

| Azure | AWS | GCP |
| --- | --- | --- |
| **Application Gateway** | **Application Load Balancer + AWS WAF** | **Cloud Load Balancing + Cloud Armor** |
| **Azure Bastion** | **AWS Systems Manager Session Manager / EC2 Instance Connect Endpoint** | **IAP TCP tunneling + bastion host patterns** |
| **Azure DDoS Protection** | **AWS Shield** | **Cloud Armor DDoS protection** |
| **Azure DNS** | **Amazon Route 53** | **Cloud DNS** |
| **Azure Firewall** | **AWS Network Firewall** | **Cloud Firewall** |
| **Azure Front Door** | **CloudFront + Global Accelerator + AWS WAF** | **Global External Application Load Balancer + Cloud CDN + Cloud Armor** |
| **Azure Private Link** | **AWS PrivateLink** | **Private Service Connect** |
| **Load Balancer** | **Elastic Load Balancing** | **Cloud Load Balancing** |
| **NAT Gateway** | **AWS NAT Gateway** | **Cloud NAT** |
| **Virtual Network** | **Amazon VPC** | **Google Cloud VPC** |
| **Virtual WAN** | **AWS Cloud WAN** | **Network Connectivity Center** |
| **VPN Gateway** | **AWS Site-to-Site VPN** | **Cloud VPN** |
| **Web Application Firewall** | **AWS WAF** | **Cloud Armor** |

## Security

| Azure | AWS | GCP |
| --- | --- | --- |
| **Azure Dedicated HSM** | **AWS CloudHSM** | **Cloud HSM** |
| **Key Vault** | **AWS KMS + AWS Secrets Manager** | **Cloud KMS + Secret Manager** |

## Storage

| Azure | AWS | GCP |
| --- | --- | --- |
| **Archive Storage** | **Amazon S3 Glacier Deep Archive** | **Cloud Storage Archive** |
| **Azure Blob Storage** | **Amazon S3** | **Cloud Storage** |
| **Azure Disk Storage** | **Amazon EBS** | **Persistent Disk** |
| **Azure Elastic SAN** | **No direct equivalent (use Amazon EBS io2 / FSx for ONTAP SAN patterns)** | **No direct equivalent (use Hyperdisk / Persistent Disk SAN patterns)** |
| **Azure Files** | **Amazon EFS / Amazon FSx** | **Filestore** |
| **Azure Managed Lustre** | **Amazon FSx for Lustre** | **No direct equivalent (use partner Managed Lustre on GCP)** |
| **Azure NetApp Files** | **Amazon FSx for NetApp ONTAP** | **Google Cloud NetApp Volumes** |
| **Azure Storage Actions** | **Amazon S3 Batch Operations** | **Cloud Storage Batch Operations** |
| **Queue Storage** | **Amazon SQS** | **Pub/Sub** |
| **Storage Accounts** | **Amazon S3** | **Cloud Storage** |
| **Storage Explorer** | **No direct equivalent (use AWS Toolkit / S3 browser tools)** | **Cloud Storage browser and tooling** |

## Virtual Desktop Infrastructure (VDI)

| Azure | AWS | GCP |
| --- | --- | --- |
| **Azure Lab Services** | **No direct equivalent (use Amazon WorkSpaces/AppStream labs + IAM controls)** | **No direct equivalent (use Cloud Workstations/lab automation patterns)** |

## Web

| Azure | AWS | GCP |
| --- | --- | --- |
| **Azure Fluid Relay** | **No direct equivalent (use AppSync + DynamoDB collaboration patterns)** | **No direct equivalent (use Firebase Realtime Database / Firestore collaboration patterns)** |
| **Azure SignalR Service** | **API Gateway WebSocket APIs / AppSync real-time** | **No direct equivalent (use Firebase + WebSockets on Cloud Run)** |
