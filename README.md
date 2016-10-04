# Karaf Camel Log QuickStart

This quickstart shows a simple Apache Camel application that logs a message taken from a Kubernetes ConfigMap to the server log every 5th second.
It also shows how Karaf assembly files can be overridden using resources from `src/main/resources/assembly/`. The included sample log file `etc/org.ops4j.pax.logging.cfg` sets the log level to DEBUG. 

This quickstart will automatically create a ConfigMap named karaf-camel-log and will set up service account view policy.
By default the view policy will be applied to a service account named `default` in namespace `default`, you can customize them via quickstart.namespace and quickstart.serviceaccount properties.

### Building

The example can be built with

    mvn clean install -Ddocker.skip


### Running the example in fabric8

It is assumed a running Kubernetes platform is already running. If not you can find details how to [get started](http://fabric8.io/guide/getStarted/index.html).

The example can be built and deployed using:

    mvn install fabric8:deploy

When the example runs in fabric8, you can use the OpenShift client tool to inspect the status

To list all the running pods:

    oc get pods

Then find the name of the pod that runs this quickstart, and output the logs from the running pods with:

    oc logs <name of pod>

You can also use the fabric8 [web console](http://fabric8.io/guide/console.html) to manage the
running pods, and view logs and much more.


### More details

You can find more details about running this [quickstart](http://fabric8.io/guide/quickstarts/running.html) on the website. This also includes instructions how to change the Docker image user and registry.

