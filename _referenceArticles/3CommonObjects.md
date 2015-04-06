---
title: Common Objects
anchor: commonobjects
---

# Common Objects

In this section we describe some of the common objects/fields of objects that can be found throughout all of the API and are explained in detail here and in the subsequent reference documentation of each API method available. 

## External References

There are a number of what we call 'external references' throughout the library. These are fields that are usually prefixed with 'ext' and they refer to the Client's system. 

### ExternalId

All of the artifacts that are present here, usually require a unique id, that should exist on the client side, to be reported.

If such a unique ID does not exist on the client's side, it should be created, persisted and enforced its uniqueness per artifact by the client.

### External dates

Some of the dates, mostly referring to creation timestamps, are requested by the library. If the creation or other such dates are not available, the time reliability of the resulting graphs cannot be assured.


## Classifiers

Classifiers, as the name implies, are a way to classify each artifact, that can later be used to segment the data by its values. e.g. if you want to know how many clients came from a specific campaign, then you should add to each subscription and client artifact a campaign classifier (a key value pair) that will allow us later to distinguish them amongst the other clients/subscription.
