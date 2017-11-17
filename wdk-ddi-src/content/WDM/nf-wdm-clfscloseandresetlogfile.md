---
UID: NF.wdm.ClfsCloseAndResetLogFile
title: ClfsCloseAndResetLogFile
author: windows-driver-content
description: The ClfsCloseAndResetLogFile routine releases all references to a specified log file object and marks its associated stream for reset.
old-location: kernel\clfscloseandresetlogfile.htm
ms.assetid: 5b52a012-1e3e-4d1f-8780-a7015b2f3c5f
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: kernel
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ClfsCloseAndResetLogFile
req.alt-loc: Clfs.sys,Ext-MS-Win-fs-clfs-l1-1-0.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: <= APC_LEVEL
ms.keywords: ClfsCloseAndResetLogFile
req.iface: 
req.product: Windows 10 or later.
---

# ClfsCloseAndResetLogFile function



## -description
<p>The <b>ClfsCloseAndResetLogFile</b> routine releases all references to a specified log file object and marks its associated stream for reset.</p>


## -syntax

````
NTSTATUS ClfsCloseAndResetLogFile(
  _In_ PLOG_FILE_OBJECT plfoLog
);
````


## -parameters
<dl>

### -param <i>plfoLog</i> [in]

<dd>
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554316">LOG_FILE_OBJECT</a> structure for which references will be released. The caller previously obtained this pointer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff540792">ClfsCreateLogFile</a>.</p>
</dd>
</dl>

## -returns
<p><b>ClfsCloseAndResetLogFile</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.</p>

## -remarks
<p><b>ClfsCloseAndResetLogFile</b> releases all references, acquired by CLFS, to the specified log file object. Typically, the client will not have acquired any additional references to the log file object. However, if the client has obtained additional refereces, it is the client's responsibility to release them.</p>

<p><b>ClfsCloseAndResetLogFile</b> causes the specified log file object's reference count to drop to zero, at which time the log file object is closed (that is, its memory is deallocated). The stream represented by the log file object might not be reset, however, because there could be other log file objects that represent the same stream. The stream is reset after all log file objects that represent the stream are closed (for example by calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff540789">ClfsCloseLogFileObject</a>).</p>

<p>A reset stream is like a newly created stream that has never had any records written to it.</p>

<p>On return from this routine, <i>plfoLog</i> is invalid.</p>

<p>You can call <b>ClfsCloseAndResetLogFile</b> at most 124 times for a given stream.</p>

<p>For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. </p>

<p><b>ClfsCloseAndResetLogFile</b> releases all references, acquired by CLFS, to the specified log file object. Typically, the client will not have acquired any additional references to the log file object. However, if the client has obtained additional refereces, it is the client's responsibility to release them.</p>

<p><b>ClfsCloseAndResetLogFile</b> causes the specified log file object's reference count to drop to zero, at which time the log file object is closed (that is, its memory is deallocated). The stream represented by the log file object might not be reset, however, because there could be other log file objects that represent the same stream. The stream is reset after all log file objects that represent the stream are closed (for example by calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff540789">ClfsCloseLogFileObject</a>).</p>

<p>A reset stream is like a newly created stream that has never had any records written to it.</p>

<p>On return from this routine, <i>plfoLog</i> is invalid.</p>

<p>You can call <b>ClfsCloseAndResetLogFile</b> at most 124 times for a given stream.</p>

<p>For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. </p>

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
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Clfs.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Clfs.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= APC_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540789">ClfsCloseLogFileObject</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541529">ClfsDeleteLogByPointer</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541539">ClfsDeleteLogFile</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsCloseAndResetLogFile routine%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>