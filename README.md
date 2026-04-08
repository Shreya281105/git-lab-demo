exp 11:
open eclipse 
click file-> new -> java project
enter project name-> JUNit 
right click src 
click new->class
class name-> calculator
paste the code
right click on project 
click build path-> add libraries
select junit->next->choose junit5
finish
right click on src 
click new ->junit test case
name-> calculatortest
finish
paste code
right click run as -> junit  test


exp-12

crate folder
open cmd
mvn --version
mvn archetype:generate
2333: 2333
9
groupID:bnmit.org
artifact:sample-app
1.0-SNAPSHOT: SAME
bnmit.org: same
y

open vs code , open folder 
edit app.java, apptest.java
paste the code

in cmd sample-app
mvn clean test


13.
do exp-12
go to github 
create new repo ->junit
upload java maven project
pom.xm, src

go to jenkins
new item 
slect maven 
dicard- 55
git-. repo , cred

poll scm -*****
post steps
run only if buil succeds

pre steps
build 
pom.xml

goals- package

ok build now

configure 
archive the artifacts

'target/*.jar'


14.

in folder cmd
mvn archetype:generate

same exp 12

cd sample-app
mvn  clean test
go to pom->vs code open 
Add the plugin inside the <build> section.
<build>
<plugins>

<plugin>
<groupId>org.jacoco</groupId>
<artifactId>jacoco-maven-plugin</artifactId>
<version>0.8.11</version>

<executions>

<execution>
<goals>
<goal>prepare-agent</goal>
</goals>
</execution>

<execution>
<id>report</id>
<phase>test</phase>
<goals>
<goal>report</goal>
</goals>
</execution>

</executions>

</plugin>

</plugins>
</build>

mvn clean test
in folder go to target->site->jacoco->index
target/site/jacoco/index.html


15.

docker --version
docker ps
docker ps -a
docker images
docker run hello-world
docker pull nginx
docker run -d -p 8080:80 nginx
docker ps
docker stop container_id
docker rm container_id
docker ps


16.
Create a folder:

docker-python-demo

Inside the folder create two files:

Dockerfile
app.py

Create app.py


from flask import Flask

app = Flask(__name__)

@app.route('/')
def home():
    return "Hello from Docker Container"

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)




Create a file named Dockerfile.



FROM python:3.9

WORKDIR /app

COPY . /app

RUN pip install flask

EXPOSE 5000

CMD ["python", "app.py"]



Open terminal inside the project folder and run:

docker build -t python-app .

docker images

docker run -p 5000:5000 python-app



17.

docker run -d nginx
docker images
docker run -d -p 8080:80 nginx
docker volume create myvolume
docker volume create dvolume
docker volume ls
docker run -it -v myvolume:/data ubuntu bash
cd /data
echo "Docker Volume Persistence Test" > test.txt
exit
docker run -it -v myvolume:/data ubuntu bash
cat /data/test.txt


docker volume create myvolume
docker run -d -p 8086:80 -v myvolume:/usr/share/nginx/html nginx
docker run -it -v myvolume:/data ubuntu bash
echo "<h1>Persistent Web Page</h1>" > /data/index.html
exit
docker run -d -p 8083:80 -v myvolume:/usr/share/nginx/html nginx


18.








19.

jenkins
new item
freestyle
dicard-> 55
git-> dockerfile, grade.java

FROM openjdk:11
WORKDIR /app
COPY . .
RUN javac Grade.java
CMD ["java","Grade"]


     
poll scm
add build steps
docker build -t java-app .
docker run -d -t java-app





