---
UID: NS.hbapiwmi._SetBindingSupport_IN
title: SetBindingSupport_IN
author: windows-driver-content
description: The SetBindingSupport_IN structure is used to deliver input parameter data to the SetBindingSupport WMI method.
old-location: storage\setbindingsupport_in.htm
ms.assetid: bdcd6f76-9a45-4687-b3ab-ece3e9419c44
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: Storage
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SetBindingSupport_IN
req.alt-loc: hbapiwmi.h
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
ms.keywords: SetBindingSupport_IN, SetBindingSupport_IN, *PSetBindingSupport_IN
req.iface: 
---

# SetBindingSupport_IN structure



## -description
<p>The SetBindingSupport_IN structure is used to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565565">SetBindingSupport</a> WMI method.</p>


## -syntax

````
typedef struct _SetBindingSupport_IN {
  UCHAR PortWWN[8];
  ULONG BindType;
} SetBindingSupport_IN, *PSetBindingSupport_IN;
````


## -struct-fields
<dl>

### -field <b>PortWWN</b>

<dd>
<p>Contains a worldwide name that indicates the port whose persistent bindings are to be retrieved. </p>
</dd>

### -field <b>BindType</b>

<dd>
<p>Contains a bitmap that indicates the ability of an HBA and its miniport driver to provide a specific set of features related to persistent binding. For a list of values that this parameter can have, see the description of the HBA_BIND_TYPE WMI class qualifier.</p>
</dd>
</dl>

## -remarks
<p>The WMI tool suite generates a declaration of the SetBindingSupport_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Hbapiwmi.h (include Hbapiwmi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565565">SetBindingSupport</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20SetBindingSupport_IN structure%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>