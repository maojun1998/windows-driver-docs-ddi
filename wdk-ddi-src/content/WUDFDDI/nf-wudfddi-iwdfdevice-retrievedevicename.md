---
UID: NF.wudfddi.IWDFDevice.RetrieveDeviceName
title: IWDFDevice::RetrieveDeviceName
author: windows-driver-content
description: The RetrieveDeviceName method retrieves the name of an underlying kernel-mode device.
old-location: wdf\iwdfdevice_retrievedevicename.htm
ms.assetid: 75304f5d-8a07-4db5-9f20-5764ff5d2ef6
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
req.umdf-ver: 1.5
req.alt-api: IWDFDevice.RetrieveDeviceName
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
ms.keywords: IWDFDevice, RetrieveDeviceName, IWDFDevice::RetrieveDeviceName
req.iface: IWDFDevice
req.product: Windows 10 or later.
---

# IWDFDevice::RetrieveDeviceName method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]</p>
<p>The <b>RetrieveDeviceName</b> method retrieves the name of an underlying kernel-mode device.</p>


## -syntax

````
HRESULT RetrieveDeviceName(
  [out]     PWSTR pDeviceName,
  [in, out] DWORD *pdwDeviceNameLength
);
````


## -parameters
<dl>

### -param <i>pDeviceName</i> [out]

<dd>
<p>A pointer to a buffer that receives a <b>NULL</b>-terminated string that represents the name of the underlying kernel-mode device, if the buffer is non-<b>NULL</b> and <b>RetrieveDeviceName</b> is successful. </p>
</dd>

### -param <i>pdwDeviceNameLength</i> [in, out]

<dd>
<p>A pointer to a variable that receives the number of characters, including the <b>NULL</b> character, in the device name.</p>
<p>If the buffer at <i>pDeviceName</i> is <b>NULL</b>, the value that the driver supplies is zero. The framework then returns the size, in characters, that is required for the device name string.</p>
<p>If the buffer at <i>pDeviceName</i> is non-<b>NULL</b>, the framework returns the size, in characters, of the device name string. </p>
</dd>
</dl>

## -returns
<p><b>RetrieveDeviceName</b> returns S_OK for the following scenarios: </p>

<p>
<ul>
<li>The buffer that the <i>pDeviceName</i> parameter pointed to was non-<b>NULL</b> and large enough to hold the name string, including the <b>NULL</b> character, and the framework successfully copied the string into the supplied buffer and set the variable that is pointed to by <i>pdwDeviceNameLength</i> to the number of characters in the string.</li>
<li>The buffer at <i>pDeviceName</i> was <b>NULL</b>, the driver preset the variable at <i>pdwDeviceNameLength</i> to 0, and the framework set the variable at <i>pdwDeviceNameLength</i> to the number of characters that were required for the string.</li>
</ul>
</p>

<p><b>RetrieveDeviceName</b> returns HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER) to indicate that the supplied buffer was non-<b>NULL</b> and did not contain enough space to hold the device name. The framework sets the variable at <i>pdwDeviceNameLength</i> to the number of characters that are required for the string.</p>

<p><b>RetrieveDeviceName</b> might also return other HRESULT values.

</p>

## -remarks
<p>The device name is not the physical device object (PDO) name. Instead, the device name is the name of the reflector. The driver must target all I/O to this device object.</p>

<p>The following code example shows how to retrieve the name of an underlying kernel-mode device.</p>

<p>The device name is not the physical device object (PDO) name. Instead, the device name is the name of the reflector. The driver must target all I/O to this device object.</p>

<p>The following code example shows how to retrieve the name of an underlying kernel-mode device.</p>

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
<p>1.5</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556917">IWDFDevice</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice::RetrieveDeviceName method%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>