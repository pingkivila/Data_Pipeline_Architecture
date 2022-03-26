# Data_Pipeline_Architecture




## 
![Untitled Diagram(6) fix](https://user-images.githubusercontent.com/89646884/160223544-fc5ce916-a547-4df7-9692-82d5abd02c89.jpg)

## Description

This repository contains about building a data pipeline architecture with the real-time data streaming method of data from Twitter. Stream data on this architecture using the Apache Kafka Platform. Apache KAFKA has core APIs including producer APIs and consumer APIs. To collect data from Twitter, first register an account with the Twitter developer to get access to consumer keys, consumer secrets, access tokens, and access secrets. After getting access from twitter, then it is connected to kafka to collect streaming data. This process uses a python script. The streaming data will be displayed in csv format. The data will be stored in cloud storage then analyzed in Bigquery and visualized in kibana.

## Apache Kafka

[We need ZooKeeper to manage and coordinate the Kafka broker. The ZooKeeper service is mainly used to notify Kafka producers and consumers about the presence of a new broker in the Kafka system or the failure of a broker in the Kafka system. According to the notification received by Zookeeper regarding the presence or absence of a broker, producers and consumers make decisions and begin to coordinate their work with several other brokers.](https://linktodocumentation)


## 🚀 Setup Apache ZooKeeper



Zookeeper requires Java to run so first install Java

```bash
sudo apt update
sudo apt upgrade
sudo wget https://download.java.net/java/GA/jdk14/076bab302c7b4508975440c56f6cc26a/36/GPL/openjdk-14_linux-x64_bin.tar.gz
sudo tar -xzvf openjdk-14_linux-x64_bin.tar.gz
```

In this step, we will configure the environment variable to use the JDK installed by us via the command line.

```bash
sudo nano /etc/profile
```

Scroll down by pressing Page Down button and add at the end of this file:

```bash
# Java 14
JAVA_HOME=/usr/java/oracle/jdk-14
PATH=$PATH:$HOME/bin:$JAVA_HOME/bin
export JAVA_HOME
export PATH
```

We can configure the Java commands to use the newly installed JDK by default. We can check the installed Java before and after executing these commands as shown below:
```bash
# Configure Java Alternatives
sudo update-alternatives --install "/usr/bin/java" "java" "/usr/java/oracle/jdk-14/bin/java" 1

# Configure Javac Alternatives
sudo update-alternatives --install "/usr/bin/javac" "javac" "/usr/java/oracle/jdk-14/bin/javac" 1
```

To check whether java is installed or not, run the following command:

```bash
java -version
```

First, download the latest version of ZooKeeper using the following command:
```bash	
curl -O https://www.apache.org/dyn/closer.lua/zookeeper/zookeeper-3.7.0/apache-zookeeper-3.7.0-bin.tar.gz
```		 
After the Zookeeper file has been downloaded, the next step is to extract the file using the following command:
```bash
tar -xzvf apache-zookeeper-3.7.0-bin.tar.gz
```		 
The output of the extraction is the zookeeper folder with various source files. we will enter the folder that was extracted earlier
```bash
cd apache-zookeeper-3.7.0-bin
```		 
ZooKeeper requires a data folder to store database snapshots of ZooKeeper.
```bash
mkdir data
```		 
Next make the configuration of this zookeeper. The trick is to go to the conf directory, then create a file called zoo.cfg.
```bash
cd conf
nano zoo.cfg
```		 
After that, fill in the following configuration into zoo.cfg earlier. Fill in the dataDir according to the directory where it was created. In this case, 
the author made it in /home/pingkivila/apache-zookeeper-3.7.0-bin/data.
```bash
tickTime=2000
dataDir=/home/pingkivila/apache-zookeeper-3.7.0-bin/data
clientPort=2181
initLimit=5
syncLimit=2
```		 
After everything is done, it's time to run ZooKeeper with the following command.
```bash
bin/zkServer.sh start
```    
## 🚀 Setup Apache Kafka

First, download the kafka file using the following command.
```bash
curl -O https://downloads.apache.org/kafka/2.8.0/kafka_2.13-2.8.0.tgz
```		 
Then extract the file earlier
```bash
tar -xzvf kafka_2.13-2.8.0.tgz
```		 
After that, go to the extracted folder, then run Kafka with the following command:
```bash
cd kafka_2.13-2.8.0
bin/kafka-server-start.sh config/server.properties
```    
## 🛠 Skills
Python, SQL, Linux, Spark, BigQuery


## 🔗 Links
[![kaggle](https://img.shields.io/badge/kaggle-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://www.kaggle.com/pingkivila/)
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/pingki-vila-9a1a27226/)

