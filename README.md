# Subtitle convertor (XIF to SRT)

This service converts a XIF file to an SRT file. Publish a request onto the correct queue in the following format:

```
<root>
    <correlationId>abc123</correlationId>
    <data>
        <![CDATA[<XIF version="1.0" filename="C:\Users\akbasi\AppData\Local\Temp\Sen1.XIF">...</XIF>]]>
    </data>
</root>
```

The service will respond with a response on the response queue in the following format:

```
<?xml version="1.0" encoding="UTF-8"?>
<response>
    <correlationId>abc123</correlationId>
    <status>OK</status>
    <data>
        <![CDATA[1
00:00:00,000 --> 00:00:01,000
...

]]>
    </data>
</response>
```
