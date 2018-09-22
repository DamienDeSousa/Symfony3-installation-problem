# Symfony3-installation-problem

If you get some installation problems like this:

    [GuzzleHttp\Exception\RequestException]
    cURL error 60: SSL certificate problem: unable to get local issuer certificate
    [GuzzleHttp\Ring\Exception\RingException]
    cURL error 60: SSL certificate problem: unable to get local issuer certificate

Do the following things:
=======================

1. Download the certificate here: [https://curl.haxx.se/ca/cacert.pem]
2. Copy it in your wamp folder. For instance on my own machine it's C:/wamp/bin.
3. Find the php.ini using the following command line in a terminal: `php --ini`.
4. Open the php.ini file and check if `extension=php_openssl.dll is uncommented`.
5. Check also if `curl.cainfo="path/to/cacert.pem"` exists. If not, add this line. For me it's `curl.cainfo="C:\wamp\bin\cacert.pem"`.
6. Restart Wamp and it should works !