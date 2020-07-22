---
description: Gateway statistics aggregation, location and channel-plan (re)configuration.
---

# Gateway management

ChirpStack Network Server has support for managing gateways. Gateways can be created by
using the [API](../integrate/api.md).

## Gateway location

The (last known) location of the gateway will be stored in the database. When
the gateway is equipped with a GPS, its location will be automatically updated
after every stats update in case it has changed. Else, it can be manually set
when creating or updating the gateway.

## Gateway re-configuration

If a [Gateway Profile](gateway-profile.md) is assigned
to the gateway, ChirpStack Network Server will push configuration updates to the gateway
to keep its channel-plan in sync with the configuration of the network.
This is triggered when ChirpStack Network Server receives gateway statistics (which also
contains the current configuration version of the gateway). If there is new
version of the configuration available, then it will be pushed by ChirpStack Network Server
to the gateway.

Note that this feature must also be configured in the
[ChirpStack Gateway Bridge Configuration](../../gateway-bridge/install/config.md).
