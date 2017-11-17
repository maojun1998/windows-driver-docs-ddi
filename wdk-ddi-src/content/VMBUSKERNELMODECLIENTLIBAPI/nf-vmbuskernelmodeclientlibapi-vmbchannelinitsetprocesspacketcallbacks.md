---
UID: NF.vmbuskernelmodeclientlibapi.VmbChannelInitSetProcessPacketCallbacks
title: VmbChannelInitSetProcessPacketCallbacks
author: windows-driver-content
description: The VmbChannelInitSetProcessPacketCallbacks function sets callback functions for packet processing.
old-location: netvista\vmbchannelinitsetprocesspacketcallbacks.htm
ms.assetid: 437DC9C5-CE73-45E8-AC4A-CFF9249809AD
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: netvista
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
req.alt-api: VmbChannelInitSetProcessPacketCallbacks
req.alt-loc: vmbkmcl.lib,vmbkmcl.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Vmbkmcl.lib
req.dll: 
req.irql: 
ms.keywords: VmbChannelInitSetProcessPacketCallbacks
req.iface: 
req.product: Windows 10 or later.
---

# VmbChannelInitSetProcessPacketCallbacks function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]</p>
<p>The <b>VmbChannelInitSetProcessPacketCallbacks</b>  function sets callback functions for packet processing. </p>


## -syntax

````
 VmbChannelInitSetProcessPacketCallbacks(
  _In_     VMBCHANNEL                          Channel,
  _In_     PFN_VMB_CHANNEL_PROCESS_PACKET      ProcessPacketCallback,
  _In_opt_ PFN_VMB_CHANNEL_PROCESSING_COMPLETE ProcessingCompleteCallback

);
````


## -parameters
<dl>

### -param <i>Channel</i> [in]

<dd>
<p>A handle for the channel.  </p>
</dd>

### -param <i>ProcessPacketCallback</i> [in]

<dd>
<p>A callback function to call when a packet is     ready for processing.</p>
</dd>

### -param <i>ProcessingCompleteCallback
</i> [in, optional]

<dd>
<p>
A callback function to call     when processing of a batch of packets has been completed.</p>
</dd>
</dl>

## -returns
<p> returns one of the following status values: </p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The function finished successfully.</p><dl>
<dt><b> STATUS_INVALID_PARAMETER_1</b></dt>
</dl><p>The <i>Channel</i> value was invalid or in an invalid state, such as Disabled.</p>

<p> </p>

## -remarks
<p>This function is only meaningful if Kernel Mode Client Library (KMCL) queue
management is not suppressed.  </p>

<p><b>ProcessPacketCallback</b> is invoked for every packet that
is received.  <a href="https://msdn.microsoft.com/E30A169E-0EC6-4128-B268-5FC1CD37A877">EvtVmbChannelProcessingComplete</a> will be invoked every time the ring buffer that contains incoming packets transitions from non-empty to empty. This happens
after the last invocation of <b>ProcessPacketCallback</b> in a single batch.</p>

<p>This function is only meaningful if Kernel Mode Client Library (KMCL) queue
management is not suppressed.  </p>

<p><b>ProcessPacketCallback</b> is invoked for every packet that
is received.  <a href="https://msdn.microsoft.com/E30A169E-0EC6-4128-B268-5FC1CD37A877">EvtVmbChannelProcessingComplete</a> will be invoked every time the ring buffer that contains incoming packets transitions from non-empty to empty. This happens
after the last invocation of <b>ProcessPacketCallback</b> in a single batch.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8.1</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012 R2</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.13</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>VmbusKernelModeClientLibApi.h (include VmbusKernelModeClientLibApi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Vmbkmcl.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/E30A169E-0EC6-4128-B268-5FC1CD37A877">EvtVmbChannelProcessingComplete</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/437DC9C5-CE73-45E8-AC4A-CFF9249809AD">ProcessPacketCallback</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbChannelInitSetProcessPacketCallbacks function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>