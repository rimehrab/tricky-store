# Tricky Store

A trick of keystore. **Android 12 or above is required**.

## Testing

Tested on Poco F3 > MiUi 14 and OnePlus Nord Ce 3 Lite > Oxygen Os 14

## ToDo

Add support for more rom [Top Priority]

## Usage

1. Flash this module and reboot.
2. Enjoy!  

## keybox.xml

format:

```xml
<?xml version="1.0"?>
<AndroidAttestation>
    <NumberOfKeyboxes>1</NumberOfKeyboxes>
    <Keybox DeviceID="...">
        <Key algorithm="ecdsa|rsa">
            <PrivateKey format="pem">
-----BEGIN EC PRIVATE KEY-----
...
-----END EC PRIVATE KEY-----
            </PrivateKey>
            <CertificateChain>
                <NumberOfCertificates>...</NumberOfCertificates>
                    <Certificate format="pem">
-----BEGIN CERTIFICATE-----
...
-----END CERTIFICATE-----
                    </Certificate>
                ... more certificates
            </CertificateChain>
        </Key>...
    </Keybox>
</AndroidAttestation>
```


For Magisk users: if you don't need this feature and zygisk is disabled, please remove or rename the
folder `/data/adb/modules/tricky_store/zygisk` manually.

## Build Vars Spoofing

> **Zygisk (or Zygisk Next) is needed for this feature to work.**

If you still do not pass you can try enabling/disabling Build variable spoofing by creating/deleting the file `/data/adb/tricky_store/spoof_build_vars`.

Tricky Store will automatically generate example config props inside `/data/adb/tricky_store/spoof_build_vars` once created, on next reboot, then you may manually edit your spoof config.

Here is an example of a spoof config:

```
MANUFACTURER=Google
MODEL=Pixel 6
FINGERPRINT=google/oriole_beta/oriole:15/AP41.240823.009/12329489:user/release-keys
BRAND=Google
PRODUCT=oriole_beta
DEVICE=oriole
RELEASE=15
ID=AD1A.240530.047.U1
INCREMENTAL=12329489
TYPE=user
TAGS=release-keys
SECURITY_PATCH=2024-09-05
```

## Acknowledgement

- [PlayIntegrityFix](https://github.com/chiteroman/PlayIntegrityFix)
- [FrameworkPatch](https://github.com/chiteroman/FrameworkPatch)
- [BootloaderSpoofer](https://github.com/chiteroman/BootloaderSpoofer)
- [KeystoreInjection](https://github.com/aviraxp/Zygisk-KeystoreInjection)
- [LSPosed](https://github.com/LSPosed/LSPosed)
