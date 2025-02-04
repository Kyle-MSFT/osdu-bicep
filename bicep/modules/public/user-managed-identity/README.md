# User Managed Identity

This module deploys a user managed identity

## Description

This module creates a user managed identity with an optional lock.

## Parameters

| Name           | Type     | Required | Description                         |
| :------------- | :------: | :------: | :---------------------------------- |
| `resourceName` | `string` | Yes      | Used to name all resources          |
| `location`     | `string` | No       | The resource location.              |
| `tags`         | `object` | No       | Tags.                               |
| `lock`         | `string` | No       | Optional. Specify the type of lock. |

## Outputs

| Name        | Type   | Description                                |
| :---------- | :----: | :----------------------------------------- |
| id          | string | The resource ID of the managed identity.   |
| principalId | string | The principal id for the managed identity. |

## Examples

```bicep
module example 'br:osdubicep.azurecr.io/bicep/modules/public/user-managed-identity:1.0.1' = {
  name: 'user_identity'
  params: {
    resourceName: 'id-${uniqueString(resourceGroup().id)}'
    location: 'southcentralus'
  }
}
```