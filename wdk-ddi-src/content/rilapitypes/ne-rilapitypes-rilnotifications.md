---
UID : NE:rilapitypes.RILNOTIFICATIONS
title : RILNOTIFICATIONS
author : windows-driver-content
description : This enumeration describes RILNOTIFICATIONS.
old-location : netvista\rilnotifications.htm
old-project : netvista
ms.assetid : a1737655-856d-430e-bce8-ef6c9b66ee54
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILNOTIFICATIONS, RILNOTIFICATIONS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : rilapitypes.h
req.include-header : Rilapitypes.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : RILNOTIFICATIONS
req.alt-loc : rilapitypes.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : RILNOTIFICATIONS
req.product : Windows 10 or later.
---

# RILNOTIFICATIONS Enumeration


## Syntax
````
enum RILNOTIFICATIONS  {
  RIL_NOTIFY_OEM_MAX                        = 0x000000FF | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_RADIOEQUIPMENTSTATECHANGED     = 0x00000100 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_RADIOPRESENCECHANGED           = 0x00000101 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_UICCFILE_DATACHANGE            = 0x00000102 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_UICCAPP_DATACHANGE             = 0x00000103 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_SLOTINFOCHANGED                = 0x00000104 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_CARDAPPREMOVED                 = 0x00000105 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_CARDAPPADDED                   = 0x00000106 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_UICCLOCKSTATUS                 = 0x00000107 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_UICCAPPPERSOCHECKSTATUS        = 0x00000108 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_PHONEBOOKENTRYDELETED          = 0x00000109 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_PHONEBOOKENTRYSTORED           = 0x0000010A | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_PHONEBOOKREADYSTATE            = 0x0000010B | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_EMERGENCYNUMBERLISTCHANGED     = 0x0000010C | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_REGSTATUSCHANGED               = 0x0000010D | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_LOCATIONUPDATE                 = 0x0000010E | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_NETWORKCODECHANGED             = 0x0000010F | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_PROVISION_STATUS               = 0x00000110 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_SYSTEMPREFSCHANGED             = 0x00000111 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_EXECUTORSTATE                  = 0x00000112 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_MANAGED_ROAMING                = 0x00000113 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_SIGNALQUALITY                  = 0x00000114 | RIL_NCLASS_NOTIFICATIONS, 
   RIL_NOTIFY_NITZ                          = 0x00000115 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_UICCTOOLKITCMD                 = 0x00000116 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_CALLMODIFICATIONINFO           = 0x00000117 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_CALLPROGRESSINFO               = 0x00000118 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_EMERGENCYMODEENTERED           = 0x00000119 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_EMERGENCYMODEEXITED            = 0x0000011A | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_CALLWAITING                    = 0x0000011B | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_DIALEDID                       = 0x0000011C | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_DISPLAY                        = 0x0000011D | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_SUPSVCINFO                     = 0x0000011E | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_SUPSERVICEDATA                 = 0x0000011F | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_UNSOLICITEDSS                  = 0x00000120 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_LINECONTROL                    = 0x00000121 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_MESSAGE                        = 0x00000122 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_MESSAGE_IN_UICC                = 0x00000123 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_IMSSTATUS                      = 0x00000124 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_ADDITIONALNUMBERSTRINGUPDATED  = 0x00000125 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_SUPSERVICEDATATERMINATED       = 0x00000126 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_CLEARIDLEMODETEXT              = 0x00000127 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_MESSAGE_STORAGE_FULL           = 0x00000128 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_TONESIGNAL                     = 0x00000129 | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_FORWARDSTARTDTMF               = 0x0000012A | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_FORWARDSTOPDTMF                = 0x0000012B | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_FORWARDBURSTDTMF               = 0x0000012C | RIL_NCLASS_NOTIFICATIONS, 
  RIL_NOTIFY_COUNT                          = 0x0000012D | RIL_NCLASS_NOTIFICATIONS 

};
````

## Constants

<table>

<tr>
<td>RIL_NOTIFY_ADDITIONALNUMBERSTRINGUPDATED</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_CALLMODIFICATIONINFO</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_CALLPROGRESSINFO</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_CALLWAITING</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_CARDAPPADDED</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_CARDAPPREMOVED</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_CLEARIDLEMODETEXT</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_COUNT</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_DIALEDID</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_DISPLAY</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_EMERGENCYMODEENTERED</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_EMERGENCYMODEEXITED</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_EMERGENCYNUMBERLISTCHANGED</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_EXECUTORSTATE</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_FORWARDBURSTDTMF</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_FORWARDSTARTDTMF</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_FORWARDSTOPDTMF</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_IMSSTATUS</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_LINECONTROL</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_LOCATIONUPDATE</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_MANAGED_ROAMING</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_MESSAGE</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_MESSAGE_IN_UICC</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_MESSAGE_STORAGE_FULL</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_NETWORKCODECHANGED</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_OEM_MAX</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_PHONEBOOKENTRYDELETED</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_PHONEBOOKENTRYSTORED</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_PHONEBOOKREADYSTATE</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_PROVISION_STATUS</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_RADIOEQUIPMENTSTATECHANGED</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_RADIOPRESENCECHANGED</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_REGSTATUSCHANGED</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_SIGNALQUALITY</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_SLOTINFOCHANGED</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_SUPSERVICEDATA</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_SUPSERVICEDATATERMINATED</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_SUPSVCINFO</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_SYSTEMPREFSCHANGED</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_TONESIGNAL</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_UICCAPP_DATACHANGE</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_UICCAPPPERSOCHECKSTATUS</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_UICCFILE_DATACHANGE</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_UICCLOCKSTATUS</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_UICCTOOLKITCMD</td>
<td></td>
</tr>

<tr>
<td>RIL_NOTIFY_UNSOLICITEDSS</td>
<td></td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h (include Rilapitypes.h) |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILNOTIFICATIONS enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>