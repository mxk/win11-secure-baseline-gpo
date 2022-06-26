Windows 11 Secure Baseline GPO
==============================

A secure baseline group policy based on [win10-secure-baseline-gpo][win10].
Currently, it does not include Server-specific settings.

[win10]: https://github.com/mxk/win10-secure-baseline-gpo

Installation
------------

*TODO*

Required ADMX templates
-----------------------

`PolicyDefinitions` directory contains templates from the following sources:

1. Windows 11 May 2022 ISO
2. Windows 11 Enterprise 21H2 (22000.739)
3. [Windows 11 Security Baseline - FINAL][SCT]
4. [Windows Restricted Traffic Limited Functionality Baseline - Windows 11 21H2][RTLFB]
5. [Microsoft Edge (103.0.1264.37)][Edge]

[SCT]: https://www.microsoft.com/en-us/download/details.aspx?id=55319
[RTLFB]: https://docs.microsoft.com/en-us/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services
[Edge]: https://www.microsoft.com/en-us/edge/business/download

When an update is released, the entire `PolicyDefinitions` directory should be
rebuilt by copying templates over in the listed order. Copying updated ADMX/ADML
files without removing old ones first may cause problems.

To extract `PolicyDefinitions` from a Windows ISO:

1. Mount the ISO file.
2. Open `sources\install.wim` with 7-Zip.
3. Check `[1].xml` for the appropriate version (though they should all be the same).
4. Extract `\<N>\Windows\PolicyDefinitions`.
