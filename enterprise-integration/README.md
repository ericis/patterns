# Enterprise Integration Patterns

_This summary is intended purely as a reference to [the book](https://amzn.to/2vTmfS7)
and complies with the "copy up to 10% of the book" copyright law._

**Citation:** [Hohpe, G., & Woolf, B. (2012). Enterprise Integration Patterns. Addison-Wesley.](https://amzn.to/2vTmfS7)

This book is a foundational reference for Enterprise, application
integration design patterns. The book inspired a lot of the
implementations found in Service-Oriented Architecture and traditional,
enterprise Service Bus solutions as well as programming integration
frameworks like [Java Spring Integration](https://spring.io/projects/spring-integration).

![A categorized list of enterprise integration patterns](./images/eip.jpg)

## Read the Book

- [Amazon](https://amzn.to/2vTmfS7)

## Six Types of Integration

- Information portals

    ![Information portals reference icon](./images/information-portal.jpg)

- Data replication

    ![Data replication reference icon](./images/data-replication.jpg)

- Shared business functions

   ![Shared business functions reference icon](./images/shared-business-function.jpg)

- Service-oriented architectures

    ![Service-oriented architectures reference icon](./images/soa.jpg)

- Distributed business processes

    ![Distributed business processes reference icon](./images/distributed-business-process.jpg)

- Business-to-business integration

    ![Business-to-business integration reference icon](./images/b2b-integration.jpg)

## Integration Styles

### Application Integration Criteria

- Application coupling
- Intrusiveness
- Technology selection
- Data format
- Data timeliness
- Data or functionality
- Remote Communication
- Reliability

### Application Integration Options

- File Transfer

    ![File transfer reference icon](./images/file-transfer.jpg)

- Shared Database

    ![Shared database reference icon](./images/shared-database.jpg)

- Remote Procedure Invocation

    ![Remote procedure invocation reference icon](./images/rpc.jpg)

- Messaging

    ![Messaging reference icon](./images/messaging.jpg)

## Messaging Systems

- Channels

    ![Message channel reference icon](./images/message-channel.jpg)

- Messages

    ![Message channel reference icon](./images/message.jpg)

- Pipes and Filters

    ![Pipes and filters reference icon](./images/pipes-filters.jpg)

- Routing

    ![Message router reference icon](./images/message-router.jpg)

- Transformation

    ![Message router reference icon](./images/message-translator.jpg)

- Endpoints

    ![Message router reference icon](./images/message-endpoint.jpg)

## Messaging Channels

### Message Channel Decisions

- One-to-one or one-to-many
- What type of data
- Invalid and dead messages
- Crash proof
- Non-messaging clients
- Communications backbone

- Point-to-point channel

    ![Point-to-point channel reference icon](./images/p2p-channel.jpg)

- Publish-Subscribe channel

    ![Publish-subscribe channel reference icon](./images/pub-sub-channel.jpg)

- Datatype channel

    ![Datatype channel reference icon](./images/datatype-channel.jpg)

- Invalid message channel

    ![Invalid message channel reference icon](./images/invalid-message-channel.jpg)

- Dead letter channel

    ![Dead letter channel reference icon](./images/dead-letter-channel.jpg)

- Guaranteed delivery

    ![Guaranteed delivery reference icon](./images/guaranteed-delivery.jpg)

- Channel adapter

    ![Channel adapter reference icon](./images/channel-adapter.jpg)

  - User interface adapter
  - Business logic adapter
  - Database adapter

- Messaging bridge

    ![Messaging bridge reference icon](./images/messaging-bridge.jpg)

- Message bus

    ![Message bus reference icon](./images/message-bus.jpg)

## Messaging Construction

- Command message

    ![Command message reference icon](./images/command-message.jpg)

- Document message

    ![Document message reference icon](./images/document-message.jpg)

- Document message

    ![Document message reference icon](./images/document-message.jpg)

- Event message

    ![Event message reference icon](./images/event-message.jpg)

  - Push model: a combined document/event message
  - Pull model: three messages
    1. Update
    2. State request
    3. State reply

- Request-Reply

    ![Request-Reply reference icon](./images/request-reply.jpg)

  1. Requestor
  2. Replier has two approaches to reply

      - Synchronous block
      - Asynchronous callback

        ... with three possible values:

      1. Void
      2. Result
      3. Exception

- Return address

    ![Return address reference icon](./images/return-address.jpg)

- Correlation identifier

    ![Correlation identifier reference icon](./images/correlation-id.jpg)

    Six parts:

    1. Requestor
    2. Replier
    3. Request
    4. Reply
    5. Request ID
    6. Correlation ID

- Message sequence

    ![Message sequence reference icon](./images/message-sequence.jpg)

    Three identification fields:

    1. Sequence identifier
    2. Position identifier
    3. Size or End indicator

- Message expiration

    ![Message expiration reference icon](./images/message-expiration.jpg)

- Format indicator

    1. Version number
    2. Foreign key
    3. Format document

## Message Routing

- Simple routers
- Composed routers
- Architectural patterns

![Message routing decision chart](./images/message-routing-decision-chart.jpg)

- Content-based router

    ![Content-based router reference icon](./images/content-based-router.jpg)

- Message filter

    ![Message filter reference icon](./images/message-filter.jpg)

- Dynamic router

    ![Dynamic router reference icon](./images/dynamic-router.jpg)

- Recipient list

    ![Recipient list reference icon](./images/recipient-list.jpg)

- Splitter

    ![Splitter reference icon](./images/splitter.jpg)

- Aggregator

    ![Aggregator reference icon](./images/aggregator.jpg)

- Resequencer

    ![Resequencer reference icon](./images/resequencer.jpg)

- Composed message processor

    ![Composed message processor reference icon](./images/composed-message-processor.jpg)

- Routing slip

    ![Routing slip reference icon](./images/routing-slip.jpg)

- Process manager

    ![Process manager reference icon](./images/process-manager.jpg)

- Message broker

    ![Message broker reference icon](./images/message-broker.jpg)

## Message Transformation

- Envelope wrapper

    ![Envelope wrapper reference icon](./images/envelope-wrapper.jpg)

- Content enricher

    ![Content enricher reference icon](./images/content-enricher.jpg)

- Content filter

    ![Content filter reference icon](./images/content-filter.jpg)

- Claim check

    ![Claim check reference icon](./images/claim-check.jpg)

- Normalizer

    ![Normalizer reference icon](./images/normalizer.jpg)

### Canonical data model

> The Canonical Data Model provides an additional level of indirection
between applications' individual data formats. If a new application
is added to the integration solution, only transformation between the
Canonical Data Model has to be created, regardless of the number of
applications that already participate.
>
> The use of a Canonical Data Model may seem overly complicated if only
a small number of applications participate in the integration solution.
However, the solution quickly pays off as the number of applications increases.

#### Transformation Options

1. Change the applications' internal data format
2. Implement a Messaging Mapper inside the application
3. Use an external Message Translator

#### Double Translation

> The use of a Canonical Data Model does introduce a certain amount of
overhead into the message flow. Each message now has to undergo two
translation steps instead of one: one translation from the source
application's format into the common format and one from the common
format into the target application's format.

## Message Endpoints

### Send and Receive Patterns

- Encapsulate the messaging code
- Data translation
- Externally controlled transactions

### Message Consumer Patterns

- Synchronous or asynchronous consumer
- Message assignment versus message grab
- Accept all messages or filter
- Subscribe while disconnected
- Idempotency
- Synchronous or asynchronous service

### Catalog

- Messaging gateway

    ![Messaging gateway reference icon](./images/messaging-gateway.jpg)

  - Messaging mapper

- Transactional client

    ![Transactional client reference icon](./images/transactional-client.jpg)

- Polling consumer

    ![Polling consumer reference icon](./images/polling-consumer.jpg)

- Event-driven consumer

    ![Event-driven consumer reference icon](./images/event-driven-consumer.jpg)

- Competing consumers

    ![Competing consumers reference icon](./images/competing-consumers.jpg)

- Message dispatcher

    ![Message dispatcher reference icon](./images/message-dispatcher.jpg)

    Two parts:

    1. Dispatcher
    2. Performer

- Selective consumer

    ![Selective consumer reference icon](./images/selective-consumer.jpg)

- Durable subscriber

    ![Durable subscriber reference icon](./images/durable-subscriber.jpg)

  - Idempotent Receiver

- Service activator

    ![Service activator reference icon](./images/service-activator.jpg)

## System Management

### Categories

- Monitoring and Controlling
- Observing and Analyzing Message Traffic
- Testing and Debugging

### Catalog

- Control bus

    ![Control bus reference icon](./images/control-bus.jpg)

- Detour

    ![Detour reference icon](./images/detour.jpg)

- Wire tap

    ![Wire tap reference icon](./images/wire-tap.jpg)

- Message history

- Message store

    ![Message store reference icon](./images/message-store.jpg)

- Smart proxy

    ![Smart proxy reference icon](./images/smart-proxy.jpg)

- Test message

    ![Test message reference icon](./images/test-message.jpg)

- Channel purger

    ![Channel purger reference icon](./images/channel-purger.jpg)
