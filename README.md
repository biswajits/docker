# docker
First Spring Boor Docker demo

Add Dockerfile in project's root directory with all config and image information..

Then to build the docker image folloe below steps

1. First navigate to the project root directory in Command prompt
2. Then run below command
           docker container build -f Dockerfile -t docker-spring-boot . (where . is Dockerfile location, in our case its in root dir)
3. Now our image is downloaded and ready. To run it 
           docker container run -p 8085:8085 docker-spring-boot
           
And don't forget to add below <finalname> tag in maven project to generate specifided name jar file

                 		</plugin>
		              </plugins>
		              <finalName>spring-boot-docker</finalName>
	              </build>
                
Below are the contents of our Dockerfile....
                  FROM openjdk:8
                  ADD target/spring-boot-docker.jar spring-boot-docker.jar
                  EXPOSE 8085
                  ENTRYPOINT ["java","-jar","spring-boot-docker.jar"]
