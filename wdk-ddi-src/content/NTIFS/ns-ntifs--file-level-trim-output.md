---
UID: NS.ntifs._FILE_LEVEL_TRIM_OUTPUT
title: FILE_LEVEL_TRIM_OUTPUT
author: windows-driver-content
description: The FILE_LEVEL_TRIM_OUTPUT structure contains the results of a trim operation performed by an FSCTL_FILE_LEVEL_TRIM request.
old-location: ifsk\file_level_trim_output.htm
ms.assetid: 28CCE967-E752-4E0E-94D9-3A4243266684
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: ifsk
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_LEVEL_TRIM_RANGE_OUTPUT
req.alt-loc: ntifs.h
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
ms.keywords: FILE_LEVEL_TRIM_OUTPUT, FILE_LEVEL_TRIM_OUTPUT, *PFILE_LEVEL_TRIM_OUTPUT
req.iface: 
---

# FILE_LEVEL_TRIM_OUTPUT structure



## -description
<p>The <b>FILE_LEVEL_TRIM_OUTPUT</b> structure contains the results of a trim operation performed by an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451098">FSCTL_FILE_LEVEL_TRIM</a> request.</p>


## -syntax

````
typedef struct _FILE_LEVEL_TRIM_OUTPUT {
  ULONG NumRangesProcessed;
} FILE_LEVEL_TRIM_RANGE_OUTPUT, *PFILE_LEVEL_TRIM_RANGE_OUTPUT;
````


## -struct-fields
<dl>

### -field <b>NumRangesProcessed</b>

<dd>
<p>The number or trim ranges processed.</p>
</dd>
</dl>

## -remarks
<p>This structure is optionally included as the output buffer for an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451098">FSCTL_FILE_LEVEL_TRIM</a> request. <b>NumRangesProcessed</b> indicates how many ranges of the in the array given in <a href="https://msdn.microsoft.com/library/windows/hardware/hh406398">FILE_LEVEL_TRIM</a> were processed.</p>

<p>All trim ranges in the array in <a href="https://msdn.microsoft.com/library/windows/hardware/hh406398">FILE_LEVEL_TRIM</a> were successfully processed if  <b>NumRangesProcessed</b> is equivalent to the <b>NumRanges</b> member of <b>FILE_LEVEL_TRIM</b>. Otherwise, the value in <b>NumRangesProcessed</b> is the starting index of the trim ranges that were not processed.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 8 and later versions of Windows.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451098">FSCTL_FILE_LEVEL_TRIM</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_LEVEL_TRIM_OUTPUT structure%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>