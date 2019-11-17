# Custom Integration

You can also integrate validata by writing custom code within your application or data environment. To do that, you will need to send the events that you would like to be validated through an API request to the validation endpoint.

## Basic steps

1. Create a `source` on validata's web app.
2. Create an `event` for that source (where you will declare the event data structure expected)
3. Get the source `auth token` that is displayed for you within the app.
4. Make this request:

```
#POST validata-backend.herokuapp.com/validate

body:
- your events body payload

headers:
- "Accept: application/json"
- "auth-token: the-token-generated-by-us"
```

Please note that is absolutely crucial that you send us a key called `event: Event_Name` where `Event_Name` is a value you will change according to the `name` of your event, since thats how we can identify wihch schema belongs to what event.
