---
UID: NF.wudfddi.IWDFFile2.GetRelatedFileObject
title: IWDFFile2::GetRelatedFileObject
author: windows-driver-content
description: The GetRelatedFileObject method retrieves the IWDFFile interface of a related file object, which is a file object that has a technology-specific relationship with another file object.
old-location: wdf\iwdffile2_getrelatedfileobject.htm
ms.assetid: 0ac5c19a-b3ec-4f1e-a018-2c11cc18e58d
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: wdf
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.alt-api: IWDFFile2.GetRelatedFileObject
req.alt-loc: WUDFx.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: <= DISPATCH_LEVEL
ms.keywords: IWDFFile2, GetRelatedFileObject, IWDFFile2::GetRelatedFileObject
req.iface: IWDFFile2
req.product: Windows 10 or later.
---

# IWDFFile2::GetRelatedFileObject method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]</p>
<p>The <b>GetRelatedFileObject</b> method retrieves the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a> interface of a <i>related file object</i>, which is a file object that has a technology-specific relationship with another file object.</p>


## -syntax

````
void GetRelatedFileObject(
  [out] IWDFFile **ppRelatedFileObj
);
````


## -parameters
<dl>

### -param <i>ppRelatedFileObj</i> [out]

<dd>
<p>The address of a location that receives a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a> interface of a UMDF file object. This file object is related to the file object that exposes the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558915">IWDFFile2</a> interface's parent <b>IWDFFile</b> interface.</p>
</dd>
</dl>

## -returns
<p>None.</p>

## -remarks
<p>Use of related file objects is technology-specific. For example, <a href="NULL">kernel streaming</a> uses related file objects to represent the parent filters of child pins.</p>

<p>For more information about related file objects, see the <b>GetRelatedFileObject</b> member of the kernel-mode <a href="https://msdn.microsoft.com/library/windows/hardware/ff545834">FILE_OBJECT</a> structure.</p>

<p>The following code example retrieves the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a> interface of a related file object, from the <b>IWDFFile</b> interface that a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556841">IQueueCallbackCreate::OnCreateFile</a>  callback function receives.</p>

<p>Use of related file objects is technology-specific. For example, <a href="NULL">kernel streaming</a> uses related file objects to represent the parent filters of child pins.</p>

<p>For more information about related file objects, see the <b>GetRelatedFileObject</b> member of the kernel-mode <a href="https://msdn.microsoft.com/library/windows/hardware/ff545834">FILE_OBJECT</a> structure.</p>

<p>The following code example retrieves the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a> interface of a related file object, from the <b>IWDFFile</b> interface that a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556841">IQueueCallbackCreate::OnCreateFile</a>  callback function receives.</p>

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
<p>End of support</p>
</th>
<td width="70%">
<p>Unavailable in UMDF 2.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>1.9</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wudfddi.h (include Wudfddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>WUDFx.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558915">IWDFFile2</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFFile2::GetRelatedFileObject method%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>