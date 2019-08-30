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

### Send SMS message

```python3 huawei-e5186-http-client.py sendsms message your_phone_number_here```

### Reboot router

```python3 huawei-e5186-http-client.py reboot```

### Turn mobile data on or off

```python3 huawei-e5186-http-client.py data on```

```python3 huawei-e5186-http-client.py data off```
