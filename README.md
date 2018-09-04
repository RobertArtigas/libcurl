# libcurl
libcurl for Clarion

## Required C6.3 and newer.

[libcurl home page](https://curl.haxx.se/libcurl/)  
[FAQ](https://clarionhub.com/t/libcurl-faq-https-github-com-mikeduglas-libcurl/1965)  
[Full version history](https://github.com/mikeduglas/libcurl/blob/master/history/changes.md)  
[Clarion 6.3 examples](https://github.com/mikeduglas/libcurl/tree/master/examples/C6.3%20apps)  


## How to install
Hit the 'Clone or Download' button and select 'Download Zip'.
Now unzip libcurl-master.zip into a temporary folder somewhere.

Copy the contents of...

Bin into %ClarionRoot%\Accessory\bin  
Lib into %ClarionRoot%\Accessory\lib  
Libsrc into %ClarionRoot%\Accessory\libsrc\win  
Template into %ClarionRoot%\Accessory\template\win  

Where %ClarionRoot% is the folder into which you installed Clarion 10.

Now, with no APPs or DCTs loaded in the Clarion IDE, register the libcurl template by selecting...
Clarion main menu - Tools - 'Edit Template Registry' - click on 'Register' and use the dialog to navigate to %ClarionRoot%\Accessory\template\win and double-click on libcurl.tpl and click 'Open'.

You should see 'Class LibcurlTpl - Libcurl template' and the LibcurlGloExt and LibcurlLocExt templates are now in the list.
Click on the Save icon 'floppy disk' and the Green arrow to close.


## Recent changes
v1.35

- NEW: TCurlMimeClass.SetDataCB method sets a callback-based data source for a mime part's body.  
- CHG: MimePost example now demonstrates both SetData and SetDataCB approaches.

v1.34

- CHG: Now uses libcurl v7.61.0, see [changelog](https://curl.haxx.se/changes.html) for details. Old binaries were moved to bin_v_7.52.1 subfolder.  
- CHG: Now uses OpenSSL v1.1.0i.  

- NEW: bitmasks for CURLOPT_HTTPAUTH and CURLOPT_PROXYAUTH options have been added: 
```
CURLAUTH_NTLM                 EQUATE(8)
CURLAUTH_DIGEST_IE            EQUATE(16)
CURLAUTH_NTLM_WB              EQUATE(32)
CURLAUTH_BEARER               EQUATE(64)
CURLAUTH_ONLY                 EQUATE(080000000h)
CURLAUTH_ANY                  EQUATE(0FFFFFFEFh)
CURLAUTH_ANYSAFE              EQUATE(0FFFFFFEEh)

```
- NEW: bitmasks for CURLOPT_SSLVERSION option have been added: 
```
CURL_SSLVERSION_MAX_DEFAULT   EQUATE(010000h)  !CURL_SSLVERSION_TLSv1   << 16
CURL_SSLVERSION_MAX_TLSv1_0   EQUATE(040000h)  !CURL_SSLVERSION_TLSv1_0 << 16
CURL_SSLVERSION_MAX_TLSv1_1   EQUATE(050000h)  !CURL_SSLVERSION_TLSv1_1 << 16
CURL_SSLVERSION_MAX_TLSv1_2   EQUATE(060000h)  !CURL_SSLVERSION_TLSv1_2 << 16
CURL_SSLVERSION_MAX_TLSv1_3   EQUATE(070000h)  !CURL_SSLVERSION_TLSv1_3 << 16
```
- NEW: CURLOPT_REQUEST_TARGET (the request target, instead of extracted from the URL)  
- NEW: CURLOPT_MIMEPOST (Post MIME data)  

- NEW: TCurlClass methods:
```
SetUserAgent  PROCEDURE(STRING pUserAgent), CURLcode, PROC    !default user-agent: curl/7.61.0
GetHandle     PROCEDURE(), CURL                               ! returns curl handle
SetMimePost   PROCEDURE(TCurlMimeClass mime), CURLcode, PROC  !set post/send data from mime structure
```
- NEW: TCurlMimeClass (libcurlmime.clw) implements new curl mime api.  
- NEW: MimePost example.  


[Full version history](https://github.com/mikeduglas/libcurl/blob/master/history/changes.md)
