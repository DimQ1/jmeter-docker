# jmeter-docker
<b> Save nessesary files in folder
  testdata\
         logs
         plans
         datasets

<b> Start docker
  
  docker-compose up --build

<b> Starting the Load testing

      $docker exec -it <container-on-master-node> bash
      root@4954e3ef40f6:/# jmeter -n -t ./jmeter/testdata/plans/sample.jmx -l ./jmeter/testdata/logs/$(date +"%m-%d-%Y_%H_%M_%S")-log.jtl
       

# Handful Commands 

<b> Stopping all the containers in a single shot </b>

       $docker stop $(docker ps -a -q)









