# Initialized

## Description

The virtual classroom session has started. The session is initialized when the first participant or an administrator session has entered the virtual classroom.

## Example

```json
{
   "actor": {
      "account": {
         "name": "john",
         "homePage": "http://gaiax-virtualclassroom.org"
      }
   },
   "verb": {
      "id": "http://adlnet.gov/expapi/verbs/initialized"
   },
   "object": {
      "id": "http://gaiax.org/xapi/activities/e59490e1-ddf2-4c43-bfdc-14e274abc106",
      "definition": {
         "type": "http://id.tincanapi.com/activitytype/webinar",
         "name": {
            "en": "xAPI 101"
         }
      }
   },
   "context": {
      "registration": "4eb0e063-669b-479a-86b3-f9be9ac88a1d",
      "contextActivities": {
         "category": [
            {
               "id": "https://w3id.org/xapi/virtual-classroom",
               "definition": {
                  "type": "http://adlnet.gov/expapi/activities/profile"
               }
            }
         ]
      },
      "extensions": {
         "http://id.tincanapi.com/extension/planned-duration": "PT2",
         "https://w3id.org/xapi/cmi5/context/extensions/sessionid": "c7b6f0a9-482c-4c03-acc1-548289126963"
      }
   },
   "timestamp": "2016-06-09T15:34:26.887Z"
}
```

## Properties

- `verb.id`: INCLUDED, must be `http://adlnet.gov/expapi/verbs/initialized`
- `object.definition.type`: INCLUDED, must be `http://id.tincanapi.com/activitytype/webinar`.

## Rules

- `context.registration`: INCLUDED, must be the same for all the statements of a planned session, even when the virtual classroom is relaunched for technical reasons.
- `context.extensions.https://w3id.org/xapi/cmi5/context/extensions/sessionid`: INCLUDED, UUID format, must be the same for all the statements from `initialized` to `terminated` (i.e. technical session).
- `context.extensions.http://id.tincanapi.com/extension/planned-duration`: RECOMMENDED, ISO 8601 duration.
- `context.contextActivities.category`: MUST contain an activity with the `https://w3id.org/xapi/virtual-classroom` id.
- `timestamp`: INCLUDED



