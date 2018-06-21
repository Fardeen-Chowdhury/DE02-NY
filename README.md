# DE02-NY
Core Java
  •	Project name CDW_SAPP 
  •	Open the project in Eclipse IDE and check the jdbc connection to mysql and dp.properties file will guide you
  •	After that compile the files
  •	And run it 
RDBMS/mySQL Description:  
  •	To create the table use CDW_SAPP file and run it in mysql
  •	And the table that will be created are 
    	cdw_sapp_branch
    	cdw_sapp_creditcard
    	cdw_sapp_customer
Hadoop/hdfs/dataware housing 
  •	Easy use of terminal is chrome browser by writing ipAddress:4200 in url
      	Use root user in terminal to transfer file to HDFS . Therefore data transferred from relational database with Sqoop is stored            in /home/maria_dev/
            o	/home/maria_dev/CaseStudy_Branch
            o	/home/maria_dev/CaseStudy_CreditCard
            o	/home/maria_dev/CaseStudy_Time
            o	/home/maria_dev/CaseStudy_Customer
Hive and Partition
  •	After sqooping the data to hdfs we created new tables in hive with partiotions
      o	Regular external tables: Branch, CreditCard, CDW_Time, Customer
      o	External partition tables: Partitioned_Branch, Partitioned_ CreditCard, Partitioned_ CDW_Time, Partitioned_ Customer
  •	Then use a Select variable to specify the partitioned and store in a directory /home/maria_dev
      o	Partitioned_Branch/
      o	Partitioned_ CreditCard/
      o	Partitioned_ CDW_Time/
      o	Partitioned_ Customer/
Oozie (Sqoop and Hive)
  •	 First Create a sqoop job and run the sqoop in metastore 
  •	Download json.jre file to avoid any java error
  •	Create workflow using any xml file 
    o	Which will have sqoop job --meta-connect jdbc:hsqldb:hsql://localhost:16000/sqoop
     --exec to execute jobs 
    o	Hive.sql file will be loaded in file system so it can create tables from sqoop job data
  •	Create a job.properties file to execute the workflow.xml 
    o	oozie job --oozie http://localhost:11000/oozie -config /root/Documents/Oozie/job.properties –run
  •	http://localhost:11000/oozie to check if the workflow is working 
  •	 Create a coordinator file so the workflow can keep automating in given time
Oozie (Sqoop and Hive optimized)
  •	After  Ooz workflow, we can run Incremental Oozie workflow for incremental update
  •	 Running same sqoop jobs and  hive 
  •	To run optimized oozie run:
    o	 oozie job --oozie http://localhost:11000/oozie -config /root/Documents/Oozie/job.properties -run

Visualization
  •	In /HiveVisualization directory there are two file firstQuery.q and secondQuery.q



