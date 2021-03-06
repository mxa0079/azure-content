<properties
	 pageTitle="Use the Azure portal to manage IoT Hub | Microsoft Azure"
	 description="An overview of how to create and manage Azure IoT hubs through the Azure portal"
	 services="iot-hub"
	 documentationCenter=""
	 authors="nasing"
	 manager="timlt"
	 editor=""/>

<tags
	 ms.service="iot-hub"
	 ms.devlang="na"
	 ms.topic="article"
	 ms.tgt_pltfrm="na"
	 ms.workload="na"
	 ms.date="10/19/2015"
	 ms.author="nasing"/>

# Manage IoT hubs through the Azure portal

## Introduction

This article describes how to get started with Azure IoT Hub through the Azure portal, how to find IoT hubs, and how to create and manage IoT hubs.

## Where to find IoT hubs

There are a number of places in which you can find IoT hubs.

1. **+ New** : **Azure IoT Hub** is an IoT service, and can be found in the category **Internet of Things**, under **+ New**, similar to other services.

2. IoT hubs can also be accessed through the Marketplace as the hero service under **Internet of Things**.

## Create an IoT hub

You can create an IoT hub using the following methods.

1. Creating an IoT hub through the **+ New** option leads to the blade shown in the next screen shot. The steps for creating the IoT hub through this method as well as through the marketplace are identical.

2. Creating an IoT hub through the Marketplace: Clicking **Create** opens a blade that is identical to the previous blade for the **+New** experience. There are several steps involved in creating an IoT hub that are listed in the next sections.

### Choose the name of the IoT hub

In order to create an IoT hub, you must name the hub. Note that this name must be unique across the hubs. No duplication of hubs is allowed on the back end, so it is recommended that this hub be named as uniquely as possible.

### Choose the pricing tier

You can choose from 3 tiers: **Free**, **Standard 1** and **Standard 2**. The free tier allows only 10 devices to be connected to the IoT hub.

**S1 (Low Frequency)**: IoT Hubs S1 (Low Frequency) edition is designed for IoT solutions that have a large number of devices generating relatively small amounts of data per device. Each unit of the S1 (Low Frequency) edition allows connectivity of up to 500 devices or up to 50,000 messages per day across all connected devices.

**S2 (High Frequency)**: IoT Hub S2 (High Frequency) edition is designed for IoT solutions in which devices generate large amounts of data. Each unit of the S2 (High Frequency) edition allows connectivity of up to 500 devices or up to 1.5 million messages per day between all connected devices.  

![][4]

> [AZURE.NOTE] IoT Hub only allows one free hub per subscription.

### IoT hub units

An IoT hub unit includes 500 devices, so choosing the number of IoT units means that the total number of devices supported for this hub is the number of units multiplied by 500. For example, if you want the IoT hub to support 1000 devices, you choose 2 units.

### Device to cloud partitions and resource group

You can change the number of partitions for an IoT hub. Default partitions are set to 4; however, you can choose a different number of partitions from a drop-down list.

For resource groups, you do not need to explicitly create an empty resource group. When creating a new resource, you can choose to either create a new resource group or use an existing resource group.

![][5]

### Choose subscriptions

Azure IoT Hub automatically shows the list of subscriptions to which the user account is linked. You can choose one of the options here to associate the IoT hub with that subscription.

### Choose the location

The location option provides a list of the regions in which IoT Hub is offered. IoT Hub is available to deploy in the following locations: US East, US West, Europe North, Europe West, East Asia, and South-East Asia.

### Create the IoT hub

When all previous steps are complete, the IoT hub is ready to be created. Click **Create** to start the back-end process of creating this IoT hub with the specific options, and to deploy it to the location specified.

Please note that it can take a few minutes for the IoT hub to be created as it takes time for the back-end deployment to occur in the appropriate location servers.

## Change the settings of the IoT hub

You can change the settings of an existing IoT hub after it is created. Click the IoT hub name to open the settings page.

![][8]

**Shared Access Policies**: These are the policies that define the permissions for devices and services to connect to IoT Hub. You can access these policies by clicking on **Shared Access Policies** under **Settings**. In this blade you can either modify existing policies or add a new policy.

### Create a new policy

- Click **Add** to open a blade in which you can enter the new policy name and the permissions that you want to associate with this policy, as shown in the following figure.

	There are several permissions that can be associated with these shared policies. The first two policies, **Registry Read** and **Registry Write**, grant read and write access rights to the device identity store or the identity registry. Please note that choosing the write option automatically chooses the read option as well.

 	The service connect policy grants permission to the consumer group for services connecting to the IoT hub, while the device connect grants permissions for device side of the IoT hub.

- Click **Create** to add this newly created policy to the existing list.

![][10]

## Messaging

Click the **Messaging** policies to display a list of messaging properties for the IoT hub that is being modified. There are two main types of properties that you can modify or copy: **Cloud to Device** and **Device to Cloud**.

- **Cloud to Device** settings: This has 2 sub-settings: **Cloud to Device TTL** (time-to-live) and **Retention time** for the messages. When the IoT hub is first created, both these settings are created with a default value of 1 hour. However, you can customize these using the sliders, or just type the values.

- **Device to Cloud** settings: This has several sub-settings, some of which are named/assigned when the IoT hub is created and can only be copied to other sub-settings that are customizable. These settings are listed in the next section.

**Partitions**: This value is set when the IoT hub is created and can be changed through this setting.

**Event Hub compatible name and endpoint**: When the IoT hub is created, an Event Hub is created internally which the user may need access to under certain circumstances. This Event Hub name and endpoint cannot be customized but is available for use via the **Copy** button.

**Retention Time**: Set to 1 day by default but can be customized to other values using the drop down list. Please note that this value is in days for Device to Cloud and not in hours, as is the similar setting for Cloud to Device.

**Consumer Groups**: Consumer Groups are a setting similar to other messaging systems that can be used to pull data in specific ways to connect other applications or services to IoT Hub. Every IoT hub is created with a default consumer group. However, you can add or delete consumer groups to your IoT hubs.

> [AZURE.NOTE] The default consumer group cannot be edited or deleted.

![][11]

## Pricing and scale

The pricing of an existing IoT hub can be changed through the **Pricing** settings, with the following exceptions:

- In the current implementation, an IoT hub with a free SKU cannot change tiers to one of the paid SKUs, or vice versa.
- There can only be one free tier IoT hub in the subscription.

![][12]

Moving from a high tier (S2) to low tier (S1) is allowed only when the number of messages sent for that day are not in conflict. For example, if the number of messages per day exceeds 50,000, then the tier for the IoT hub cannot be changed from S2 to S1.

## Delete the IoT hub

You can browse to the IoT hub you want to delete by clicking **Browse**, and then choosing the appropriate hub to delete. Click the **Delete** button below the hub name to delete the hub.

## Next steps

Follow these links to learn more about Azure IoT Hub:

- [Get started with IoT Hub (Tutorial)][lnk-get-started]
- [What is Azure IoT Hub?][]


  [4]: ./media/iot-hub-manage-through-portal/create-iothub.png
  [5]: ./media/iot-hub-manage-through-portal/location1.png
  [8]: ./media/iot-hub-manage-through-portal/portal-settings.png
  [10]: ./media/iot-hub-manage-through-portal/shared-access-policies.png
  [11]: ./media/iot-hub-manage-through-portal/messaging-settings.png
  [12]: ./media/iot-hub-manage-through-portal/pricing-error.png

[lnk-get-started]: iot-hub-csharp-csharp-getstarted.md
[What is Azure IoT Hub?]: iot-hub-what-is-iot-hub.md
