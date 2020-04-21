#UPDATE 2020
## in order to run this locally:
1. Start the data stores

PostgreSQL and SQL Server databases are stored in Docker containers. These containers should be started first so the databases are on-line when the application logic containers start up. 

Go to DIR:
{your-drive}\SmartHotel360-Backend\Source\Backend\src>

Start the data stores first by typing:

docker-compose up sql-data reviews-data tasks-data

Wait for those containers to be initialized; you'll know they're ready once the console output stops appearing for longer than a minute. The screen shot below demonstrates the data store containiners' setup being complete and with them in a ready state.

Data containers up

2. Start the microservices

Once the data stores are running, the microservices can be started. BUT BEFORE, UPDATE THE 2 pom.xml (tasks, reviews) FILES LOCATED @ 
{your-drive}\SmartHotel360-Backend\Source\Backend\src\SmartHotel.Services.Tasks
{your-drive}\SmartHotel360-Backend\Source\Backend\src\SmartHotel.Services.Reviews

FROM 
	<repositories>
       <repository>
          <id>central</id>
          <name>Central</name>
          <url>http://repo1.maven.org/maven2</url>
       </repository>
    </repositories>

TO
	<repositories>
       <repository>
          <id>central</id>
          <name>Central</name>
          <url>https://repo1.maven.org/maven2</url> <!-- HTTPS HERE, CHECK CONNECTION IN BROWSER-->
       </repository>
    </repositories>
TO AVOID THE 'Non-resolvable parent POM' ERROR 

Open a new terminal window and execute a second call to docker-compose, this time with no images specified.

    Note: It is important that you open a new terminal window and leave the first one running. Killing the terminal process with a Ctrl-C will stop all of the data containers.

docker-compose up

This will start all the remaining containers. Once the containers are online the terminal should stop updating for a few seconds. The terminal screen shot below demonstrates what the terminal should look like once all the microservice containers are running.

Microservices up


# **This project is retired, archived, and no longer supported. You are welcome to continue to use and fork the repository.**

## For the latest sample references visit: https://aka.ms/tailwindtraders & https://aka.ms/rpsls 

# SmartHotel360
During **Connect(); 2017** event this year we presented beautiful app demos using Xamarin and many features of Azure. For //build/ 2018's keynote, we updated some components of the back-end API code to support **Azure Kubernetes Service (AKS)**.

# SmartHotel360 Repos
For this reference app scenario, we built several consumer and line-of-business apps and an Azure backend. You can find all SmartHotel360 repos in the following locations:

- [SmartHotel360](https://github.com/Microsoft/SmartHotel360)
- [IoT](https://github.com/Microsoft/SmartHotel360-IoT)
- [Mixed Reality](https://github.com/Microsoft/SmartHotel360-MixedReality)
- [Backend](https://github.com/Microsoft/SmartHotel360-Backend)
- [Website](https://github.com/Microsoft/SmartHotel360-Website)
- [Mobile](https://github.com/Microsoft/SmartHotel360-Mobile)
- [Sentiment Analysis](https://github.com/Microsoft/SmartHotel360-SentimentAnalysis)
- [Registration](https://github.com/Microsoft/SmartHotel360-Registration)

# SmartHotel360 - Backend Services

Welcome to the SmartHotel360 AKS repository. Here you'll find everything you need to run the backend services locally and/or deploy them in a AKS cluster.

## Getting Started

SmartHotel360 uses a **microservice oriented** architecture implemented using containers. There are various services developed in different technologies: .NET Core 2, Java, and Node.js. These services use different data stores like PostgreSQL and SQL Server. 

We have added an ARM template so you can automate the creation of the resources

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3a%2f%2fraw.githubusercontent.com%2fMicrosoft%2fSmartHotel360-Backend%2fmaster%2fSource%2farm%2fsmarthote360.backend.deployment.json"><img src="/Documents/Images/deploy-to-azure.png" alt="Deploy to Azure"/></a>

1. [Demo Setup](Documents/Setup.md) - Create the Azure resources and demo environment setup, and deploy the SmartHotel360 services to the AKS Cluster.

# Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us the rights to use your contribution. For details, visit https://cla.microsoft.com.

When you submit a pull request, a CLA-bot will automatically determine whether you need to provide a CLA and decorate the PR appropriately (e.g., label, comment). Simply follow the instructions provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
