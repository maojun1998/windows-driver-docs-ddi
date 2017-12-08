---
UID: NC.bthddi.PFNSCO_INDICATION_CALLBACK
title: PFNSCO_INDICATION_CALLBACK
author: windows-driver-content
description: Profile drivers implement a SCO callback function to provide the Bluetooth driver stack with a mechanism to notify the profile driver about incoming SCO connection requests from remote devices, and any changes to the status of a currently open SCO connection.
old-location: bltooth\sco_callback_function.htm
old-project: bltooth
ms.assetid: abc9fc88-6852-4bfb-8271-7a73a508c397
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: _MPEG2_TRANSPORT_STRIDE, MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Desktop
req.target-min-winverclnt: Versions: Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SCOIndicationCallback
req.alt-loc: bthddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
---

# PFNSCO_INDICATION_CALLBACK callback



## -description
Profile drivers implement a SCO callback function to provide the Bluetooth driver stack with a
  mechanism to notify the profile driver about incoming SCO connection requests from remote devices, and any
  changes to the status of a currently open SCO connection.


## -prototype

````
PFNSCO_INDICATION_CALLBACK SCOIndicationCallback;

void SCOIndicationCallback(
  _In_ PVOID                      Context,
  _In_ SCO_INDICATION_CODE        Indication,
  _In_ PSCO_INDICATION_PARAMETERS Parameters
)
{ ... }
````


## -parameters

### -param Context [in]

For incoming remote connection request indications, this is the context specified by the profile
     driver in the 
     <b>IndicationCallbackContext</b> member of the 
     <a href="..\bthddi\ns-bthddi-_brb_sco_register_server.md">_BRB_SCO_REGISTER_SERVER</a> structure
     when the profile driver registered the callback function. For changes to existing SCO connections, this
     is the 
     <b>CallbackContext</b> member specified by the profile driver when it built and sent a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536626">BRB_SCO_OPEN_CHANNEL</a> BRB.

### -param Indication [in]

A 
     <a href="bltooth.sco_indication_code">SCO_INDICATION_CODE</a> value that indicates
     the type of SCO event.

### -param Parameters [in]

A 
     <a href="bltooth.sco_indication_parameters">
     SCO_INDICATION_PARAMETERS</a> structure that contains parameter information based on the value passed
     to the 
     <i>Indication</i> parameter.

## -returns
None

## -remarks
The 
    <b>BtAddress</b> member found in the SCO_INDICATION_PARAMETERS structure passed in the 
    <i>Parameters</i> parameter indicates the Bluetooth address of the remote device.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Versions: Supported in Windows Vista, and later.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Bthddi.h (include Bthddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback
   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access
   paged memory)
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\bthddi\ns-bthddi-_brb_sco_register_server.md">_BRB_SCO_REGISTER_SERVER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536626">BRB_SCO_OPEN_CHANNEL</a>
</dt>
<dt>
<a href="bltooth.sco_indication_code">SCO_INDICATION_CODE</a>
</dt>
<dt>
<a href="bltooth.sco_indication_parameters">SCO_INDICATION_PARAMETERS</a>
</dt>
<dt>
<a href="..\bthioctl\ni-bthioctl-ioctl_internal_bth_submit_brb.md">IOCTL_INTERNAL_BTH_SUBMIT_BRB</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20PFNSCO_INDICATION_CALLBACK callback function%20 RELEASE:%20(11/27/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>