---
UID: NF.fltkernel.FltOplockKeysEqual
title: FltOplockKeysEqual
author: windows-driver-content
description: The FltOplockKeysEqual routine compares the opportunistic lock (oplock) keys that are stored in the file object extensions of two file objects.
old-location: ifsk\fltoplockkeysequal.htm
ms.assetid: 660aa6f2-03d8-44aa-b263-29a74c912668
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: ifsk
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: The FltOplockKeysEqual routine is available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltOplockKeysEqual
req.alt-loc: fltmgr.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
ms.keywords: FltOplockKeysEqual
req.iface: 
---

# FltOplockKeysEqual function



## -description
<p>The <b>FltOplockKeysEqual</b> routine compares the opportunistic lock (oplock) keys that are stored in the file object extensions of two file objects. </p>


## -syntax

````
BOOLEAN FltOplockKeysEqual(
  _In_opt_ PFILE_OBJECT Fo1,
  _In_opt_ PFILE_OBJECT Fo2
);
````


## -parameters
<dl>

### -param <i>Fo1</i> [in, optional]

<dd>
<p>A pointer to the first file object for the comparison. </p>
</dd>

### -param <i>Fo2</i> [in, optional]

<dd>
<p>A pointer to the second file object for the comparison. </p>
</dd>
</dl>

## -returns
<p>The <b>FltOplockKeysEqual</b> routine returns <b>TRUE</b> if the keys match or if the file object pointers are the same. <b>FltOplockKeysEqual</b> returns <b>FALSE</b> if the keys do not match, if either of the file objects is missing, or if either of the file objects does not have a key. </p>

## -remarks
<p>If no oplock key was provided when the file objects were created, the file objects are considered to match if the file object pointers are the same (that is, they are the same file object). If the file object pointers are different and either or both of the file objects do not have an associated oplock key, the file objects are considered to not match.</p>

<p>If no oplock key was provided when the file objects were created, the file objects are considered to match if the file object pointers are the same (that is, they are the same file object). If the file object pointers are different and either or both of the file objects do not have an associated oplock key, the file objects are considered to not match.</p>

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
<p>The <b>FltOplockKeysEqual</b> routine is available starting with Windows 8. </p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>FltMgr.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Fltmgr.sys</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547141">FsRtlOplockKeysEqual</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltOplockKeysEqual routine%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>