# Remove Tags — Zoho CRM

Standalone reference for removing tags from Zoho CRM records using Zoho's CRM API.

## Deluge

```deluge
removeResponse = invokeurl
[
    url :apiUrl
    type :POST
    parameters:removePayload.toString()
    connection:"zoho_crm"
];
info removeResponse;
```

## API Endpoint Pattern

```deluge
apiUrl = "https://www.zohoapis.com/crm/v8/{Module_API_Name}/" + recordId + "/actions/remove_tags";
```

## Payload

```deluge
removeTagList = List();
removeTagMap = Map();
removeTagMap.put("name",tagName);
removeTagList.add(removeTagMap);

removePayload = Map();
removePayload.put("tags",removeTagList);
```

## Complete Example

```deluge
removeTagList = List();
removeTagMap = Map();
removeTagMap.put("name",tagName);
removeTagList.add(removeTagMap);

removePayload = Map();
removePayload.put("tags",removeTagList);

apiUrl = "https://www.zohoapis.com/crm/v8/{Module_API_Name}/" + recordId + "/actions/remove_tags";

removeResponse = invokeurl
[
    url :apiUrl
    type :POST
    parameters:removePayload.toString()
    connection:"zoho_crm"
];
info removeResponse;
```

## Notes

- Replace `{Module_API_Name}` with the CRM module API name.
- Replace `recordId` with the record ID.
- Replace `tagName` with the tag to remove.
- Keep the CRM connection name configured in your Zoho environment.
