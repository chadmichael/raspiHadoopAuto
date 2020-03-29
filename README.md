Ansible automation for the hadoop / spark pi cluster
=====================================================

Purpose
-------

Create Apache Hadoop cluster out of four raspi's.

Hadoop is open source cluster computing software.  Includes a distributed file system (HDFS) to store data across cluster,
as well as a distributed resource manager (YARN) for giving resources for execution of parallel jobs across worker nodes.

On top of YARN/Hadoop will be Apache Spark.  This layer of defining the jobs to be executed in parallel across the cluster
is pluggable.  Older big data applications used Apache MapReduce for this layer; Spark is gaining favor.

Systems
-------

**Raspberry Pi 4B** with 4GB and ample SD cards ( the SD cards are the storage, so for real big data this just won't work, 
but it's good enough for dev purposes )  

**Raspbian OS** ( raspberry pi specific flavor of Debian )  

I tried to use Ubuntu, but Ubuntu's server or core distributions ( stripped down for production work, i.e. no desktop but also no easy wifi ... ) but found that I benefit by the ease of wifi and other home lab niceties not found in these lean production tuned base OS flavors. 

One hassle though ... I had to remove Java 11, which simply wouldn't be there on the Ubuntu Server or Ubuntu Core because Java 11 is not supported across the jave ecosystem yet, and is therefore not a player in production systems yet.
Open JDK 8 ( from Raspbian's APT repos )

Automation
----------

Ansible Playbooks -- simple tool for automating system configuration and application deployment.  Agentless.
Only need python installed on the system from which you orchestrate, my laptop generally in my home environment.     

