![logo](../assets/images/mkdocs_logo.jpg){: width=150 }

# dmkdocs - Getting Started
---

**Version** : `1.0.0`

**Revision History**

| Version  | Date          |  <div style="width:3rem">Author</div>   | Content Revised                                        |
| -------- | ------------- | --------- | ------------------------------------------------------------------------------------ |
| 1.0.0    | 2021/04/19    | elyse | Initial release.                                                                     |


**Table of Contents**
{: .my-page-break-before}

[TOC]

## Setup {: .my-page-break-before}
---

![wtf](images/wtf.jpg)

Edit `docs/sites/default.yml`

### Site Info
---

``` yaml
site_name: Title
site_description: Description
```

###  Navigation
---

``` yaml
nav:
  - Tab 1: 'docs/index.md'
  - Tab 2:
     - Section 1: 'docs/tab1/section1/index.md'
     - Section 2: 'docs/tab1/section2/index.md'
```

## Examples
---

The device should maintain the flexibility for the configuration data format changes, unrecognized fields should be ignored.

All fields are optional, i.e., partial configuration should be supported.

| Field               || Type | Description |
| ------------------- || ---- |----------- |
| user                || List of [`user`](#user) | User configuration |
| network | ipv4       | [`ipv4`](#ipv4) | IPv4 network configuration |
| time    | timezone   | [`timezone`](#timezone) | Time zone configuration|

**Example :**

``` json
{
    "user": [
        {
            "username": "admin",
            "password": "awesome-password",
            "role": "admin"
        }
    ],
    "network": {
        "ipv4": {
            "mode": "static",
            "ip": "192.168.0.5",
            "netmask": "255.255.255.0",
            "gateway": "192.168.0.1",
            "dns": [
                "8.8.8.8",
                "1.1.1.1"
            ]
        }
    },
    "time": {
        "timezone": {
            "utcOffset": "+09:00"
        }
    }
}
```

### Type Definitions
---

#### user
---

Type : object

| Field    | Type   | Description |
| -------- | ------ | ----------- |
| username | string | Username    |
| password | string | Password    |
| role     | string | `admin` - Administrator |

#### ipv4
---

Type : object

| Field    | Type   | Description |
| -------- | ------ | ----------- |
| mode     | string | - `static` - Static IP configuration <br> - `dhcp` (Default) - IP configuraiton by DHCP |
| ip       | string | - Get : Current IP address <br> - Set : Ignore if `mode` eqauls `dhcp`|
| netmask  | string | - Get : Current netmask <br> - Set : Ignore if `mode` eqauls `dhcp`|
| gateway  | string | - Get : Current default gateway <br> - Set : Ignore if `mode` eqauls `dhcp`|
| dns      | List of string | - Get : Current DNS servers <br> - Set : Ignore if `mode` eqauls `dhcp`|

#### timezone
---

Type : object

| Field     | Type   | Description |
| --------- | ------ | ----------- |
| utcOffset | string | - UTC offset <br> - Default : `+00:00`  |

