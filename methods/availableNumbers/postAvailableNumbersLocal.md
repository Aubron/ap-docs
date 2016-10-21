{% method %}
## POST availableNumbers/local
Searches and order available local numbers by location criteria.

| Parameter          | Description                                                                                                                                                                                                                           | Mandatory |
|:-------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:----------|
| city               | A city name.                                                                                                                                                                                                                          | No        |
| state              | A two-letter US state abbreviation ("CA" for California).                                                                                                                                                                             | **        |
| zip                | A 5-digit US ZIP code.                                                                                                                                                                                                                | **        |
| areaCode           | A 3-digit telephone area code.                                                                                                                                                                                                        | **        |
| localNumber        | It is defined as the first digits of a telephone number inside an area code for filtering the results. It must have at least 3 digits and the areaCode field must be filled.                                                          | ***       |
| inLocalCallingArea | Boolean value to indicate that the search for available numbers must consider overlayed areas. Only applied for localNumber searching.                                                                                                | ***       |
| quantity           | The maximum number of numbers to return (default 10, maximum 5000).                                                                                                                                                                   | No        |
| pattern            | A number pattern that may include letters, digits, and the following wildcard characters: <br> ? : matches any single digit <br> * : matches zero or more digits<br> Don't forget to encode wildcard characters in the requested URL. | No        |

<aside class="notice">
** state, zip and areaCode are mutually exclusive, you may use only one of them per request.
</aside>
<aside class="notice">
*** localNumber and inLocalCallingArea only applies for searching numbers in specific areaCode.
</aside>

{% common %}
### Example: Search and allocate for city/state

> To search and order two available local numbers in the city of Cary, North Carolina, make the following request

{% sample lang="bash" %}
```bash
curl -v -X POST  https://api.catapult.inetwork.com/v1/availableNumbers/local?city=Cary&state=NC&quantity=2 \
  -u {token}:{secret} \
  -H "Content-type: application/json" \
```

{% sample lang="js" %}
```js
// Search 2 available local phone numbers with area code 910 and order them

// Promise
client.AvailableNumber.searchAndOrder("local", { areaCode : "910", quantity : 2 }).then(function (numbers) {});

// Callback
client.AvailableNumber.serchAndOrder("local", { areaCode : "910", quantity : 2 }, function (err, numbers) {});
```

{% sample lang="csharp" %}
```csharp
var results = await client.AvailableNumber.SearchAndOrderLocalAsync(
  new LocalNumberQueryForOrder{ AreaCode = "910", Quantity = 2});
```

{% sample lang="ruby" %}
```ruby
#coming soon
```

{% common %}
> The above command returns a `201` response JSON structured like this:

```json
[
    {
        "number": "{number1}",
        "nationalNumber": "{national_number1}",
        "price": "0.60",
        "location": "https://.../v1/users/.../phoneNumbers/{numberId1}"
    },
    {
        "number": "{number2}",
        "nationalNumber": "{national_number2}",
        "price": "0.60",
        "location": "https://.../v1/users/.../phoneNumbers/{numberId2}"
    }
]
```
{% endmethod %}