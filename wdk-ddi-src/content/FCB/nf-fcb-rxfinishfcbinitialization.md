---
UID: NF.fcb.RxFinishFcbInitialization
title: RxFinishFcbInitialization
author: windows-driver-content
description: RxFinishFcbInitialization is used to finish initializing an FCB after the successful completion of a create operation by the network mini-redirector.
old-location: ifsk\rxfinishfcbinitialization.htm
ms.assetid: 290d0b06-ccf7-4792-b7bb-556092845e55
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: ifsk
req.header: fcb.h
req.include-header: Mrxfcb.h, Nodetype.h, Fcb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxFinishFcbInitialization
req.alt-loc: fcb.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
ms.keywords: RxFinishFcbInitialization
req.iface: 
---

# RxFinishFcbInitialization function



## -description
<p><b>RxFinishFcbInitialization</b> is used to finish initializing an FCB after the successful completion of a create operation by the network mini-redirector. </p>


## -syntax

````
VOID RxFinishFcbInitialization(
  _Inout_  PMRX_FCB         MrxFcb,
  _In_     RX_FILE_TYPE     RdbssStorageType,
  _In_opt_ PFCB_INIT_PACKET InitPacket
);
````


## -parameters
<dl>

### -param <i>MrxFcb</i> [in, out]

<dd>
<p>A pointer to the MRX_FCB structure being initialized.</p>
</dd>

### -param <i>RdbssStorageType</i> [in]

<dd>
<p>The value indicating the storage type of entity that the FCB refers to. Possible options for this parameter include the following:</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="RDBSS_NTC_MAILSLOT"></a><a id="rdbss_ntc_mailslot"></a><dl>

### -param <b>RDBSS_NTC_MAILSLOT</b>

</dl>
</td>
<td width="60%">
<p>A mail slot.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="RDBSS_NTC_SPOOLFILE"></a><a id="rdbss_ntc_spoolfile"></a><dl>

### -param <b>RDBSS_NTC_SPOOLFILE</b>

</dl>
</td>
<td width="60%">
<p>A printer spool file.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="RDBSS_NTC_STORAGE_TYPE_DIRECTORY"></a><a id="rdbss_ntc_storage_type_directory"></a><dl>

### -param <b>RDBSS_NTC_STORAGE_TYPE_DIRECTORY</b>

</dl>
</td>
<td width="60%">
<p>A directory.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="RDBSS_NTC_STORAGE_TYPE_UNKNOWN"></a><a id="rdbss_ntc_storage_type_unknown"></a><dl>

### -param <b>RDBSS_NTC_STORAGE_TYPE_UNKNOWN</b>

</dl>
</td>
<td width="60%">
<p>The storage type is unknown.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="RDBSS_NTC_STORAGE_TYPE_FILE"></a><a id="rdbss_ntc_storage_type_file"></a><dl>

### -param <b>RDBSS_NTC_STORAGE_TYPE_FILE</b>

</dl>
</td>
<td width="60%">
<p>A file.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -param <i>InitPacket</i> [in, optional]

<dd>
<p>Pointer to extra data that is required for initialization depending on the storage type of the FCB being initialized. This parameter may be a <b>NULL</b> pointer if no extra data is provided.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>When called as a result of an IRP_MJ_CREATE, <a href="https://msdn.microsoft.com/library/windows/hardware/ff554356">RxCreateNetFCB</a> is called first to create the FCB. If the <b>Type</b> member of the NET_ROOT to be created is not a NET_ROOT_MAILSLOT, then <b>RxFinishFcbInitialization</b> is called to finish the initialization of the FCB structure. </p>

<p>If the <b>FcbState</b> member of the MRX_FCB structure pointed to by <i>MrxFcb</i> does not have the FCB_STATE_TIME_AND_SIZE_ALREADY_SET on, then the following members of the FCB will be updated from the <i>InitPacket</i> parameter if <i>InitPacket</i> is non <b>NULL</b>: <b>Attributes</b>, <b>NumberOfLinks</b>, <b>CreationTime</b>, <b>LastAccessTime</b>, <b>LastWriteTime</b>, <b>LastChangeTime</b>, <b>ActualAllocationLength</b>, <b>Header.AllocationSize</b>, <b>Header.FileSize</b>, and <b>Header.ValidDataLength</b>. The FCB_STATE_TIME_AND_SIZE_ALREADY_SET option is then set on in the <b>FcbState</b> member of the FCB structure.</p>

