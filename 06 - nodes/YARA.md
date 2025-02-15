#tool-blue/threat-intelligence 

```json
rule silent_banker : banker
{
    meta:
        description = "This is just an example"
        threat_level = 3
        in_the_wild = true

    strings:
        $a = {6A 40 68 00 30 00 00 6A 14 8D 91}
        $b = {8D 4D B0 2B C1 83 C0 27 99 6A 4E 59 F7 F9}
        $c = "UVODFRYSIHLNWPEJXQZAKCBGMT"

    condition:
        $a or $b or $c
}
```
## References 
- [https://yara.readthedocs.io/](https://yara.readthedocs.io/)
- [https://github.com/VirusTotal/yara](https://github.com/VirusTotal/yara)

### Writing rules
- [https://yara.readthedocs.io/en/stable/writingrules.html](https://yara.readthedocs.io/en/stable/writingrules.html)
- [https://github.com/Neo23x0/YARA-Style-Guide](https://github.com/Neo23x0/YARA-Style-Guide)
- [https://github.com/Neo23x0/signature-base/tree/master/yara](https://github.com/Neo23x0/signature-base/tree/master/yara)

- [https://yara.readthedocs.io/en/stable/modules/pe.html](https://yara.readthedocs.io/en/stable/modules/pe.html)
- [https://yara.readthedocs.io/en/stable/writingrules.html](https://yara.readthedocs.io/en/stable/writingrules.html)
- [https://github.com/Neo23x0/YARA-Style-Guide](https://github.com/Neo23x0/YARA-Style-Guide)
- [https://github.com/Neo23x0/signature-base/tree/master/yara](https://github.com/Neo23x0/signature-base/tree/master/yara)