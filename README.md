# deploy-iot-hub-advance-configuration
IoT hub can be deployed from the Azure Portal, however, all the settings for IoT hub are not exposed during the process.  Here we have defined a deployment template that exposes all the different configuration options.  Below are the explanations of these settings.



| Standard Configuration | Explanation                                                  |
| ---------------------- | ------------------------------------------------------------ |
| Subscription           | The Azure subscription in which to deploy to the IoT Hub to. |
| Resource Group         | The Azure Resource Group in which to deploy the IoT Hub to.  |
| Region                 | The Azure region in which to deploy the IoT Hub to.          |
| IoT Hub Name           | The Name of the IoT Hub, must be unique                      |
| Sku Size               | The size of the IoT Hub; F1, S1, S2, S3                      |
| Capacity Units         | The number of SKU sizes to deploy, example 1 unit of S1 SKU  |



| Advanced Configuration                          | Explanation                                                  |
| ----------------------------------------------- | ------------------------------------------------------------ |
| D2C Message Retention In Days Period            | Retention time in days for device to cloud messages.         |
| Partition Count                                 | Number of partitions for IoT Hub.  The default is 4, scalable to 128.  For more information see this [article](https://docs.microsoft.com/en-us/azure/event-hubs/event-hubs-scalability#partitions) |
| C2D Message TTL As ISO 8601                     | Default TTL in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format for cloud to device messages.  Values range from PT1M to PT2D. |
| C2D Messages Max Delivery Count                 | Maximum delivery count for cloud to device messages per device queues. |
| C2D Feedback Messages TTL As ISO 8601           | TTL in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) Format for service bound feedback messages.  Value can range PT1M to PT1D |
| C2D Feedback Messages Max Delivery Count        | Maximum delivery count for feedback queue.                   |
| C2D Feedback Messages Lock Duration As ISO 8601 | Lock duration in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format for service bound feedback messages value can range from PT5S to PT300S |
| Consumer Group Name                             | Name of device to cloud consumer group to provision on the IoT Hub instance. |



------



ARM template to deploy the IoT Hub and its advanced configuration

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FMSKeith%2Fdeploy-iot-hub-advance-configuration%2Fmaster%2Fdeploy.json" target="_blank">
    <img src="https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.png" />
</a>

The ARM template visualized for exploration

<a href="http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FMSKeith%2Fdeploy-iot-hub-advance-configuration%2Fmaster%2Fdeploy.json" target="_blank">
    <img src="https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/visualizebutton.png" /></a>