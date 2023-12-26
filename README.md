# Zygisk-SSL-Unpinning

Bypass ssl pinning with zygisk.

## Supports
- [x] arm64-v8a
- [ ] armeabi-v7a [TODO]
- [ ] x86 [TODO]
- [ ] x86_64 [TODO]

## Usage
- Enable zygisk in magisk or ZygiskNext (KernelSU)
- Flash the module
- Reboot
- Rename the file `config.json.example` to `config.json` in the path `/data/local/tmp/zyg.ssl`
- Replace `com.target.package` to your package name
- Launch your app (if the configuration is not updated, relaunch again)
- check `adb logcat | grep -i ZygiskSSL` to see if an error is logged


## Config File
```json
{
    "targets": [
        {
            "pkg_name" : "com.target.package",
            "enable": true,
            "start_safe": true,
            "start_delay": 1000
        }
    ]
}
```
### pkg_name
Identifier of the application.
### enable
If set to false, then this module will ignore this configuration.
### start_safe
If set to true, then this module wait for process initialization to complete.
### start_delay
Delay in milliseconds.

