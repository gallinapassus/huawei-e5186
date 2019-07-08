# huawei-e5186
HTTP client for Huawei E5186 mobile broadband router.

## Username and password

This script assumes router has 'admin' user account.

Edit the router's password to variable passwordSHA256 (as SHA256 hexdigest)
-or-
set your password with command line option -s.

You can convert your plaintext password to SHA256 hexdigest with following command:

```echo -n 'router password' | shasum -a 256```

## Default IP-address

By default this script assumes your router's internal IP-address is 192.168.8.1.
Use -t option to set an alternative address/hostname.

## Usage

```python3 huawei-e5186-http-client.py -h```

## Examples

### Show traffic stats (all)

```python3 huawei-e5186-http-client.py show traffic```

### Traffic stats (filtered)

```python3 huawei-e5186-http-client.py show traffic TotalUpload TotalDownload```

### Show MAC address blacklist/whitelist

```python3 huawei-e5186-http-client.py show mac-filter```

### Send SMS message

```python3 huawei-e5186-http-client.py sendsms message your_phone_number_here```

### Reboot router

```python3 huawei-e5186-http-client.py reboot```

### Blacklist/whitelist MAC address(-es)

```python3 huawei-e5186-http-client.py mac-filter deny 1:2:3:4:5:6 1:2:3:4:5:7```

```python3 huawei-e5186-http-client.py mac-filter allow 1:2:3:4:5:6 1:2:3:4:5:7```

**NB!** You must specify the full list of MAC addresses to blacklist/whitelist.
E.g. if you have 1:2:3:4:5:6 blacklisted then calling `deny 1:2:3:4:5:7` will remove 1:2:3:4:5:6
and add 1:2:3:4:5:7 to the blacklist.
