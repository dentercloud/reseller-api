+++
title = "GetOrderStatuses"
toc = true
+++

Retrieve Order Status and number in those statuses

### Request Parameters

| Parameter | Type | Description | Required |
| --------- | ---- | ----------- | -------- |
| action | string | "GetOrderStatuses" | Required |

### Response Parameters

| Parameter | Type | Description |
| --------- | ---- | ----------- |
| result | string | The result of the operation: success or error |
| totalresults | int | The total number of results available |
| statuses | array | An array of order statuses |


### Example Request (CURL)

```
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, 'https://www.example.com/includes/api.php');
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_POSTFIELDS,
    http_build_query(
        array(
            'action' => 'GetOrderStatuses',
            // See https://developers.Denter.com/api/authentication
            'username' => 'IDENTIFIER_OR_ADMIN_USERNAME',
            'password' => 'SECRET_OR_HASHED_PASSWORD',
            'responsetype' => 'json',
        )
    )
);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
$response = curl_exec($ch);
curl_close($ch);
```


### Example Request (Local API)

```
$command = 'GetOrderStatuses';
$postData = array(
);
$adminUsername = 'ADMIN_USERNAME'; // Optional for Denter 7.2 and later

$results = localAPI($command, $postData, $adminUsername);
print_r($results);
```


### Example Response JSON

```
{
    "result": "success",
    "totalresults": "4",
    "statuses[status][0][Pending]": "1",
    "statuses[status][1][Active]": "15",
    "statuses[status][2][Fraud]": "0",
    "statuses[status][3][Cancelled]": "1",
    "statuses[status][4][My Custom Status]": "27"
}
```


### Version History

| Version | Changelog |
| ------- | --------- |
| 1.0 | Initial Version |
