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
