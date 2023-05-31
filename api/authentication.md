+++
next = "/api/internal-api"
prev = "/api/getting-started"
title = "Authentication"
toc = true
weight = 20

+++

Use of the API requires API Authentication Credentials. This is currently obtained manually through Denter Cloud support.

Authentication is required for each API request.

## Authenticating with API Credentials

API requests will be authenticated based on the request parameters `identifier` and `secret`

```
$api_identifier = 'D4j1dKYE3g40VROOPCGyJ9zRwP0ADJIv';
$api_secret = 'F1CKGXRIpylMfsrig3mwwdSdYUdLiFlo';

$postfields = array(
    'identifier' => $api_identifier,
    'secret' => $api_secret,
    'action' => $api_call,
    'responsetype' => $response_type,
);
```

For forwards compatibility with existing integrations, the `identifier` and `secret` may also be passed in the `username` and `password` fields respectively. A valid identifier and secret combination passed in this way will also result in successful authentication.

## Authenticating with Login Credentials

```
$username = "your_admin_login_username";
$password = "your_admin_login_password";

$postfields = array(
    'username' => $username,
    'password' => md5($password),
    'action' => $api_call,
    'responsetype' => $response_type,
);
```
