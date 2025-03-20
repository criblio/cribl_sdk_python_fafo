# InvoiceV5


## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `id`                                                                 | *str*                                                                | :heavy_check_mark:                                                   | N/A                                                                  |
| `from_date`                                                          | [date](https://docs.python.org/3/library/datetime.html#date-objects) | :heavy_check_mark:                                                   | N/A                                                                  |
| `to_date`                                                            | [date](https://docs.python.org/3/library/datetime.html#date-objects) | :heavy_check_mark:                                                   | N/A                                                                  |
| `total_credits`                                                      | *float*                                                              | :heavy_check_mark:                                                   | N/A                                                                  |
| `status`                                                             | [models.InvoiceV5Status](../models/invoicev5status.md)               | :heavy_check_mark:                                                   | N/A                                                                  |
| `products`                                                           | List[[models.InvoiceProductV5](../models/invoiceproductv5.md)]       | :heavy_check_mark:                                                   | N/A                                                                  |