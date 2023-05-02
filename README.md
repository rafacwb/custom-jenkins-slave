# custom-jenkins-slave

```shell
oc project cicd-tools

oc process -f build.yaml --param-file=maven/build.params | oc apply -f - 

oc start-build supp-jenkins-slave-maven-build -F -w

oc apply -f slave-configmap.yaml
```



Nao precisa abaixo:

```
oc label node node1.ctba-bcc0.internal environment=cicd

oc annotate ns cicd-tools openshift.io/node-selector='environment=cicd'

docker run  --user root  --rm -it --entrypoint "/bin/bash" registry.redhat.io/openshift3/jenkins-agent-maven-35-rhel7:v3.11
```



```

oc import-image openshift3/jenkins-agent-maven-35-rhel7:v3.11 --from=registry.redhat.io/openshift3/jenkins-agent-maven-35-rhel7:v3.11 --confirm
```

Referências

- https://github.com/containers/skopeo/blob/master/install.md
- https://access.redhat.com/solutions/3671891 - Build fails with error "This system is not receiving updates" on Openshift Container Platform 3
- https://github.com/jenkinsci/kubernetes-plugin
- Sharing Persistent Volume between Jenkins Master and Slaves - https://access.redhat.com/solutions/3461461
