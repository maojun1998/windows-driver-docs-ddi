---
UID: NS.NTIFS._WOF_EXTERNAL_FILE_ID
title: _WOF_EXTERNAL_FILE_ID
author: windows-driver-content
description: The WOF_EXTERNAL_FILE_ID structure contains a file ID that is used to open a handle to a mini-filter or driver.
old-location: ifsk\wof_external_file_id.htm
old-project: ifsk
ms.assetid: 5C208DF7-C6CB-419D-B775-74E09DC4D448
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _WOF_EXTERNAL_FILE_ID, *PWOF_EXTERNAL_FILE_ID, WOF_EXTERNAL_FILE_ID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Windows.h, WinIoCtl.h, Ntifs.h, Windows.h, WinIoCtl.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WOF_EXTERNAL_FILE_ID
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
---

# _WOF_EXTERNAL_FILE_ID structure



## -description
The <b>WOF_EXTERNAL_FILE_ID</b> structure contains a file ID that is used to open a handle to a mini-filter or driver.


## -syntax

````
typedef struct _WOF_EXTERNAL_FILE_ID {
  FILE_ID_128 FileId;
} WOF_EXTERNAL_FILE_ID, *PWOF_EXTERNAL_FILE_ID;
````


## -struct-fields

### -field FileId

The file ID used with the <b>FILE_OPEN_BY_FILE_ID</b> flag to open a file with the <a href="ifsk.fltcreatefile">FltCreateFile</a> or <a href="kernel.zwcreatefile">ZwCreateFile</a> functions.

## -remarks
Use the <a href="ifsk.fltcreatefile">FltCreateFile</a> function to open a handle to a minifilter driver and use the <a href="kernel.zwcreatefile">ZwCreateFile</a> function to open a handle to a driver.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available starting with Windows 10.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Windows.h, WinIoCtl.h, Ntifs.h, Windows.h, WinIoCtl.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.wof_external_info">WOF_EXTERNAL_INFO</a>
</dt>
<dt>
<a href="ifsk.wof_version_info">WOF_VERSION_INFO</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20WOF_EXTERNAL_FILE_ID structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>