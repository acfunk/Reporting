# Getting Started with Reporting API
###Authorization

Authorization is easy, just insert your secret key in the `Authorization` header:

`Authorization: secretKEYGOESHERE`
  
###Content Types
Communicate with us in your favorite content type!

We support the following for `Content-Type` and `Accepts` values:

* `application/json`

##Transactions

###[Stored Value Reports](STOREDVALUE.md)
* [Business Reconcile](STOREDVALUE.md#load) `GET` /storedvalue/business/reconcile?startDate=**{startDate}**&endDate=**{endDate}**
* [Business Liability Current](STOREDVALUE.md#void-load) `GET` /storedvalue/business/liabilityCurrent
* [Business Liability Effective](STOREDVALUE.md#sale) `GET` /storedvalue/business/liabilityEffective?effectiveDate=**{effectiveDate}**

###Success Responses
* ```200 OK```

###Failure Responses
* ```400 BAD REQUEST```
* ```401 UNAUTHORIZED```

###Example Stored Value Business Reconcile Request

```
GET https://reporting.monetary.co/v1/storedvalue/business/reconcile?startDate=2016-10-1&endDate=2016-10-31

Authorization: secretKEYGOESHERE
Content-Type: application/json
Accept: application/json
```

###Example Stored Value Business Reconcile Response
```
200 OK

[{"GroupId":1,"Group":"Bark & Meow","Amount":"-11.23"}]
```
