---
UID: NF.wudfddi.IWDFRemoteTarget.GetState
title: IWDFRemoteTarget::GetState
author: windows-driver-content
description: The GetState method returns the current state of a remote I/O target.
old-location: wdf\iwdfremotetarget_getstate.htm
ms.assetid: 3918d764-c5bb-42b6-8b06-a2d544511a96
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: wdf
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.alt-api: IWDFRemoteTarget.GetState
req.alt-loc: WUDFx.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: <= DISPATCH_LEVEL
ms.keywords: IWDFRemoteTarget, GetState, IWDFRemoteTarget::GetState
req.iface: IWDFRemoteTarget
req.product: Windows 10 or later.
---

# IWDFRemoteTarget::GetState method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]</p>
<p>The <b>GetState</b> method returns the current state of a <a href="wdf.general_i_o_targets_in_umdf">remote I/O target</a>.</p>


## -syntax

````
WDF_IO_TARGET_STATE GetState();
````


## -parameters


## -returns
<p><b>GetState</b> returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552390">WDF_IO_TARGET_STATE</a>-typed value that identifies the state of the remote I/O target.</p>

<p><b>GetState</b> returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552390">WDF_IO_TARGET_STATE</a>-typed value that identifies the state of the remote I/O target.</p>

<p><b>GetState</b> returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552390">WDF_IO_TARGET_STATE</a>-typed value that identifies the state of the remote I/O target.</p>

## -remarks
<p>For more information about remote I/O target states, see <a href="wdf.controlling_a_general_i_o_target_s_state_in_umdf">Controlling a General I/O Target's State in UMDF</a>.</p>

<p>The following code example determines whether a remote I/O target is closed.</p>

<p>For more information about remote I/O target states, see <a href="wdf.controlling_a_general_i_o_target_s_state_in_umdf">Controlling a General I/O Target's State in UMDF</a>.</p>

<p>The following code example determines whether a remote I/O target is closed.</p>

<p>For more information about remote I/O target states, see <a href="wdf.controlling_a_general_i_o_target_s_state_in_umdf">Controlling a General I/O Target's State in UMDF</a>.</p>

<p>The following code example determines whether a remote I/O target is closed.</p>

<p>For more information about remote I/O target states, see <a href="wdf.controlling_a_general_i_o_target_s_state_in_umdf">Controlling a General I/O Target's State in UMDF</a>.</p>

<p>The following code example determines whether a remote I/O target is closed.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>End of support</p>
</th>
<td width="70%">
<p>Unavailable in UMDF 2.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>1.9</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wudfddi.h (include Wudfddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>WUDFx.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560247">IWDFRemoteTarget</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552390">WDF_IO_TARGET_STATE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFRemoteTarget::GetState method%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>