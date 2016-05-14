---
title: Public API Service 1

search: true
---

# Public API Service 1
> ### Produces


# Orders
## 

```http
GET /1.0/commerce/orders/ HTTP/1.1
```
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "result": [
        {
            "id": "string",
            "orderNumber": "string",
            "createdOn": "string",
            "testmode": "boolean",
            "billingAddress": {
                "firstName": "string",
                "lastName": "string",
                "address1": "string",
                "address2": "string",
                "city": "string",
                "state": "string",
                "countryCode": "string",
                "postalCode": "string"
            },
            "shippingAddress": {
                "firstName": "string",
                "lastName": "string",
                "address1": "string",
                "address2": "string",
                "city": "string",
                "state": "string",
                "countryCode": "string",
                "postalCode": "string"
            },
            "fulfillmentStatus": "string",
            "lineItems": [
                {
                    "id": "string",
                    "sku": "string",
                    "productId": "string",
                    "productName": "string",
                    "quantity": "integer",
                    "variantOptions": [
                        {
                            "optionName": "string",
                            "value": "string"
                        }
                    ]
                }
            ],
            "shippingLines": [
                {
                    "method": "string",
                    "amount": {
                        "value": "string",
                        "currency": "string"
                    }
                }
            ],
            "discountLines": [
                {
                    "description": "string",
                    "amount": {
                        "value": "string",
                        "currency": "string"
                    },
                    "promoCode": "string"
                }
            ],
            "subtotal": {
                "value": "string",
                "currency": "string"
            },
            "shippingTotal": {
                "value": "string",
                "currency": "string"
            },
            "discountTotal": {
                "value": "string",
                "currency": "string"
            },
            "taxTotal": {
                "value": "string",
                "currency": "string"
            },
            "refundedTotal": {
                "value": "string",
                "currency": "string"
            },
            "grandTotal": {
                "value": "string",
                "currency": "string"
            }
        }
    ],
    "nextPageUrl": "string",
    "prevPageUrl": "string"
}
```

Gets all orders with pagination parameters provided.


### Parameters
Name | In | Type | Description
--- | --- | --- | ---
modifiedAfter<b title="required">&nbsp;*&nbsp;</b> | query | string | 
modifiedBefore<b title="required">&nbsp;*&nbsp;</b> | query | string | 
cursor | query | string | 
//todo: migrate to html tables. after cool looking nested table
### Responses
<span comment="workaround for markdown processing in table"></span>
<table>
<tr><th>Http code</th><th>Type</th><th>Description</th></tr>
<tr><td>200</td><td>[OrderListResponse](#orderlistresponse)</td><td>Return a list of Order objects</td></tr> 
</table>

## 

```http
GET /1.0/commerce/orders/{id} HTTP/1.1
```
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "id": "string",
    "orderNumber": "string",
    "createdOn": "string",
    "testmode": "boolean",
    "billingAddress": {
        "firstName": "string",
        "lastName": "string",
        "address1": "string",
        "address2": "string",
        "city": "string",
        "state": "string",
        "countryCode": "string",
        "postalCode": "string"
    },
    "shippingAddress": {
        "firstName": "string",
        "lastName": "string",
        "address1": "string",
        "address2": "string",
        "city": "string",
        "state": "string",
        "countryCode": "string",
        "postalCode": "string"
    },
    "fulfillmentStatus": "string",
    "lineItems": [
        {
            "id": "string",
            "sku": "string",
            "productId": "string",
            "productName": "string",
            "quantity": "integer",
            "variantOptions": [
                {
                    "optionName": "string",
                    "value": "string"
                }
            ]
        }
    ],
    "shippingLines": [
        {
            "method": "string",
            "amount": {
                "value": "string",
                "currency": "string"
            }
        }
    ],
    "discountLines": [
        {
            "description": "string",
            "amount": {
                "value": "string",
                "currency": "string"
            },
            "promoCode": "string"
        }
    ],
    "subtotal": {
        "value": "string",
        "currency": "string"
    },
    "shippingTotal": {
        "value": "string",
        "currency": "string"
    },
    "discountTotal": {
        "value": "string",
        "currency": "string"
    },
    "taxTotal": {
        "value": "string",
        "currency": "string"
    },
    "refundedTotal": {
        "value": "string",
        "currency": "string"
    },
    "grandTotal": {
        "value": "string",
        "currency": "string"
    }
}
```

