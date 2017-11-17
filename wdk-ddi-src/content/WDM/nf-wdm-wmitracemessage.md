---
UID: NF.wdm.WmiTraceMessage
title: WmiTraceMessage
author: windows-driver-content
description: The WmiTraceMessage routine adds a message to the output log of a WPP software tracing session.
old-location: kernel\wmitracemessage.htm
ms.assetid: 045c45fe-c971-4d41-a43d-415c2a4d464b
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: kernel
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WmiTraceMessage
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
req.irql: See Remarks section.
ms.keywords: WmiTraceMessage
req.iface: 
req.product: Windows 10 or later.
---

# WmiTraceMessage function



## -description
<p>The <b>WmiTraceMessage</b> routine adds a message to the output log of a <a href="NULL">WPP software tracing</a> session.</p>


## -syntax

````
NTSTATUS WmiTraceMessage(
  _In_ TRACEHANDLE LoggerHandle,
  _In_ ULONG       MessageFlags,
  _In_ LPCGUID     MessageGuid,
  _In_ USHORT      MessageNumber,
  _In_             ...
);
````


## -parameters
<dl>

### -param <i>LoggerHandle</i> [in]

<dd>
<p>Specifies a trace handle for a software tracing session.</p>
</dd>

### -param <i>MessageFlags</i> [in]

<dd>
<p>Specifies a bitwise OR of one or more message flags. See the Remarks section for details.</p>
</dd>

### -param <i>MessageGuid</i> [in]

<dd>
<p>Specifies a GUID that identifies the class of software trace messages.</p>
</dd>

### -param <i>MessageNumber</i> [in]

<dd>
<p>Identifies the message subtype. The meaning of subtypes is specific to the software trace class and the provider.</p>
</dd>

### -param <i>...</i> [in]

<dd>
<p>Provides a required list of message parameters that specify a set of message parts. The parameters are organized as a sequence of parameter pairs, where each pair specifies one part of the complete message. Each parameter pair consists of a PVOID pointer to data, followed immediately by a ULONG value that specifies the length of the data. The parameter list must be terminated by a <b>NULL</b> PVOID pointer followed by a ULONG(0).</p>
</dd>
</dl>

## -returns
<p><b>WmiTraceMessage</b> returns one of the following values:</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The operation completed successfully.</p><dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl><p><i>LoggerHandle</i> is not a valid software trace handle.</p><dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl><p>There is insufficient buffer memory to log the message. See the Remarks section.</p><dl>
<dt><b>Other NTSTATUS value</b></dt>
</dl><p>An internal error occurred.</p>

<p> </p>

## -remarks
<p>A caller can use <b>WmiTraceMessage</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff566340">WmiTraceMessageVa</a> to add a message to the output log of a WPP software tracing session. <b>WmiTraceMessage</b> simplifies a caller's code by handling the variable list mechanism before calling <b>WmiTraceMessageVa</b>.</p>

<p>A caller can set the following message flags:</p>

<p>TRACE_MESSAGE_SEQUENCE</p>

<p>Include a sequence number in the message. Message sequencing can only be used if it is set for the software tracing session specified by <i>LoggerHandle</i>.</p>

<p>TRACE_MESSAGE_GUID</p>

<p><i>MessageGuid</i> specifies a GUID that identifies a software trace class. This flag must be set.</p>

<p>TRACE_MESSAGE_TIMESTAMP</p>

<p>Include a time stamp in the message.</p>

<p>TRACE_MESSAGE_PERFORMANCE_TIMESTAMP</p>

<p>This flag is not implemented and is <u>obsolete</u>. It must not be used. </p>

<p>TRACE_MESSAGE_SYSTEMINFO</p>

<p>Include the thread identifier (TID) and process identifier (PID) in the message.</p>

<p> </p>

<p>A message will not be logged if one of the following is true:</p>

<p>The total size, in bytes, of the message data and the message header is greater than the size of individual message buffers allocated for a software tracing session. (The maximum message header size is 48 bytes.)</p>

<p>All message buffers allocated to software tracing session are full. </p>

<p><b>WmiTraceMessage</b> runs at the IRQL of the caller.</p>

<p>A caller can use <b>WmiTraceMessage</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff566340">WmiTraceMessageVa</a> to add a message to the output log of a WPP software tracing session. <b>WmiTraceMessage</b> simplifies a caller's code by handling the variable list mechanism before calling <b>WmiTraceMessageVa</b>.</p>

<p>A caller can set the following message flags:</p>

<p>TRACE_MESSAGE_SEQUENCE</p>

<p>Include a sequence number in the message. Message sequencing can only be used if it is set for the software tracing session specified by <i>LoggerHandle</i>.</p>

<p>TRACE_MESSAGE_GUID</p>

<p><i>MessageGuid</i> specifies a GUID that identifies a software trace class. This flag must be set.</p>

<p>TRACE_MESSAGE_TIMESTAMP</p>

<p>Include a time stamp in the message.</p>

<p>TRACE_MESSAGE_PERFORMANCE_TIMESTAMP</p>

<p>This flag is not implemented and is <u>obsolete</u>. It must not be used. </p>

<p>TRACE_MESSAGE_SYSTEMINFO</p>

<p>Include the thread identifier (TID) and process identifier (PID) in the message.</p>

<p> </p>

<p>A message will not be logged if one of the following is true:</p>

<p>The total size, in bytes, of the message data and the message header is greater than the size of individual message buffers allocated for a software tracing session. (The maximum message header size is 48 bytes.)</p>

<p>All message buffers allocated to software tracing session are full. </p>

<p><b>WmiTraceMessage</b> runs at the IRQL of the caller.</p>

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
<p>Available in Windows XP and later versions of Windows. </p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
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
<p>See Remarks section.</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550520">IoWmiWriteEvent</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564750">TRACE_INFORMATION_CLASS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565807">WmiFireEvent</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565820">WmiQueryTraceInformation</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566340">WmiTraceMessageVa</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20WmiTraceMessage routine%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>