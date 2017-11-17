---
UID: NC.hdaudio.PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK
title: PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK
author: windows-driver-content
description: HDAudio codec unsolicited response callback function. PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK is used by the PREGISTER_EVENT_CALLBACK callback function.
old-location: audio\phdaudio_unsolicited_response_callback.htm
ms.assetid: B98F669D-D0DE-4FF2-903C-D51E0FEEE840
ms.author: windowsdriverdev
ms.date: 10/30/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: audio
req.header: hdaudio.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HDAudioUnsolicitedResponseCallback
req.alt-loc: Hdaudio.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
ms.keywords: SM_SetRNIDMgmtInfo_OUT, SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
req.iface: 
---

# PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK callback



## -description
<p>HDAudio codec unsolicited response callback function. <b>PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK</b> is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537803">PREGISTER_EVENT_CALLBACK</a> callback function. </p>


## -prototype

````
PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK HDAudioUnsolicitedResponseCallback;

VOID HDAudioUnsolicitedResponseCallback(
   HDAUDIO_CODEC_RESPONSE HDAudioCodecResponse,
   PVOID                  Context
)
{ ... }

typedef PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK HDAudioUnsolicitedResponseCallback;
````


## -parameters
<dl>

### -param <i>HDAudioCodecResponse</i> 

<dd>
<p>This is a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff536422">HDAUDIO_CODEC_RESPONSE</a> that specifies the codec's response to the command. This structure is passed by value.  </p>
</dd>

### -param <i>Context</i> 

<dd>
<p>This is the callbackContext value that was passed previously to <a href="https://msdn.microsoft.com/library/windows/hardware/ff537803">PREGISTER_EVENT_CALLBACK</a>.</p>
</dd>
</dl>

## -returns
<p>Void</p>

## -remarks
<p>The HD Audio bus driver calls the callback routine at PASSIVE_LEVEL.</p>

<p>The HD Audio bus driver calls the callback routine at PASSIVE_LEVEL.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Hdaudio.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>