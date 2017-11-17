---
UID: NF.ndis.NdisWriteEventLogEntry
title: NdisWriteEventLogEntry
author: windows-driver-content
description: NdisWriteEventLogEntry logs an event to the Win32 event log.
old-location: netvista\ndiswriteeventlogentry.htm
ms.assetid: 1f3fbcf1-e6f4-4117-a795-f4b14ef9fc96
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   NdisWriteEventLogEntry (NDIS
   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   NdisWriteEventLogEntry (NDIS
   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisWriteEventLogEntry
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
ms.keywords: NdisWriteEventLogEntry
req.iface: 
---

# NdisWriteEventLogEntry function



## -description
<p><b>NdisWriteEventLogEntry</b> logs an event to the Win32 event log.</p>


## -syntax

````
NDIS_STATUS NdisWriteEventLogEntry(
  _In_     PVOID       LogHandle,
  _In_     NDIS_STATUS EventCode,
  _In_     ULONG       UniqueEventValue,
  _In_     USHORT      NumStrings,
  _In_opt_ PVOID       StringsList,
  _In_     ULONG       DataSize,
  _In_opt_ PVOID       Data
);
````


## -parameters
<dl>

### -param <i>LogHandle</i> [in]

<dd>
<p>Pointer to the driver object of the protocol that is logging this event.</p>
</dd>

### -param <i>EventCode</i> [in]

<dd>
<p>Specifies the NDIS_STATUS_<i>XXX</i> code describing the event.</p>
</dd>

### -param <i>UniqueEventValue</i> [in]

<dd>
<p>Identifies this instance of the error message.</p>
</dd>

### -param <i>NumStrings</i> [in]

<dd>
<p>Specifies the number of pointers to Unicode strings in the optional 
     <i>StringsList</i>. If 
     <i>StringsList</i> is <b>NULL</b>, 
     <i>NumStrings</i> must be zero.</p>
</dd>

### -param <i>StringsList</i> [in, optional]

<dd>
<p>Either <b>NULL</b> or points to buffered Unicode strings. These strings, which describe the event, are
     inserted into the Win32 event log and can be examined with the Win32 event viewer. Each string must be a
     NUL-terminated Unicode string.</p>
</dd>

### -param <i>DataSize</i> [in]

<dd>
<p>Specifies the number of bytes in the buffer for the binary data at 
     <i>Data</i> . If 
     <i>Data</i> is <b>NULL</b>, 
     <i>DataSize</i> must be zero.</p>
</dd>

### -param <i>Data</i> [in, optional]

<dd>
<p>Either <b>NULL</b> or points to buffered binary dump data that is useful for understanding the event.
     This data can be examined with the Win32 event viewer.</p>
</dd>
</dl>

## -returns
<p><b>NdisWriteEventLogEntry</b> can return one of the following values:</p><dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><p>The event was successfully logged.</p><dl>
<dt><b>NDIS_STATUS_BUFFER_TOO_SHORT</b></dt>
</dl><p>The optionally supplied Unicode strings and binary dump data exceed the maximum-allowed size
       (MAX_EVENT_LOG_DATA_SIZE).</p><dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl><p>NDIS was unable to allocate memory for the I/O error log record.</p>

<p> </p>

## -remarks
<p><b>NdisWriteEventLogEntry</b> allocates an I/O error log record, fills in the record with the supplied
    information about the event, and then writes the record to the I/O error log file. A user can view the
    logged event, including an optional description of the event and/or optional binary dump data, with the
    Win32 event viewer.</p>

<p>The NT error-logging thread uses any strings supplied in the optional 
    <i>StringsList</i> to fill in messages written into the Win32 event log. Each string must be a
    NUL-terminated Unicode string. The I/O manager assumes that the initial string is either the name of the
    driver reporting the error or the name of the device that caused the error.</p>

<p>The Unicode strings supplied by the caller should be read from the registry or should be
    language-independent (that is, the strings should be the same in any language -- for example, the string
    could be a file name).</p>

<p>Caller-supplied dump data can be any binary data (such as register values) that is useful in
    understanding the event. The caller does not have to pad the binary data. If necessary, 
    <b>NdisWriteEventLogEntry</b> pads the binary dump data so that the final data size is a multiple integral
    of 
    <b>sizeof</b>(ULONG).</p>

<p>The system limits the total size of the optional data supplied to 
    <b>NdisWriteEventLogEntry</b>. The combined size of the strings list and the (possibly padded) binary
    dump must be less than or equal to MAX_EVENT_LOG_DATA_SIZE.</p>

<p><b>NdisWriteEventLogEntry</b> is called only by protocol drivers. Miniport drivers should call 
    <b>NdisWriteErrorLogEntry</b> to log events and errors.</p>

<p><b>NdisWriteEventLogEntry</b> allocates an I/O error log record, fills in the record with the supplied
    information about the event, and then writes the record to the I/O error log file. A user can view the
    logged event, including an optional description of the event and/or optional binary dump data, with the
    Win32 event viewer.</p>

<p>The NT error-logging thread uses any strings supplied in the optional 
    <i>StringsList</i> to fill in messages written into the Win32 event log. Each string must be a
    NUL-terminated Unicode string. The I/O manager assumes that the initial string is either the name of the
    driver reporting the error or the name of the device that caused the error.</p>

<p>The Unicode strings supplied by the caller should be read from the registry or should be
    language-independent (that is, the strings should be the same in any language -- for example, the string
    could be a file name).</p>

<p>Caller-supplied dump data can be any binary data (such as register values) that is useful in
    understanding the event. The caller does not have to pad the binary data. If necessary, 
    <b>NdisWriteEventLogEntry</b> pads the binary dump data so that the final data size is a multiple integral
    of 
    <b>sizeof</b>(ULONG).</p>

<p>The system limits the total size of the optional data supplied to 
    <b>NdisWriteEventLogEntry</b>. The combined size of the strings list and the (possibly padded) binary
    dump must be less than or equal to MAX_EVENT_LOG_DATA_SIZE.</p>

<p><b>NdisWriteEventLogEntry</b> is called only by protocol drivers. Miniport drivers should call 
    <b>NdisWriteErrorLogEntry</b> to log events and errors.</p>

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
<p>Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/f8da3fa3-caa1-4306-8556-e7cd0d7e8c15">NdisWriteEventLogEntry (NDIS
   5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisWriteEventLogEntry (NDIS
   5.1)</b>) in Windows XP.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547982">Irql_Miscellaneous_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/15f82163-a1b5-4cef-a53e-8a97adb2cd92">MiniportResetEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563672">NdisMSetMiniportAttributes</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564663">NdisWriteErrorLogEntry</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisWriteEventLogEntry function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>