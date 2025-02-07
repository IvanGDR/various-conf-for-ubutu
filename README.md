# various-conf-for-ubutu


### JAVA_HOME When using JAVA ALTERNATIVES


Then set the following in your .bashrc or .zshrc:
```
#!/bin/bash
if [ -z "${JAVA_HOME}" ]
then
    JAVA_HOME=$(readlink -nf $(which java) | xargs dirname | xargs dirname)
    if [ ! -e "$JAVA_HOME" ]
    then
        JAVA_HOME=""
    fi
    export JAVA_HOME=$JAVA_HOME
fi
```



Another that worked for me:
```
export JAVA_HOME=$(dirname $(dirname `readlink -f /etc/alternatives/java`))

```

After saving any of the solutions above then source `.bashrc` or `.zhhrc`


### Installing Maven
`Note: JAVA_HOME needs to be set up`

Download version from here:
https://maven.apache.org/download.cgi

Go to `cd /opt`
```
opt $ wget https://dlcdn.apache.org/maven/maven-3/3.9.9/binaries/apache-maven-3.9.9-bin.tar.gz
opt $ tar -xvf apache-maven-3.9.9-bin.tar.gz
opt $ chown -R <user>:<group> apache-maven-3.9.9
```
Finally
```
mvn -version
Apache Maven 3.9.9 (8e8579a9e76f7d015ee5ec7bfcdc97d260186937)
Maven home: /opt/apache-maven-3.9.9
Java version: 21.0.6, vendor: Ubuntu, runtime: /usr/lib/jvm/java-21-openjdk-amd64
Default locale: en_US, platform encoding: UTF-8
OS name: "linux", version: "6.8.0-52-generic", arch: "amd64", family: "unix"
```



#### For VSCode
Maven Executable path is:
`/opt/apache-maven-3.9.9/bin/mvn`


