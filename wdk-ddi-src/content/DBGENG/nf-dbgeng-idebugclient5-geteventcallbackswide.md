---
UID: NF.dbgeng.IDebugClient5.GetEventCallbacksWide
title: IDebugClient5::GetEventCallbacksWide
author: windows-driver-content
description: The GetEventCallbacksWide method returns the event callbacks object registered with this client.
old-location: debugger\geteventcallbackswide.htm
ms.assetid: 254eb89f-c330-4fca-8c58-6dbe56861743
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: debugger
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugClient5.GetEventCallbacksWide
req.alt-loc: dbgeng.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
ms.keywords: IDebugClient5, GetEventCallbacksWide, IDebugClient5::GetEventCallbacksWide
req.iface: IDebugClient5
---

# IDebugClient5::GetEventCallbacksWide method



## -description
<p>The <b>GetEventCallbacksWide</b> method returns the event callbacks object registered with this client.</p>


## -syntax

````
HRESULT GetEventCallbacksWide(
  [out] PDEBUG_EVENT_CALLBACKS_WIDE *Callbacks
);
````


## -parameters
<dl>

### -param <i>Callbacks</i> [out]

<dd>
<p>Receives an interface pointer to the event callbacks object registered with this client.</p>
</dd>
</dl>

## -returns
<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

## -remarks
<p>Each client can have at most one <a href="https://msdn.microsoft.com/library/windows/hardware/ff550550">IDebugEventCallbacks</a> or <b>IDebugEventCallbacksWide</b> object registered with it for receiving <a href="debugger.events#events#events">events</a>.</p>

<p>If no event callbacks object is registered with the client, the value of <i>Callbacks</i> will be set to <b>NULL</b>.</p>

<p>The <b>IDebugEventCallbacksWide</b> interface extends the COM interface <b>IUnknown</b>.  Before returning the <b>IDebugEventCallbacksWide</b> object specified by <i>Callbacks</i>, the engine calls its <b>IUnknown::AddRef</b> method.  When this object is no longer needed, its <b>IUnknown::Release</b> method should be called. </p>

<p>For more information about callbacks, see <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">Callbacks</a>.</p>

<p>Each client can have at most one <a href="https://msdn.microsoft.com/library/windows/hardware/ff550550">IDebugEventCallbacks</a> or <b>IDebugEventCallbacksWide</b> object registered with it for receiving <a href="debugger.events#events#events">events</a>.</p>

<p>If no event callbacks object is registered with the client, the value of <i>Callbacks</i> will be set to <b>NULL</b>.</p>

<p>The <b>IDebugEventCallbacksWide</b> interface extends the COM interface <b>IUnknown</b>.  Before returning the <b>IDebugEventCallbacksWide</b> object specified by <i>Callbacks</i>, the engine calls its <b>IUnknown::AddRef</b> method.  When this object is no longer needed, its <b>IUnknown::Release</b> method should be called. </p>

<p>For more information about callbacks, see <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">Callbacks</a>.</p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550550">IDebugEventCallbacks</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556671">SetEventCallbacks</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient5::GetEventCallbacksWide method%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>