Fetches one order.


### Parameters
Name | In | Type | Description
--- | --- | --- | ---
id<b title="required">&nbsp;*&nbsp;</b> | path | string | 
//todo: migrate to html tables. after cool looking nested table
### Responses
<span comment="workaround for markdown processing in table"></span>
<table>
<tr><th>Http code</th><th>Type</th><th>Description</th></tr>
<tr><td>200</td><td>[Order](#order)</td><td>Return an Order object</td></tr> 
</table>

## 

```http
POST /1.0/commerce/orders/{id}/fulfillments HTTP/1.1
Content-Type: application/json

{
    "update": {
        "carrier": "string",
        "service": "string",
        "trackingNumber": "string"
    }
}
```
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "carrier": "string",
    "service": "string",
    "trackingNumber": "string"
}
```

Fulfills this order, changing the order status and emitting notifications.


### Parameters
Name | In | Type | Description
--- | --- | --- | ---
id<b title="required">&nbsp;*&nbsp;</b> | path | string | 
update | body | [FulfillmentRequest](#fulfillmentrequest) | 
//todo: migrate to html tables. after cool looking nested table
### Responses
<span comment="workaround for markdown processing in table"></span>
<table>
<tr><th>Http code</th><th>Type</th><th>Description</th></tr>
<tr><td>200</td><td>[Fulfillment](#fulfillment)</td><td>Return a Fulfillment object</td></tr> 
</table>

# Blogposts
## Read blog posts

```http
GET /1.0/{blog_id}/posts HTTP/1.1
```
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "results": [
        {
            "id": "string",
            "title": "string",
            "content_html": "string",
            "content_markdown": "string",
            "excerpt": "string",
            "tags": [
                "string"
            ],
            "categories": [
                "string"
            ],
            "workflowState": "string",
            "comments_allowed": "boolean",
            "featured": "boolean"
        }
    ],
    "pagination": {
        "count": "integer",
        "next_url": "string",
        "prev_url": "string"
    }
}
```

The blog posts read endpoint returns all posts



### Parameters
Name | In | Type | Description
--- | --- | --- | ---
blog_id<b title="required">&nbsp;*&nbsp;</b> | path | string | The identifier for a blog collection.
//todo: migrate to html tables. after cool looking nested table
### Responses
<span comment="workaround for markdown processing in table"></span>
<table>
<tr><th>Http code</th><th>Type</th><th>Description</th></tr>
<tr><td>200</td><td>[GetBlogPostsResponse](#getblogpostsresponse)</td><td>An array of posts</td></tr> 
</table>
## Create a blog post

```http
POST /1.0/{blog_id}/posts HTTP/1.1
Content-Type: application/json

{
    "body": {
        "id": "string",
        "title": "string",
        "content_html": "string",
        "content_markdown": "string",
        "excerpt": "string",
        "tags": [
            "string"
        ],
        "categories": [
            "string"
        ],
        "workflowState": "string",
        "comments_allowed": "boolean",
        "featured": "boolean"
    }
}
```
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "id": "string",
    "title": "string",
    "content_html": "string",
    "content_markdown": "string",
    "excerpt": "string",
    "tags": [
        "string"
    ],
    "categories": [
        "string"
    ],
    "workflowState": "string",
    "comments_allowed": "boolean",
    "featured": "boolean"
}
```

The blog posts create endpoint adds a blog post and returns its new value



### Parameters
Name | In | Type | Description
--- | --- | --- | ---
blog_id<b title="required">&nbsp;*&nbsp;</b> | path | string | The identifier for a blog collection.
body<b title="required">&nbsp;*&nbsp;</b> | body | [BlogPost](#blogpost) | 
//todo: migrate to html tables. after cool looking nested table
### Responses
<span comment="workaround for markdown processing in table"></span>
<table>
<tr><th>Http code</th><th>Type</th><th>Description</th></tr>
<tr><td>200</td><td>[BlogPost](#blogpost)</td><td>The new blog post</td></tr> 
</table>

## Update a blog post

```http
PUT /1.0/{blog_id}/posts/{post_id} HTTP/1.1
Content-Type: application/json

