---
UID: NF.wdm.ClfsDeleteLogFile
title: ClfsDeleteLogFile
author: windows-driver-content
description: The ClfsDeleteLogFile routine marks a CLFS stream for deletion.
old-location: kernel\clfsdeletelogfile.htm
ms.assetid: a8c90199-e938-45bb-9356-48591e127eed
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
req.alt-api: ClfsDeleteLogFile
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
ms.keywords: ClfsDeleteLogFile
req.iface: 
req.product: Windows 10 or later.
---

# ClfsDeleteLogFile function



## -description
<p>The <b>ClfsDeleteLogFile</b> routine marks a CLFS stream for deletion.</p>


## -syntax

````
NTSTATUS ClfsDeleteLogFile(
  _In_     PUNICODE_STRING puszLogFileName,
  _In_opt_ PVOID           psdLogFile,
  _In_     ULONG           fLogOptionFlag,
  _In_opt_ PVOID           pvContext,
  _In_     ULONG           cbContext
);
````


## -parameters
<dl>

### -param <i>puszLogFileName</i> [in]

<dd>
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that supplies the name of the CLFS stream to be deleted. </p>
<p>If the stream to be deleted is the only stream of a dedicated log, the name has the form log:<i>physical log name</i>, where <i>physical log name</i> is the path name of the physical log on the underlying file system.</p>
<p>If the stream to be deleted is one of the streams of a multiplexed log, the name has the form log:<i>physical log name</i>::<i>stream name</i>, where <i>physical log name</i> is the path name of  the physical log on the underlying file system and <i>stream name</i> is the unique name of the stream to be deleted.</p>
</dd>

### -param <i>psdLogFile</i> [in, optional]

<dd>
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a> structure that supplies the security attributes for accessing the stream. This parameter can be <b>NULL</b>.</p>
</dd>

### -param <i>fLogOptionFlag</i> [in]

<dd>
<p>A value that indicates the relationship between CLFS and the component that is deleting the log. For a list of possible values, see the description of the <i>fLogOptionFlag</i> parameter of the <b>ClfsCreateLogFile</b> routine.</p>
</dd>

### -param <i>pvContext</i> [in, optional]

<dd>
<p>A pointer to a context. The way the context is interpreted depends on the value passed in <i>fLogOptionFlag</i>.</p>
</dd>

### -param <i>cbContext</i> [in]

<dd>
<p>The size, in bytes, of the context pointed to by <i>pvContex</i>t. If <i>pvContext</i> is not <b>NULL</b>, this parameter must be greater than zero.</p>
</dd>
</dl>

## -returns
<p><b>ClfsDeleteLogFile</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.</p>

## -remarks
<p><b>ClfsDeleteLogFile</b> marks a stream for deletion but does not close any log file objects that are currently open. To close a log file object, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff540789">ClfsCloseLogFileObject</a>. A stream marked for deletion is deleted after all log file objects associated with the stream are closed.</p>

<p>A CLFS stream marked for deletion will refuse subsequent requests to open the stream.</p>

<p>The name of a physical CLFS log does not include the .blf extension.</p>

<p>For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. </p>

<p><b>ClfsDeleteLogFile</b> marks a stream for deletion but does not close any log file objects that are currently open. To close a log file object, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff540789">ClfsCloseLogFileObject</a>. A stream marked for deletion is deleted after all log file objects associated with the stream are closed.</p>

<p>A CLFS stream marked for deletion will refuse subsequent requests to open the stream.</p>

<p>The name of a physical CLFS log does not include the .blf extension.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540792">ClfsCreateLogFile</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541529">ClfsDeleteLogByPointer</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540789">ClfsCloseLogFileObject</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540787">ClfsCloseAndResetLogFile</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsDeleteLogFile routine%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>