---
id: Email
sidebar_label: Email
title: Email
hide_title: true
---
# `Email`

A collection of information to be used to initiate an email with a Contact or ContactList

## Type

`fdc3.email`

## Schema

https://fdc3.finos.org/schemas/next/email.schema.json

## Details

| Property          | Type                                  | Required | Example Value       |
|-------------------|---------------------------------------|----------|---------------------|
| `type`            | string                                | Yes      | `'fdc3.email'` |
| `recipients`      | fdc3.contact or fdc3.contactList      | Yes      | { type: "fdc3.contact", name: "John Doe", id: { "email": "john@sample.com"}} |
| `subject`         | string                                | No       | `'The information you requested'`            |
| `textBody`        | string                                | No       | `'Blah, blah, bah`         |
| `richTextBody`    | fdc3.richTextBlock                    | No       | See https://github.com/finos/FDC3/issues/575        |

**Note: ** richTextBody requires a fdc3.richTextBlock, the specification of which is currently being finalised. As richTextBody is an optional
field, textBody can be used until the fdc3.richTextBlock type is finalised


## Example

```js
const email = {
  type: 'fdc3.email',
  recipients: {
    type: 'fdc3.contact',
    name: 'Jane Doe',
    id: {
      email: 'jane.doe@example.com'
    }
  },
  subject: 'The information you requested',
  textBody: 'Blah, blah, blah ...'
}


fdc3.broadcast(email)
```

## See Also

Other Types
* [Contact](Contact)
* [ContactList](ContactList)

Intents
* [StartEmail](../../intents/ref/StartEmail)