---
id: Interaction
sidebar_label: Interaction
title: Interaction
hide_title: true
---
# `Interaction`

An `Interaction` is a significant direct exchange of ideas or information between a number of participants, e.g. a Sell Side party and one or more Buy Side parties. An `Interaction` might be a call, a meeting (physical or virtual), an IM or the preparation of some specialist data, such as financial data for a given company or sector.

Notes:

- `interactionType` SHOULD be one of 'Instant Message', 'Email', 'Call', or 'Meeting' although other values are permitted.
- `origin` is used to represent the application or service that the interaction was created from to aid in tracing the source of an interaction.

## Type

`fdc3.interaction`

## Schema

https://fdc3.finos.org/schemas/next/interaction.schema.json

## Details

| Property    | Type    | Required | Example Value       |
|-------------|---------|----------|---------------------|
| `type`      | string  | Yes      | `fdc3.interaction` |
| `participants`      | fdc3.contactList  | Yes       | See below      |
| `timeRange` | fdc3.timeRange  | Yes       | See below            |
| `interactionType` | string  | Yes       | `Instant Message`            |
| `description`    | string  | Yes       | `Blah, blah, blah`         |
| `initiator`    | fdc3.contact  | No       | See below         |
| `origin`    |  string  | No       | `Outlook`         |

## Example

```js
const interaction = {
    type: 'fdc3.interaction',
    participants: {
        type: 'fdc3.contactList',
        contacts: [
            {
                type: 'fdc3.contact',
                name: 'Jane Doe',
                id: {
                    email: 'jane.doe@mail.com'
                }
             },
            {
                type: 'fdc3.contact',
                name: 'John Doe',
                id: {
                    email: 'john.doe@mail.com'
                }
            },
        ]
    },
    interactionType: 'Instant Message',
    timeRange: {
        type: 'fdc3.timeRange',
        startTime: '2022-02-10T15:12:00Z'
    },
    description: 'Laboris libero dapibus fames elit adipisicing eu, fermentum, dignissimos laboriosam, erat, risus qui deserunt. Praesentium! Reiciendis. Hic harum nostrud, harum potenti amet? Mauris. Pretium aliquid animi, eget eiusmod integer proident. Architecto ipsum blandit ducimus, possimus illum sunt illum necessitatibus ab litora sed, nonummy integer minus corrupti ducimus iste senectus accumsan, fugiat nostrud? Pede vero dictumst excepturi, iure earum consequuntur voluptatum',
    initiator:  {
        type: 'fdc3.contact',
        name: 'Jane Doe',
        id: {
            email: 'jane.doe@mail.com'
        }
    },
    origin: 'Outlook'
}

fdc3.raiseIntent('CreateInteraction', interaction)
```

## See Also

Other Types
- [Contact](Contact)
- [ContactList](ContactList)
- [TimeRange](TimeRange)

Intents
- [CreateInteraction](../../intents/ref/CreateInteraction)