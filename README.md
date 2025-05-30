[![Maven build](https://github.com/Netcracker/qubership-maas-client-quarkus/actions/workflows/maven-build.yaml/badge.svg)](https://github.com/Netcracker/qubership-maas-client-quarkus/actions/workflows/maven-build.yaml)
[![Coverage](https://sonarcloud.io/api/project_badges/measure?metric=coverage&project=Netcracker_qubership-maas-client-quarkus)](https://sonarcloud.io/summary/overall?id=Netcracker_qubership-maas-client-quarkus)
[![duplicated_lines_density](https://sonarcloud.io/api/project_badges/measure?metric=duplicated_lines_density&project=Netcracker_qubership-maas-client-quarkus)](https://sonarcloud.io/summary/overall?id=Netcracker_qubership-maas-client-quarkus)
[![vulnerabilities](https://sonarcloud.io/api/project_badges/measure?metric=vulnerabilities&project=Netcracker_qubership-maas-client-quarkus)](https://sonarcloud.io/summary/overall?id=Netcracker_qubership-maas-client-quarkus)
[![bugs](https://sonarcloud.io/api/project_badges/measure?metric=bugs&project=Netcracker_qubership-maas-client-quarkus)](https://sonarcloud.io/summary/overall?id=Netcracker_qubership-maas-client-quarkus)
[![code_smells](https://sonarcloud.io/api/project_badges/measure?metric=code_smells&project=Netcracker_qubership-maas-client-quarkus)](https://sonarcloud.io/summary/overall?id=Netcracker_qubership-maas-client-quarkus)

# MaaS Client

MaaS provide quarkus extension based on plain java core maas library: maas-client-java.

To include extension to your project add:
```xml
<project>
    <dependencyManagement>
        <dependency>
            <groupId>org.qubership.cloud.quarkus</groupId>
            <artifactId>maas-client-quarkus-bom</artifactId>
            <version>x.x.x</version>
            <type>pom</type>
            <scope>import</scope>
        </dependency>
    </dependencyManagement>

    <dependencies>
        <dependency>
            <groupId>org.qubership.cloud.quarkus</groupId>
            <artifactId>maas-client-quarkus-kafka</artifactId>
        </dependency>
        <dependency>
            <groupId>org.qubership.cloud.quarkus</groupId>
            <artifactId>maas-client-quarkus-rabbit</artifactId>
        </dependency>
    </dependencies>
</project>
```

It proivides default MaaSClient bean instance to inject.
There is also a DeploymentVersionTracker bean for quarkus:
```java
@Inject
MaaSAPIClient maasClient;

@Inject
DeploymentVersionTracker tracker;
```


For Rabbit there is a default maas client rabbit bean and also DynamicQueueBindingsManager if you want to use dynamic bindings:

```java
@Inject
RabbitMaaSClient rabbitClient;

@Inject
DynamicQueueBindingsManager manager;
```



For Kafka:

```java
@Inject
KafkaMaaSClient kafkaClient;
```




