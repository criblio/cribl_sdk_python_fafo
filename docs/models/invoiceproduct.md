# InvoiceProduct


## Fields

| Field                                                                      | Type                                                                       | Required                                                                   | Description                                                                |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| `product_name`                                                             | *str*                                                                      | :heavy_check_mark:                                                         | N/A                                                                        |
| `line_items`                                                               | List[[models.InvoiceLineItem](../models/invoicelineitem.md)]               | :heavy_minus_sign:                                                         | N/A                                                                        |
| `grouped_line_items`                                                       | List[[models.InvoiceGroupedLineItem](../models/invoicegroupedlineitem.md)] | :heavy_minus_sign:                                                         | N/A                                                                        |