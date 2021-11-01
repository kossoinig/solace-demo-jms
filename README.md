[![Build Status](https://travis-ci.org/SolaceSamples/solace-samples-jms.svg?branch=master)](https://travis-ci.org/SolaceSamples/solace-samples-jms)

# Demo Based on Solace Getting Started Tutorial
## Solace JMS API and Messaging System Required

This demo requires a running Solace messaging system to connect with.
There are two ways you can get started:

- Follow [these instructions](https://cloud.solace.com/learn/group_getting_started/ggs_signup.html) to quickly spin up a cloud-based Solace messaging service for your applications.
- Follow [these instructions](https://docs.solace.com/Solace-SW-Broker-Set-Up/Setting-Up-SW-Brokers.htm) to start the Solace VMR in leading Clouds, Container Platforms or Hypervisors. The tutorials outline where to download and how to install the Solace VMR.

The project includes the latest version of the Solace JMS API implementation at time of creation.
Note that there are additional files in the project that were inherited from the samples project which are not used for this demo, and can be ignored.

## Build the demo

Just clone and build. For example:

  1. clone this GitHub repository
  2. `./gradlew assemble`

## Run the Demo

This demo was created to simulate a specific problem scenario and includes the  scripts below.

Start these scripts in the order listed:

    ./build/staged/bin/analyticsDataPipelineSubscriber <host:port> <message-vpn> <client-username> [password]
    ./build/staged/bin/crewRelaySvcSubscriber <host:port> <message-vpn> <client-username> [password]
    ./build/staged/bin/crewPayAnalyticsProcessor <host:port> <message-vpn> <client-username> [password]
    ./build/staged/bin/crewSchedulingAppPublisher <host:port> <message-vpn> <client-username> [password]

Tip - You can find above launch parameters in Connect tab of the Cluster Manager page (expand first section)
   
The output will show no messages until the last one is launched.
Messages produced there are consumed by the crewRelaySvcSubscriber and crewPayAnalyticsProcessor applications.
The processor transforms and republishes on the topic consumed by the analyticsDataPipelineSubscriber.

Stop the processor to show no messages flowing to the data pipeline on the second topic.
Stop the publisher to show no messages flowing to the processor or crewRelaySvcSubscriber.

See related presentation PPT for details of the problem setup for this demo.

## Authors

This demo was prepared by Karl Ossoinig, and is based on the work done for the solace-samples-jms project.
See the list of original [contributors](https://github.com/SolaceSamples/solace-samples-jms/contributors) who participated in that project.

## License

This project is licensed under the Apache License, Version 2.0. - See the [LICENSE](LICENSE) file for details.

## Resources

For more information try these resources:

- The Solace Developer Portal website at: https://solace.dev
- Ask the https://solace.community
- Solace API Tutorials @ https://tutorials.solace.dev
