# Data_Pipeline_Architecture
This repository contains about building a data pipeline architecture with the real-time data streaming method of data from Twitter. Stream data on this architecture using the Apache Kafka Platform. Apache KAFKA has core APIs including producer APIs and consumer APIs. To collect data from Twitter, first register an account with the Twitter developer to get access to consumer keys, consumer secrets, access tokens, and access secrets.

# Apache Kafka
We need ZooKeeper to manage and coordinate the Kafka broker. The ZooKeeper service is mainly used to notify Kafka producers and consumers about the presence of a new broker in the Kafka system or the failure of a broker in the Kafka system. According to the notification received by Zookeeper regarding the presence or absence of a broker, producers and consumers make decisions and begin to coordinate their work with several other brokers.
	1. Setup Apache ZooKeeper
		 Zookeeper requires Java to run so first install Java
		 sudo apt update
		 sudo apt upgrade
		 sudo apt install openjdk-14-jdk
		 
		 To check whether java is installed or not, run the following command:
		 java -version
		 
		 First, download the latest version of ZooKeeper using the following command:
		 curl -O https://www.apache.org/dyn/closer.lua/zookeeper/zookeeper-3.7.0/apache-zookeeper-3.7.0-bin.tar.gz
		 
		 After the Zookeeper file has been downloaded, the next step is to extract the file using the following command:
		 tar -xzvf apache-zookeeper-3.7.0-bin.tar.gz
		 
		 The output of the extraction is the zookeeper folder with various source files. we will enter the folder that was extracted earlier
		 cd apache-zookeeper-3.7.0-bin
		 
		 ZooKeeper requires a data folder to store database snapshots of ZooKeeper.
		 mkdir data
		 
		 Next make the configuration of this zookeeper. The trick is to go to the conf directory, then create a file called zoo.cfg.
		 cd conf
		 nano zoo.cfg
		 
		 After that, fill in the following configuration into zoo.cfg earlier. Fill in the dataDir according to the directory where it was created. In this case, 
		 the 	author made it in /home/pingkivila/apache-zookeeper-3.7.0-bin/data.
		 tickTime=2000
		 dataDir=/home/pingkivila/apache-zookeeper-3.7.0-bin/data
		 clientPort=2181
		 initLimit=5
		 syncLimit=2
		 
		After everything is done, it's time to run ZooKeeper with the following command.
		 bin/zkServer.sh start
		 
	1. Setup Apache Kafka
		 First, download the kafka file using the following command.
		 curl -O https://downloads.apache.org/kafka/2.8.0/kafka_2.13-2.8.0.tgz
		 
		 Then extract the file earlier
		 tar -xzvf kafka_2.13-2.8.0.tgz
		 
		 After that, go to the extracted folder, then run Kafka with the following command:
		 cd kafka_2.13-2.8.0
		 bin/kafka-server-start.sh config/server.properties
		 
		 
Remember to always keep Zookeeper up and running when running Kafka.
