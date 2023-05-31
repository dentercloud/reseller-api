+++
next = "/api/response-types/"
prev = "/api/authentication/"
title = "Access Control"
toc = true
weight = 30

+++

Access to the API by default is restricted by IP.

For situations where IP access control is not feasible, an Access Key can also be configured.

## Allowing IP

Provide your IP to Denter support to whitelist it.

## Configuring an Access Key

Alternatively an access key can be configured to allow IP restrictions to be bypassed.



```
$api_access_key = 'secret_key_passphrase_goes_here';
```

An API Access Key can contain letters, numbers, and the following special characters only:

```
! @ # $ % . ( ) * [ ] - _
```

Following the introduction of an API Access Key, you can then include it in your API requests as follows:

```
?action=xxxx&username=xxx&password=xxx&accesskey=secret_key_passphrase_goes_here
```
