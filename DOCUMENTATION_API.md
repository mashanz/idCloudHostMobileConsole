# 1. TOKEN VERIFICATION FEATURE

DATE_FORMAT: YYYY-MM-DD hh:mm:ss

```sh
# [ GET ]
https://api.idcloudhost.com/v1/user-resource/user

# HEADER
apikey: <API_KEY>
```
```json
// RESPONSE
{
    "cookie_id": "",              // [ string ] hash
    "id": 0,                      // [ int ]
    "name": "",                   // [ string ] email format
    "profile_data": {
        "id": 0,                  // [ int ]
        "updated_at": "",         // [ string ] date format
        "avatar": "",             // [ string ] link format
        "last_name": "",          // [ string ]
        "user_id": 0,             // [ int ]
        "created_at": "",         // [ string ] date format
        "email": "",              // [ string ] email format
        "first_name": ""          // [ string ]
    },
    "signup_site": ""             // [ string ]
}
```

# 2 GET TOKEN LIST
```sh
# [ GET ]
https://api.idcloudhost.com/v1/user-resource/token/list

# HEADER
apikey: <API_KEY>
```
```json
// RESPONSE
[
    {
        "billing_account_id": 0,  // [ int ]
        "consumer_id": "",        // [ string ]
        "created_at": "",         // [ string ] date format
        "description": "",        // [ string ]
        "id": 0,                  // [ int ]
        "kong_id": "",            // [ string ]
        "restricted": false,      // [ boolean ]
        "token": "",              // [ string ]
        "user_id": 0              // [ int ]
    }
]
```

# 3. GET SERVER LOCATION LIST
```sh
# [ GET ]
https://api.idcloudhost.com/v1/config/locations

# HEADER
apikey: <API_KEY>
```

```json
// RESPONSE
[
    {
        "display_name": "",     // [ string ]
        "is_preferred": false,  // [ boolean ]
        "is_default": false,    // [ boolean ]
        "description": "",      // [ string ]
        "country_code": "",     // [ string ] country 3 character format
        "order_nr": 0,          // [ int ]
        "slug": ""              // [ string ] slug format
    }
]
```

# 4. GET VM LIST BY LOCATION
```sh
# [ GET ]
https://api.idcloudhost.com/v1/<SLUG>/user-resource/vm/list?billing_account_id=<BILLING_ACCOUNT>

# HEADER
apikey: <API_KEY>
```
```json
// RESPONSE
[
    {
        "backup": false,          // [ boolean ]
        "billing_account": 0,     // [ int ]
        "created_at": "",         // [ string ] date format
        "description": "",        // [ string ] domain format
        "hostname": "",           // [ string ]
        "mac": "",                // [ string ] date format
        "memory": 0,              // [ int ]
        "name": "",               // [ string ] domain format
        "os_name": "",            // [ string ]
        "os_version": "",         // [ string ]
        "private_ipv4": "",       // [ string ] ip fomrat
        "status": "",             // [ string ]
        "storage": [
            {
                "created_at": "", // [ string ] date format
                "name": "",       // [ string ]
                "pool": "",       // [ string ]
                "primary": false, // [ boolean ]
                "replica": [],    // [ array object ]
                "shared": false,  // [ boolean ]
                "size": 0,        // [ int ]
                "type": "",       // [ string ]
                "user_id": 0,     // [ int ]
                "uuid": ""        // [ string ]
            }
        ],
        "updated_at": "",         // [ string ] date format
        "user_id": 0,             // [ int ]
        "username": "",           // [ string ]
        "uuid": "",               // [ string ]
        "vcpu": 0                 // [ int ]
    }
]
```

# 4.1 GET VM STATUS [ OPTIONAL ]
```sh
# [ GET ]
https://api.idcloudhost.com/v1/jkt01/user-resource/vm?uuid=<VM_UUID>
```

```json
// same as object no 4
```

# 5. START VM
```sh
# [ POST ]
https://api.idcloudhost.com/v1/jkt01/user-resource/vm/start

# x-www-form-urlencoded
uuid: <VM_UUID>
```

```json
// same as object no 4
```

# 6. STOP VM
```sh
# [ POST ]
https://api.idcloudhost.com/v1/jkt01/user-resource/vm/stop

# x-www-form-urlencoded
uuid: <VM_UUID>
```

```json
// same as object no 4
```