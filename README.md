# **Copy Certificates**
## Description
Based on [Move Certificates](https://github.com/Magisk-Modules-Repo/movecert).
Copies certificates from the user certificate store to the system store.
## Rationale
Chrome recently started requiring CT logs for certs issues by CAs from the system store.
One way to continue using Chrome while having custom CA certs in the system store
is to copy the custom certs from the user store instead of moving them, and exclude
Chrome from Magisk modifications (which can be done in recent version of Magisk by
enabling Zygisk and adding Chrome to the denylist). This way Chrome will use
the certificates from the user store, for which CT is not mandatory, while
other apps will see the certificates in the system store.
