# tasklist-declarative-service
Karaf Tutorial 10 - Declarative services and JPA

# Remarks
Because we use @Component annotation with following properties: 
`property = { "service.exported.interfaces=*",
		"service.exported.configs=org.apache.cxf.rs", "org.apache.cxf.rs.address=/tasklistRest" }`
so although we create CXF Rest service, we [strong]should not install CXF feature[/strong], instead add these feature repos:
* `<repository>mvn:org.apache.aries.rsa/rsa-features/1.8.0/xml/features</repository>`
* `<repository>mvn:org.apache.cxf.dosgi/cxf-dosgi/1.8.0/xml/features</repository>`
and install these features:
* `aries-rsa-discovery-zookeeper`
* `aries-rsa-discovery-zookeeper-server`
* `cxf-dosgi-provider-cxf`

