# jmeter-docker
<b> Save nessesary files in folder
  testdata->(logs; plans; data)

# Start docker
  
  docker-compose up --build -d

# Starting the Load testing on a master

  docker exec -it jmeter-docker_master_1 bash /apache-jmeter-5.2.1/bin/jmeter -n -t /jmeter/testdata/plans/tests.jmx -l /jmeter/testdata/logs/log.log -j /jmeter/testdata/logs/jlog.log

# Starting the Load testing on a one slave

  docker exec -it jmeter-docker_master_1 bash /apache-jmeter-5.2.1/bin/jmeter -n -t /jmeter/testdata/plans/tests.jmx -l /jmeter/testdata/logs/log.log -j /jmeter/testdata/logs/jlog.log  -R jmeter-docker_slave_1

# For start several slave servers

  docker-compose up --scale slave=5 -d

# Starting the Load testing on five slaves

  docker exec -it jmeter-docker_master_1 bash /apache-jmeter-5.2.1/bin/jmeter -n -t /jmeter/testdata/plans/tests.jmx -l /jmeter/testdata/logs/log.log -j /jmeter/testdata/logs/jlog.log  -R jmeter-docker_slave_1,jmeter-docker_slave_2,jmeter-docker_slave_3,jmeter-docker_slave_4,jmeter-docker_slave_5

# Handful Commands 

<b> Stopping all the containers in a single shot </b>

       $docker stop $(docker ps -a -q)









