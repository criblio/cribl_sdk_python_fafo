# UpdateSavedQueryByIDRequest


## Fields

| Field                                        | Type                                         | Required                                     | Description                                  |
| -------------------------------------------- | -------------------------------------------- | -------------------------------------------- | -------------------------------------------- |
| `id_param`                                   | *str*                                        | :heavy_check_mark:                           | Unique ID to PATCH                           |
| `saved_query`                                | [models.SavedQuery](../models/savedquery.md) | :heavy_check_mark:                           | SavedQuery object to be updated              |