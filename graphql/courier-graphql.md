# Courier GraphQL API

## Overview

Courier provides a native GraphQL API in addition to its REST API. The GraphQL endpoint is available at `https://api.courier.com/graphql` and supports querying and mutating notifications, messages, recipients, lists, brands, templates, automations, preferences, and more.

## Endpoint

```
https://api.courier.com/graphql
```

## Authentication

Authenticate using Bearer token in the Authorization header:

```
Authorization: Bearer <COURIER_AUTH_TOKEN>
```

Tokens can be obtained from the Courier dashboard under Settings > API Keys.

## Schema File

The GraphQL schema for this API is defined in `courier-schema.graphql`.

## Capabilities

### Queries

- Retrieve message details and delivery status logs
- Fetch recipient profiles and preference settings
- List notification templates and brand configurations
- Query subscription lists and audience segments
- Inspect automation workflows and step runs
- Retrieve workspace and API key metadata
- Access event and webhook configurations

### Mutations

- Send notifications to individual recipients or lists
- Create and update recipient profiles
- Manage subscription list memberships
- Create, update, or archive notification templates
- Configure brand themes and styling
- Set recipient notification preferences
- Trigger automation workflows
- Register and manage webhooks

## Example Query

```graphql
query GetMessage($messageId: String!) {
  message(messageId: $messageId) {
    messageId
    status
    enqueued
    sent
    delivered
    clicked
    opened
    provider {
      channel
      provider
      status
    }
    log {
      timestamp
      type
      body
    }
  }
}
```

## Example Mutation

```graphql
mutation SendNotification($input: SendNotificationInput!) {
  sendNotification(input: $input) {
    requestId
    messageId
  }
}
```

## References

- REST Reference: https://www.courier.com/docs/reference/
- GraphQL Endpoint: https://api.courier.com/graphql
- GitHub Organization: https://github.com/trycourier
- Developer Portal: https://www.courier.com/docs/
