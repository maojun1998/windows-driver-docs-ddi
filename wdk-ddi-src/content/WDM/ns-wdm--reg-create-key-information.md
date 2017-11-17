---
UID: NS.wdm._REG_CREATE_KEY_INFORMATION
title: REG_CREATE_KEY_INFORMATION
author: windows-driver-content
description: The REG_OPEN_KEY_INFORMATION structure contains the name of a registry key that is about to be opened.
old-location: kernel\reg_open_key_information.htm
ms.assetid: 486510a0-006d-45dc-a33a-70e92370da79
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: kernel
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Server 2003, but some structure members are available only in Windows Vista and later versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: REG_CREATE_KEY_INFORMATION
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
ms.keywords: REG_CREATE_KEY_INFORMATION, REG_CREATE_KEY_INFORMATION, REG_OPEN_KEY_INFORMATION, *PREG_CREATE_KEY_INFORMATION, *PREG_OPEN_KEY_INFORMATION
req.iface: 
req.product: Windows 10 or later.
---

# REG_CREATE_KEY_INFORMATION structure



## -description
<p>The <b>REG_OPEN_KEY_INFORMATION</b> structure contains the name of a registry key that is about to be opened.</p>


## -syntax

````
typedef struct _REG_CREATE_KEY_INFORMATION {
  PUNICODE_STRING CompleteName;
  PVOID           RootObject;
  PVOID           ObjectType;
  ULONG           CreateOptions;
  PUNICODE_STRING Class;
  PVOID           SecurityDescriptor;
  PVOID           SecurityQualityOfService;
  ACCESS_MASK     DesiredAccess;
  ACCESS_MASK     GrantedAccess;
  PULONG          Disposition;
  PVOID           *ResultObject;
  PVOID           CallContext;
  PVOID           RootObjectContext;
  PVOID           Transaction;
  PVOID           Reserved;
} REG_CREATE_KEY_INFORMATION, REG_OPEN_KEY_INFORMATION, *PREG_CREATE_KEY_INFORMATION, *PREG_OPEN_KEY_INFORMATION;
````


## -struct-fields
<dl>

### -field <b>CompleteName</b>

<dd>
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains the path of the new registry key. The path can be absolute or relative. If the path is absolute, this structure contains a fully qualified path that starts with the "\" character. For an absolute path, the <b>RootObject</b> member specifies the <b>\REGISTRY</b> key, which is the root directory of the registry tree. If the path is relative, the path starts with a character other than "\", and is relative to the key that is specified by the <b>RootObject</b> member.</p>
</dd>

### -field <b>RootObject</b>

<dd>
<p>A pointer to the registry key object that serves as the root for the path that the <b>CompleteName</b> member specifies. </p>
</dd>

### -field <b>ObjectType</b>

<dd>
<p>The <b>ObjectType</b> member is for internal use. Drivers must not access this member. This member is defined starting with Windows Vista.</p>
</dd>

### -field <b>CreateOptions</b>

<dd>
<p>The <b>CreateOptions</b> member is not used. This member is defined starting with Windows Vista.</p>
</dd>

### -field <b>Class</b>

<dd>
<p>The <b>Class</b> member is not used. This member is defined starting with Windows Vista.</p>
</dd>

### -field <b>SecurityDescriptor</b>

<dd>
<p>The <b>SecurityDescriptor</b> member is not used. This member is defined starting with Windows Vista.</p>
</dd>

### -field <b>SecurityQualityOfService</b>

<dd>
<p>The <b>SecurityQualityOfService</b> member is not used. This member is defined starting with Windows Vista.</p>
</dd>

### -field <b>DesiredAccess</b>

<dd>
<p>The access mask that was specified by the thread that is attempting to open the registry key. This member is defined starting with Windows Vista.</p>
</dd>

### -field <b>GrantedAccess</b>

<dd>
<p>An access mask that indicates the access rights that have been granted to the thread that is attempting to open the registry key. For more information about this member, see Remarks. This member is defined starting with Windows Vista.</p>
</dd>

### -field <b>Disposition</b>

<dd>
<p>The <b>Disposition</b> member is not used. This member is defined starting with Windows Vista.</p>
</dd>

### -field <b>ResultObject</b>

<dd>
<p>A pointer to a location that receives the address of the key object that represents the opened registry key. For more information about this member, see Remarks. This member is defined starting with Windows Vista.</p>
</dd>

### -field <b>CallContext</b>

<dd>
<p>A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541924">CmSetCallbackObjectContext</a>. This member is defined starting with Windows Vista.</p>
</dd>

### -field <b>RootObjectContext</b>

<dd>
<p>A pointer to a driver-defined context information that the driver has associated with the root of the path for the registry object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541924">CmSetCallbackObjectContext</a>. This member is defined starting with Windows Vista.</p>
</dd>

### -field <b>Transaction</b>

<dd>
<p>A pointer to a transaction object that the operation is attempted on. If this member is <b>NULL</b>, the operation is being performed in non-transactional context. This member is defined starting with Windows Vista.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>Starting with Windows Vista, if this member is 1, then it is safe to cast this structure to type <a href="https://msdn.microsoft.com/library/windows/hardware/ff560959">REG_OPEN_KEY_INFORMATION_V1</a>, which contains additional parameters.</p>
<p>In versions of Windows before Windows Vista, this member is always 0.</p>
</dd>
</dl>

## -remarks
<p>The system passes this structure to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine every time a thread attempts to open a key—for example, when a user-mode thread calls the <a href="base.regopenkey">RegOpenKey</a> or <a href="base.regopenkeyex">RegOpenKeyEx</a> function, or when or a driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567014">ZwOpenKey</a> routine.</p>

<p>If the driver's <i>RegistryCallback</i> routine returns STATUS_CALLBACK_BYPASS for a <b>RegNtPreOpenKeyEx</b> notification, the driver must supply the <b>GrantedAccess</b> and <b>ResultObject</b> values.</p>

<p>For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows Server 2003, but some structure members are available only in Windows Vista and later versions.</p>
</td>
</tr>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541924">CmSetCallbackObjectContext</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>
</dt>
<dt>
<a href="base.regopenkey">RegOpenKey</a>
</dt>
<dt>
<a href="base.regopenkeyex">RegOpenKeyEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560959">REG_OPEN_KEY_INFORMATION_V1</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567014">ZwOpenKey</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20REG_OPEN_KEY_INFORMATION structure%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>