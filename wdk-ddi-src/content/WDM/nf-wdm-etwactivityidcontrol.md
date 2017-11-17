---
UID: NF.wdm.EtwActivityIdControl
title: EtwActivityIdControl
author: windows-driver-content
description: The EtwActivityIdControl function creates, queries, and sets the current activity identifier.
old-location: devtest\etwactivityidcontrol.htm
ms.assetid: dd2e1558-db5d-4d48-a55e-fbdf2838ec55
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: devtest
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: EtwActivityIdControl
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Comments section
ms.keywords: EtwActivityIdControl
req.iface: 
req.product: Windows 10 or later.
---

# EtwActivityIdControl function



## -description
<p>The <b>EtwActivityIdControl</b> function creates, queries, and sets the current activity identifier. </p>


## -syntax

````
NTSTATUS EtwActivityIdControl(
  _In_    ULONG  ControlCode,
  _Inout_ LPGUID ActivityId
);
````


## -parameters
<dl>

### -param <i>ControlCode</i> [in]

<dd>
<p>The <i>ControlCode</i> parameter can be one of the following defined values.</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="EVENT_ACTIVITY_CTRL_GET_ID"></a><a id="event_activity_ctrl_get_id"></a><dl>

### -param <b>EVENT_ACTIVITY_CTRL_GET_ID</b>

</dl>
</td>
<td width="60%">
<p>Returns the current thread's activity identifier in the <i>ActivityId</i> parameter.  </p>
</td>
</tr>
<tr>
<td width="40%"><a id="EVENT_ACTIVITY_CTRL_SET_ID"></a><a id="event_activity_ctrl_set_id"></a><dl>

### -param <b>EVENT_ACTIVITY_CTRL_SET_ID</b>

</dl>
</td>
<td width="60%">
<p>Sets the current thread's activity identifier to the value specified in <i>ActivityId</i>. Note that the <i>ActivityId</i> you pass to this function
            does not necessarily have to be one created by EVENT_ACTIVITY_CTRL_CREATE_ID or EVENT_ACTIVITY_CTRL_CREATE_SET_ID control code.
            You can use any value that fits inside a GUID, including any available
            local value that would serve your need for
            some type of activity identifier.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="EVENT_ACTIVITY_CTRL_CREATE_ID"></a><a id="event_activity_ctrl_create_id"></a><dl>

### -param <b>EVENT_ACTIVITY_CTRL_CREATE_ID</b>

</dl>
</td>
<td width="60%">
<p>Creates a new identifier and sets the <i>ActivityId</i> parameter to the value of the new identifier.  </p>
</td>
</tr>
<tr>
<td width="40%"><a id="EVENT_ACTIVITY_CTRL_GET_SET_ID"></a><a id="event_activity_ctrl_get_set_id"></a><dl>

### -param <b>EVENT_ACTIVITY_CTRL_GET_SET_ID</b>

</dl>
</td>
<td width="60%">
<p>Sets the current thread's activity identifier to the value specified in <i>ActivityId</i>, and then returns <i>ActivityId</i> with the value of the thread's activity identifier prior to the function call.  </p>
</td>
</tr>
<tr>
<td width="40%"><a id="EVENT_ACTIVITY_CTRL_CREATE_SET_ID"></a><a id="event_activity_ctrl_create_set_id"></a><dl>

### -param <b>EVENT_ACTIVITY_CTRL_CREATE_SET_ID</b>

</dl>
</td>
<td width="60%">
<p>Copies the current thread's activity identifier. Creates a new identifier and sets the current thread's   activity identifier to the new value. Returns <i>ActivityId</i> with the value of the thread's activity identifier prior to the function call. </p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -param <i>ActivityId</i> [in, out]

<dd>
<p>The identifier that indicates the activity associated with the event. The <i>ActivityId</i> parameter provides a way to group related events and is used in end-to-end tracing.</p>
</dd>
</dl>

## -returns
<p><b>EtwActivityIdControl</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value.</p>

## -remarks
<p>Activity identifiers provide a method of linking separate events in a common thread of computation. An <i>activity</i> is a work item performed by an application and or a driver. The concept of activity is a core component in end-to-end tracing.</p>

<p>Callers of <b>EtwActivityIdControl</b> must be running at IRQL &lt; DISPATCH_LEVEL, unless the <i>ControlCode</i> is EVENT_ACTIVITY_CTRL_CREATE_ID, in which case the function can be called at any IRQL.</p>

<p>Use the <a href="https://msdn.microsoft.com/library/windows/hardware/dn268326">EtwActivityIdControlKernel</a> function to  query or set  activity identifiers  kernel threads. </p>

<p>Activity identifiers provide a method of linking separate events in a common thread of computation. An <i>activity</i> is a work item performed by an application and or a driver. The concept of activity is a core component in end-to-end tracing.</p>

<p>Callers of <b>EtwActivityIdControl</b> must be running at IRQL &lt; DISPATCH_LEVEL, unless the <i>ControlCode</i> is EVENT_ACTIVITY_CTRL_CREATE_ID, in which case the function can be called at any IRQL.</p>

<p>Use the <a href="https://msdn.microsoft.com/library/windows/hardware/dn268326">EtwActivityIdControlKernel</a> function to  query or set  activity identifiers  kernel threads. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of Windows.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h or Ntddk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>See Comments section</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn268326">EtwActivityIdControlKernel</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20EtwActivityIdControl function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>