{
    "body": {
        "id": "string",
        "title": "string",
        "content_html": "string",
        "content_markdown": "string",
        "excerpt": "string",
        "tags": [
            "string"
        ],
        "categories": [
            "string"
        ],
        "workflowState": "string",
        "comments_allowed": "boolean",
        "featured": "boolean"
    }
}
```
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "id": "string",
    "title": "string",
    "content_html": "string",
    "content_markdown": "string",
    "excerpt": "string",
    "tags": [
        "string"
    ],
    "categories": [
        "string"
    ],
    "workflowState": "string",
    "comments_allowed": "boolean",
    "featured": "boolean"
}
```
```http
HTTP/1.1 default 
Content-Type: application/json

{
    "code": "integer",
    "message": "string",
    "fields": "string"
}
```

The blog posts update endpoint modifies a blog post and returns its new value



### Parameters
Name | In | Type | Description
--- | --- | --- | ---
blog_id<b title="required">&nbsp;*&nbsp;</b> | path | string | The identifier for a blog collection.
post_id<b title="required">&nbsp;*&nbsp;</b> | path | string | The identifier for a blog post item.
body<b title="required">&nbsp;*&nbsp;</b> | body | [BlogPost](#blogpost) | 
//todo: migrate to html tables. after cool looking nested table
### Responses
<span comment="workaround for markdown processing in table"></span>
<table>
<tr><th>Http code</th><th>Type</th><th>Description</th></tr>
<tr><td>200</td><td>[BlogPost](#blogpost)</td><td>The new blog post</td></tr> 
<tr><td>default</td><td>[Error](#error)</td><td>Unexpected error</td></tr> 
</table>
## Delete a blog post

```http
DELETE /1.0/{blog_id}/posts/{post_id} HTTP/1.1
```
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "success": "boolean"
}
```
```http
HTTP/1.1 default 
Content-Type: application/json

{
    "code": "integer",
    "message": "string",
    "fields": "string"
}
```

The blog posts delete endpoint destroys a blog post



### Parameters
Name | In | Type | Description
--- | --- | --- | ---
blog_id<b title="required">&nbsp;*&nbsp;</b> | path | string | The identifier for a blog collection.
post_id<b title="required">&nbsp;*&nbsp;</b> | path | string | The identifier for a blog post item.
//todo: migrate to html tables. after cool looking nested table
### Responses
<span comment="workaround for markdown processing in table"></span>
<table>
<tr><th>Http code</th><th>Type</th><th>Description</th></tr>
<tr><td>200</td><td>[DeleteBlogPostResponse](#deleteblogpostresponse)</td><td>The new blog post</td></tr> 
<tr><td>default</td><td>[Error](#error)</td><td>Unexpected error</td></tr> 
</table>


# Models
## Order
```json
{
    "id": "string",
    "orderNumber": "string",
    "createdOn": "string",
    "testmode": "boolean",
    "billingAddress": {
        "firstName": "string",
        "lastName": "string",
        "address1": "string",
        "address2": "string",
        "city": "string",
        "state": "string",
        "countryCode": "string",
        "postalCode": "string"
    },
    "shippingAddress": {
        "firstName": "string",
        "lastName": "string",
        "address1": "string",
        "address2": "string",
        "city": "string",
        "state": "string",
        "countryCode": "string",
        "postalCode": "string"
    },
    "fulfillmentStatus": "string",
    "lineItems": [
        {
            "id": "string",
            "sku": "string",
            "productId": "string",
            "productName": "string",
            "quantity": "integer",
            "variantOptions": [
                {
                    "optionName": "string",
                    "value": "string"
                }
            ]
        }
    ],
    "shippingLines": [
        {
            "method": "string",
            "amount": {
                "value": "string",
                "currency": "string"
            }
        }
    ],
    "discountLines": [
        {
            "description": "string",
            "amount": {
                "value": "string",
                "currency": "string"
            },
            "promoCode": "string"
        }
    ],
    "subtotal": {
        "value": "string",
        "currency": "string"
    },
    "shippingTotal": {
        "value": "string",
        "currency": "string"
    },
    "discountTotal": {
        "value": "string",
        "currency": "string"
    },
    "taxTotal": {
        "value": "string",
        "currency": "string"
    },
    "refundedTotal": {
        "value": "string",
        "currency": "string"
    },
    "grandTotal": {
        "value": "string",
        "currency": "string"
    }
}
```
	
### Fields
Name | Type | Description
--- | --- | ---
id | string | 
orderNumber | string | 
createdOn | string | 
testmode | boolean | 
billingAddress | [Address](#address) | 
shippingAddress | [Address](#address) | 
fulfillmentStatus | string | 
lineItems | array[[LineItem](#lineitem)] | 
shippingLines | array[[ShippingLine](#shippingline)] | 
discountLines | array[[DiscountLine](#discountline)] | 
subtotal | [Money](#money) | 
shippingTotal | [Money](#money) | 
discountTotal | [Money](#money) | 
taxTotal | [Money](#money) | 
refundedTotal | [Money](#money) | 
grandTotal | [Money](#money) | 

	
## Address
```json
{
    "firstName": "string",
    "lastName": "string",
    "address1": "string",
    "address2": "string",
    "city": "string",
    "state": "string",
    "countryCode": "string",
    "postalCode": "string"
}
```
	
### Fields
Name | Type | Description
--- | --- | ---
firstName | string | 
lastName | string | 
address1 | string | 
address2 | string | 
city | string | 
state | string | 
countryCode | string | 
postalCode | string | 

	
## ShippingLine
```json
{
    "method": "string",
    "amount": {
        "value": "string",
        "currency": "string"
    }
}
```
	
### Fields
Name | Type | Description
--- | --- | ---
method<b title="required">&nbsp;*&nbsp;</b> | string | the delivery method selected, e.g. &quot;UPS Ground&quot;
amount<b title="required">&nbsp;*&nbsp;</b> | [Money](#money) | the shipping charge for this order

	
## OrderListResponse
```json
{
    "result": [
        {
            "id": "string",
            "orderNumber": "string",
            "createdOn": "string",
            "testmode": "boolean",
            "billingAddress": {
                "firstName": "string",
                "lastName": "string",
                "address1": "string",
                "address2": "string",
                "city": "string",
                "state": "string",
                "countryCode": "string",
                "postalCode": "string"
            },
            "shippingAddress": {
                "firstName": "string",
                "lastName": "string",
                "address1": "string",
                "address2": "string",
                "city": "string",
                "state": "string",
                "countryCode": "string",
                "postalCode": "string"
            },
            "fulfillmentStatus": "string",
            "lineItems": [
                {
                    "id": "string",
                    "sku": "string",
                    "productId": "string",
                    "productName": "string",
                    "quantity": "integer",
                    "variantOptions": [
                        {
                            "optionName": "string",
                            "value": "string"
                        }
                    ]
                }
            ],
            "shippingLines": [
                {
                    "method": "string",
                    "amount": {
                        "value": "string",
                        "currency": "string"
                    }
                }
            ],
            "discountLines": [
                {
                    "description": "string",
                    "amount": {
                        "value": "string",
                        "currency": "string"
                    },
                    "promoCode": "string"
                }
            ],
            "subtotal": {
                "value": "string",
                "currency": "string"
            },
            "shippingTotal": {
                "value": "string",
                "currency": "string"
            },
            "discountTotal": {
                "value": "string",
                "currency": "string"
            },
            "taxTotal": {
                "value": "string",
                "currency": "string"
            },
            "refundedTotal": {
                "value": "string",
                "currency": "string"
            },
            "grandTotal": {
                "value": "string",
                "currency": "string"
            }
        }
    ],
    "nextPageUrl": "string",
    "prevPageUrl": "string"
}
```
	
### Fields
Name | Type | Description
--- | --- | ---
result | array[[Order](#order)] | 
nextPageUrl | string | 
prevPageUrl | string | 

	
## VariantOption
```json
{
    "optionName": "string",
    "value": "string"
}
```

a variant option chosen by a shopper (e.g. red + small)

	
### Fields
Name | Type | Description
--- | --- | ---
optionName<b title="required">&nbsp;*&nbsp;</b> | string | 
value<b title="required">&nbsp;*&nbsp;</b> | string | the shopper-selected value for the option (e.g. red, small, cotton)

	
## DeleteBlogPostResponse
```json
{
    "success": "boolean"
}
```
	
### Fields
Name | Type | Description
--- | --- | ---
success | boolean | 

	
## LineItem
```json
{
    "id": "string",
    "sku": "string",
    "productId": "string",
    "productName": "string",
    "quantity": "integer",
    "variantOptions": [
        {
            "optionName": "string",
            "value": "string"
        }
    ]
}
```
	
### Fields
Name | Type | Description
--- | --- | ---
id | string | 
sku | string | 
productId | string | 
productName | string | 
quantity | integer | 
variantOptions | array[[VariantOption](#variantoption)] | 

	
## Error
```json
{
    "code": "integer",
    "message": "string",
    "fields": "string"
}
```
	
### Fields
Name | Type | Description
--- | --- | ---
code | integer | 
message | string | 
fields | string | 

	
## GetBlogPostsResponse
```json
{
    "results": [
        {
            "id": "string",
            "title": "string",
            "content_html": "string",
            "content_markdown": "string",
            "excerpt": "string",
            "tags": [
                "string"
            ],
            "categories": [
                "string"
            ],
            "workflowState": "string",
            "comments_allowed": "boolean",
            "featured": "boolean"
        }
    ],
    "pagination": {
        "count": "integer",
        "next_url": "string",
        "prev_url": "string"
    }
}
```
	
### Fields
Name | Type | Description
--- | --- | ---
results | array[[BlogPost](#blogpost)] | 
pagination | [Pagination](#pagination) | 

	
## BlogPost
```json
{
    "id": "string",
    "title": "string",
    "content_html": "string",
    "content_markdown": "string",
    "excerpt": "string",
    "tags": [
        "string"
    ],
    "categories": [
        "string"
    ],
    "workflowState": "string",
    "comments_allowed": "boolean",
    "featured": "boolean"
}
```
	
### Fields
Name | Type | Description
--- | --- | ---
id | string | Unique identifier representing a specific blog post.
title<b title="required">&nbsp;*&nbsp;</b> | string | The blog post title.
content_html | string | The content of the blog post, represented in HTML.
content_markdown | string | The content of the blog post, represented in markdown.
excerpt | string | A short plain text excerpt to be displayed in list views of this blog.
tags | array[string] | A list of tags for this post.
categories | array[string] | A list of categories for this post.
workflowState | string | The workflow state. One of &quot;draft&quot;, &quot;published&quot;, &quot;review&quot; or &quot;scheduled&quot;.
comments_allowed | boolean | Should comments be enabled on this post?
featured | boolean | Should this post be featured?

	
## FulfillmentRequest
```json
{
    "carrier": "string",
    "service": "string",
    "trackingNumber": "string"
}
```
	
### Fields
Name | Type | Description
--- | --- | ---
carrier | string | the shipping carrier, e.g. &quot;FedEx&quot;, &quot;USPS&quot;, etc.
service | string | the service used, e.g. &quot;Priority Mail&quot;, &quot;Ground&quot;, etc.
trackingNumber | string | the carrier-generated tracking number

	
## Fulfillment
```json
{
    "carrier": "string",
    "service": "string",
    "trackingNumber": "string"
}
```
	
### Fields
Name | Type | Description
--- | --- | ---
carrier | string | the shipping carrier, e.g. &quot;FedEx&quot;, &quot;USPS&quot;, etc.
service | string | the service used, e.g. &quot;Priority Mail&quot;, &quot;Ground&quot;, etc.
trackingNumber | string | the carrier-generated tracking number

	
## Money
```json
{
    "value": "string",
    "currency": "string"
}
```
	
### Fields
Name | Type | Description
--- | --- | ---
value | string | 
currency | string | 

	
## Pagination
```json
{
    "count": "integer",
    "next_url": "string",
    "prev_url": "string"
}
```
	
### Fields
Name | Type | Description
--- | --- | ---
count | integer | The number of results in this response.
next_url | string | A URL that can be used to obtain the next page of results.
prev_url | string | A URL that can be used to obtain the previous page of results.

	
## DiscountLine
```json
{
    "description": "string",
    "amount": {
        "value": "string",
        "currency": "string"
    },
    "promoCode": "string"
}
```
	
### Fields
Name | Type | Description
--- | --- | ---
description<b title="required">&nbsp;*&nbsp;</b> | string | 
amount<b title="required">&nbsp;*&nbsp;</b> | [Money](#money) | 
promoCode | string | 

	
