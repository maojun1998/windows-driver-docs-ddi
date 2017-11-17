---
UID: NS.scsiwmi._SCSIWMILIB_CONTEXT
title: SCSIWMILIB_CONTEXT
author: windows-driver-content
description: A SCSI_WMILIB_CONTEXT structure provides registration information for a miniport driver's data and event blocks and defines entry points for the miniport driver's HwScsiWmiXxx callback routines.
old-location: storage\scsi_wmilib_context.htm
ms.assetid: 7886cee8-1142-42e6-8206-84667621ba77
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: Storage
req.header: scsiwmi.h
req.include-header: Scsiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SCSI_WMILIB_CONTEXT
req.alt-loc: scsiwmi.h
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
ms.keywords: SCSIWMILIB_CONTEXT, SCSI_WMILIB_CONTEXT, *PSCSI_WMILIB_CONTEXT
req.iface: 
req.product: Windows 10 or later.
---

# SCSIWMILIB_CONTEXT structure



## -description
<p>A SCSI_WMILIB_CONTEXT structure provides registration information for a miniport driver's data and event blocks and defines entry points for the miniport driver's <b>HwScsiWmi</b><b><i>Xxx</i></b> callback routines. </p>


## -syntax

````
typedef struct _SCSIWMILIB_CONTEXT {
  ULONG                     GuidCount;
  PSCSIWMIGUIDREGINFO       GuidList;
  PSCSIWMI_QUERY_REGINFO    QueryWmiRegInfo;
  PSCSIWMI_QUERY_DATABLOCK  QueryWmiDataBlock;
  PSCSIWMI_SET_DATABLOCK    SetWmiDataBlock;
  PSCSIWMI_SET_DATAITEM     SetWmiDataItem;
  PSCSIWMI_EXECUTE_METHOD   ExecuteWmiMethod;
  PSCSIWMI_FUNCTION_CONTROL WmiFunctionControl;
} SCSI_WMILIB_CONTEXT, *PSCSI_WMILIB_CONTEXT;
````


## -struct-fields
<dl>

### -field <b>GuidCount</b>

<dd>
<p>Specifies the number of structures in the SCSIWMIGUIDREGINFO array at <b>GuidList</b>.</p>
</dd>

### -field <b>GuidList</b>

<dd>
<p>Points to an array of <b>GuidCount</b> SCSIWMIGUIDREGINFO structures that contain registration information for each block.</p>
</dd>

### -field <b>QueryWmiRegInfo</b>

<dd>
<p>Points to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557344">HwScsiWmiQueryReginfo</a> routine, which is a required entry point for miniport drivers that support WMI.</p>
</dd>

### -field <b>QueryWmiDataBlock</b>

<dd>
<p>Points to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557340">HwScsiWmiQueryDataBlock</a> routine, which is a required entry point for miniport drivers that support WMI.</p>
</dd>

### -field <b>SetWmiDataBlock</b>

<dd>
<p>Points to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557349">HwScsiWmiSetDataBlock</a> routine, which is an optional entry point for miniport drivers that support WMI. If the miniport driver does not implement this routine, it must set this member to <b>NULL</b></p>
</dd>

### -field <b>SetWmiDataItem</b>

<dd>
<p>Points to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557357">HwScsiWmiSetDataItem</a> routine, which is an optional entry point for miniport drivers that support WMI. If the miniport driver does not implement this routine, it must set this member to <b>NULL</b>.</p>
</dd>

### -field <b>ExecuteWmiMethod</b>

<dd>
<p>Points to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557332">HwScsiWmiExecuteMethod</a> routine, which is an optional entry point for miniport drivers that support WMI. If the miniport driver does not implement this routine, it must set this member to <b>NULL</b></p>
</dd>

### -field <b>WmiFunctionControl</b>

<dd>
<p>Points to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557338">HwScsiWmiFunctionControl</a> routine, which is an optional entry point for miniport drivers that support WMI. If the miniport driver does not implement this routine, it must set this member to <b>NULL</b>. </p>
</dd>
</dl>

## -remarks
<p>A SCSI miniport driver that supports WMI stores an initialized SCSI_WMILIB_CONTEXT structure (or a pointer to such a structure) in its device extension. A miniport driver can use the same SCSI_WMILIB_CONTEXT structure for multiple device objects if each device object supplies the same set of data blocks. </p>

<p>When the miniport driver receives an SRB in which the <b>Function</b> member is set to SRB_FUNCTION_WMI, it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff564766">ScsiPortWmiDispatchFunction</a> with request parameters, including a pointer to an initialized SCSI_WMILIB_CONTEXT structure. <b>ScsiPortWmiDispatchFunction</b> handles the request by calling the miniport driver's appropriate HwScsiWmiXxx routine.</p>

<p>If the miniport driver does not implement an optional HwScsiWmiXxx routine, the port driver returns an appropriate status to the caller.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Scsiwmi.h (include Scsiwmi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557332">HwScsiWmiExecuteMethod</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557338">HwScsiWmiFunctionControl</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557340">HwScsiWmiQueryDataBlock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557344">HwScsiWmiQueryReginfo</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557349">HwScsiWmiSetDataBlock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557357">HwScsiWmiSetDataItem</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564766">ScsiPortWmiDispatchFunction</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564941">SCSIWMIGUIDREGINFO</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20SCSI_WMILIB_CONTEXT structure%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>