---
UID: NS.WDM._OB_OPERATION_REGISTRATION
title: _OB_OPERATION_REGISTRATION
author: windows-driver-content
description: The OB_OPERATION_REGISTRATION structure specifies ObjectPreCallback and ObjectPostCallback callback routines and the types of operations that the routines are called for.
old-location: kernel\ob_operation_registration.htm
old-project: kernel
ms.assetid: 06da3ec0-b8d3-4bd8-8270-ead38b7deada
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _OB_OPERATION_REGISTRATION, OB_OPERATION_REGISTRATION, *POB_OPERATION_REGISTRATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Server 2008.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: OB_OPERATION_REGISTRATION,PsProcessType,PsThreadType
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
req.product: Windows 10 or later.
---

# _OB_OPERATION_REGISTRATION structure



## -description
The <b>OB_OPERATION_REGISTRATION</b> structure specifies <a href="kernel.objectprecallback">ObjectPreCallback</a> and <a href="kernel.objectpostcallback">ObjectPostCallback</a> callback routines and the types of operations that the routines are called for. 


## -syntax

````
typedef struct _OB_OPERATION_REGISTRATION {
  POBJECT_TYPE                *ObjectType;
  OB_OPERATION                Operations;
  POB_PRE_OPERATION_CALLBACK  PreOperation;
  POB_POST_OPERATION_CALLBACK PostOperation;
} OB_OPERATION_REGISTRATION, *POB_OPERATION_REGISTRATION;
````


## -struct-fields

### -field ObjectType

A pointer to the object type that triggers the callback routine. Specify one of the following values:
<ul>
<li><b>PsProcessType</b> for process handle operations</li>
<li><b>PsThreadType</b> for thread handle operations</li>
<li><b>ExDesktopObjectType</b> for desktop handle operations. This value is supported in Windows 10 and not in the earlier versions of the operating system.</li>
</ul>

### -field Operations

Specify one or more of the following flags:


### -field OB_OPERATION_HANDLE_CREATE

A new process, thread, or desktop handle was or will be opened.

### -field OB_OPERATION_HANDLE_DUPLICATE

A process, thread, or desktop handle was or will be duplicated.
</dd>
</dl>

### -field PreOperation

A pointer to an <a href="kernel.objectprecallback">ObjectPreCallback</a> routine. The system calls this routine before the requested operation occurs.

### -field PostOperation

A pointer to an <a href="kernel.objectpostcallback">ObjectPostCallback</a> routine. The system calls this routine after the requested operation occurs.

## -remarks
This structure is used by the <a href="kernel.obregistercallbacks">ObRegisterCallbacks</a> routine. The <i>CallBackRegistration</i> parameter to this routine is a pointer to a buffer that contains an <a href="kernel.ob_callback_registration">OB_CALLBACK_REGISTRATION</a> structure that is followed by an array of one or more <b>OB_OPERATION_REGISTRATION</b> structures.

In each <b>OB_OPERATION_REGISTRATION</b> structure passed to <b>ObRegisterCallback</b>, the caller must supply one or both callback routines. If the <b>PreOperation</b> and <b>PostOperation</b> members of this structure are both <b>NULL</b>, the callback registration operation fails.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available starting with Windows Server 2008.
</td>
</tr>
<tr>
<th width="30%">
Header
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
<a href="kernel.ob_callback_registration">OB_CALLBACK_REGISTRATION</a>
</dt>
<dt>
<a href="kernel.objectpostcallback">ObjectPostCallback</a>
</dt>
<dt>
<a href="kernel.objectprecallback">ObjectPreCallback</a>
</dt>
<dt>
<a href="kernel.obregistercallbacks">ObRegisterCallbacks</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20OB_OPERATION_REGISTRATION structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>