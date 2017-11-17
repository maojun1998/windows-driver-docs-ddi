---
UID: NS.wdm._FILE_BASIC_INFORMATION
title: FILE_BASIC_INFORMATION
author: windows-driver-content
description: The FILE_BASIC_INFORMATION structure is used as an argument to routines that query or set file information.
old-location: kernel\file_basic_information.htm
ms.assetid: 8f79a3cf-9bc7-4135-a90e-d9dce86cf5f6
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: kernel
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_BASIC_INFORMATION
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
ms.keywords: FILE_BASIC_INFORMATION, FILE_BASIC_INFORMATION, *PFILE_BASIC_INFORMATION
req.iface: 
req.product: Windows 10 or later.
---

# FILE_BASIC_INFORMATION structure



## -description
<p>The <b>FILE_BASIC_INFORMATION</b> structure is used as an argument to routines that query or set file information.</p>


## -syntax

````
typedef struct _FILE_BASIC_INFORMATION {
  LARGE_INTEGER CreationTime;
  LARGE_INTEGER LastAccessTime;
  LARGE_INTEGER LastWriteTime;
  LARGE_INTEGER ChangeTime;
  ULONG         FileAttributes;
} FILE_BASIC_INFORMATION, *PFILE_BASIC_INFORMATION;
````


## -struct-fields
<dl>

### -field <b>CreationTime</b>

<dd>
<p>Specifies the time that the file was created. </p>
</dd>

### -field <b>LastAccessTime</b>

<dd>
<p>Specifies the time that the file was last accessed. </p>
</dd>

### -field <b>LastWriteTime</b>

<dd>
<p>Specifies the time that the file was last written to. </p>
</dd>

### -field <b>ChangeTime</b>

<dd>
<p>Specifies the last time the file was changed. </p>
</dd>

### -field <b>FileAttributes</b>

<dd>
<p>Specifies one or more FILE_ATTRIBUTE_<i>XXX</i> flags. For descriptions of these flags, see the documentation for the <b>GetFileAttributes</b> function in the Microsoft Windows SDK.</p>
</dd>
</dl>

## -remarks
<p>The FILE_ATTRIBUTE_NORMAL flag cannot be set or returned in combination with any other attributes. All other <b>FileAttributes</b> values override this attribute.</p>

<p>Time values <b>CreationTime</b>, <b>LastAccessTime</b>, <b>LastWriteTime</b>, and <b>ChangeTime</b> are expressed in absolute system time format. Absolute system time is the number of 100-nanosecond intervals since the start of the year 1601 in the Gregorian calendar.</p>

<p>If you specify a value of zero for any of the <i>Xxx</i><b>Time</b> members of the <b>FILE_BASIC_INFORMATION</b> structure, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567096">ZwSetInformationFile</a> function keeps a file's current setting for that time.</p>

<p>The file system updates the values of the <b>LastAccessTime</b>, <b>LastWriteTime</b>, and <b>ChangeTime</b> members as appropriate after an I/O operation is performed on a file. However, a driver or application can request that the file system not update one or more of these members for I/O operations that are performed on the caller's file handle by setting the appropriate members to -1. The caller can set one, all, or any other combination of these three members to -1. Only the members that are set to -1 will be unaffected by I/O operations on the file handle; the other members will be updated as appropriate.</p>

<p>To set the members of this structure, the caller must have FILE_WRITE_ATTRIBUTES access to the file.</p>

## -requirements
<table>
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
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553068">KeQuerySystemTime</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567052">ZwQueryInformationFile</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567096">ZwSetInformationFile</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20FILE_BASIC_INFORMATION structure%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>