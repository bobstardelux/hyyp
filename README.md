This is a fork from https://github.com/RenierM26. This fork has reversed engineered the protobuf pb2 files and recompiled with version 4.21. THis fixes the issues on newer versions of home assistant.



0.0.0.7

Added feature: Binary sensor which shows which zone caused alarm trigger.


# pyHyypApi
API for ADT Secure Home and IDS Hyyp. There could be more variants but it's easy to add package names to the constants.py file.

How to use:

  1. Install:

```pip install pyhyypapihawkmod```

  2.1. Login (ADT Secure Home):


```
import pyhyypapihawkmod
import json
client = pyhyypapihawkmod.HyypClient(email="",password="")
client.login()
```

**OR**

  2.2. Login (IDT Hyyp):

```
import pyhyypapihawkmod
import json
client = pyhyypapihawkmod.HyypClient(email="",password="",pkg=pyhyypapihawkmod.HyypPkg.IDS_HYYP_GENERIC.value)
client.login()

```


3. Get site/partition/user/zone info:

```
print(json.dumps(client.get_sync_info(),indent=2))

```

TO Do:

- CLI usage. (GCF client is there, just needs some more automation.)
- Capture panic api...for obvious reasons.
- What zone caused arm/arm stay not to work. - Looks like GCM/Firebase push messages. Added GCM client...just run main program and register GCF code in function called register gcf. It works.