<p>If the storage type is an RDBSS_NTC_MAILSLOT and the FcbState member of the FCB does have the FCB_STATE_TIME_AND_SIZE_ALREADY_SET option set on, then the following members of the FCB structure for the mail slot will be initialized to 0: <b>Attributes</b>, <b>NumberOfLinks</b>,<b> CreationTime.QuadPart</b>,<b> LastAccessTime.QuadPart</b>, <b>LastWriteTime.QuadPart</b>, <b>LastChangeTime</b>.<b>QuadPart</b>, <b>ActualAllocationLength</b>, <b>Header.AllocationSize.QuadPart</b>, <b>Header.FileSize.QuadPart</b>, and <b>Header.ValidDataLength.QuadPart</b></p>

<p>When called as a result of an IRP_MJ_CREATE, <a href="https://msdn.microsoft.com/library/windows/hardware/ff554356">RxCreateNetFCB</a> is called first to create the FCB. If the <b>Type</b> member of the NET_ROOT to be created is not a NET_ROOT_MAILSLOT, then <b>RxFinishFcbInitialization</b> is called to finish the initialization of the FCB structure. </p>

<p>If the <b>FcbState</b> member of the MRX_FCB structure pointed to by <i>MrxFcb</i> does not have the FCB_STATE_TIME_AND_SIZE_ALREADY_SET on, then the following members of the FCB will be updated from the <i>InitPacket</i> parameter if <i>InitPacket</i> is non <b>NULL</b>: <b>Attributes</b>, <b>NumberOfLinks</b>, <b>CreationTime</b>, <b>LastAccessTime</b>, <b>LastWriteTime</b>, <b>LastChangeTime</b>, <b>ActualAllocationLength</b>, <b>Header.AllocationSize</b>, <b>Header.FileSize</b>, and <b>Header.ValidDataLength</b>. The FCB_STATE_TIME_AND_SIZE_ALREADY_SET option is then set on in the <b>FcbState</b> member of the FCB structure.</p>

<p>If the storage type is an RDBSS_NTC_MAILSLOT and the FcbState member of the FCB does have the FCB_STATE_TIME_AND_SIZE_ALREADY_SET option set on, then the following members of the FCB structure for the mail slot will be initialized to 0: <b>Attributes</b>, <b>NumberOfLinks</b>,<b> CreationTime.QuadPart</b>,<b> LastAccessTime.QuadPart</b>, <b>LastWriteTime.QuadPart</b>, <b>LastChangeTime</b>.<b>QuadPart</b>, <b>ActualAllocationLength</b>, <b>Header.AllocationSize.QuadPart</b>, <b>Header.FileSize.QuadPart</b>, and <b>Header.ValidDataLength.QuadPart</b></p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Fcb.h (include Mrxfcb.h, Nodetype.h, or Fcb.h)</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554356">RxCreateNetFCB</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554358">RxCreateNetFobx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554366">RxCreateNetRoot</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554370">RxCreateSrvCall</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554376">RxCreateSrvOpen</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554380">RxCreateVNetRoot</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554388">RxDereference</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554409">RxFinalizeConnection</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554412">RxFinalizeNetFcb</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554418">RxFinalizeNetFobx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554421">RxFinalizeNetRoot</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554426">RxFinalizeSrvCall</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554432">RxFinalizeSrvOpen</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554450">RxFinalizeVNetRoot</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554463">RxForceFinalizeAllVNetRoots</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554688">RxReference</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554728">RxSetSrvCallDomainName</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554608">RxpDereferenceNetFcb</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554627">RxpReferenceNetFcb</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxFinishFcbInitialization function%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>