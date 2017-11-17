---
UID: NS.ntddk._RTL_GENERIC_TABLE~r1
title: RTL_GENERIC_TABLE
author: windows-driver-content
description: The RTL_GENERIC_TABLE structure contains file system-specific data for a splay tree.
old-location: ifsk\rtl_generic_table.htm
ms.assetid: 0e5dba1b-8b0d-470a-8ead-4c022e9da7fe
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: ifsk
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available on Windows 2000 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RTL_GENERIC_TABLE
req.alt-loc: ntddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
ms.keywords: RTL_GENERIC_TABLE, RTL_GENERIC_TABLE
req.iface: 
---

# RTL_GENERIC_TABLE structure



## -description
<p>The RTL_GENERIC_TABLE structure contains file system-specific data for a splay tree. </p>
<p>RTL_GENERIC_TABLE is opaque and not directly manipulated. Drivers must use the support routines that are described in the Remarks section to manipulate RTL_GENERIC_TABLE values. </p>


## -syntax

````
typedef struct _RTL_GENERIC_TABLE {
  PRTL_SPLAY_LINKS              TableRoot;
  LIST_ENTRY                    InsertOrderList;
  PLIST_ENTRY                   OrderedPointer;
  ULONG                         WhichOrderedElement;
  ULONG                         NumberGenericTableElements;
  PRTL_GENERIC_COMPARE_ROUTINE  CompareRoutine;
  PRTL_GENERIC_ALLOCATE_ROUTINE AllocateRoutine;
  PRTL_GENERIC_FREE_ROUTINE     FreeRoutine;
  PVOID                         TableContext;
} RTL_GENERIC_TABLE, *PRTL_GENERIC_TABLE;
````


## -struct-fields
<dl>

### -field <b>TableRoot</b>

<dd>
<p>Reserved for system use.</p>
</dd>

### -field <b>InsertOrderList</b>

<dd>
<p>Reserved for system use.</p>
</dd>

### -field <b>OrderedPointer</b>

<dd>
<p>Reserved for system use.</p>
</dd>

### -field <b>WhichOrderedElement</b>

<dd>
<p>Reserved for system use.</p>
</dd>

### -field <b>NumberGenericTableElements</b>

<dd>
<p>Reserved for system use.</p>
</dd>

### -field <b>CompareRoutine</b>

<dd>
<p>Reserved for system use.</p>
</dd>

### -field <b>AllocateRoutine</b>

<dd>
<p>Reserved for system use.</p>
</dd>

### -field <b>FreeRoutine</b>

<dd>
<p>Reserved for system use.</p>
</dd>

### -field <b>TableContext</b>

<dd>
<p>Reserved for system use.</p>
</dd>
</dl>

## -remarks
<p>To initialize a generic table package, you allocate a buffer that is at least <b>sizeof(</b>RTL_GENERIC_TABLE<b>) </b>bytes in size to receive the initialized generic table structure from a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552989">RtlInitializeGenericTable</a> routine. You can use the following routines to manipulate the table:</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552209">RtlDeleteElementGenericTable</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552243">RtlEnumerateGenericTable</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552247">RtlEnumerateGenericTableWithoutSplaying</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552297">RtlGetElementGenericTable</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553024">RtlInsertElementGenericTable</a>
</p>

<p>
<a href="https://msdn.microsoft.com/c7d346ab-6990-4636-bafd-2e448a937f3b">RtlInsertElementGenericTableFull</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553046">RtlIsGenericTableEmpty</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553091">RtlLookupElementGenericTable</a>
</p>

<p>
<a href="https://msdn.microsoft.com/fddb2e23-ddb3-48bc-a94e-0ca9a8580b78">RtlLookupElementGenericTableFull</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553134">RtlNumberGenericTableElements</a>
</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>This structure is available on Windows 2000 and later. </p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552209">RtlDeleteElementGenericTable</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552243">RtlEnumerateGenericTable</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552247">RtlEnumerateGenericTableWithoutSplaying</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552297">RtlGetElementGenericTable</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552989">RtlInitializeGenericTable</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553024">RtlInsertElementGenericTable</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/c7d346ab-6990-4636-bafd-2e448a937f3b">RtlInsertElementGenericTableFull</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553046">RtlIsGenericTableEmpty</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553091">RtlLookupElementGenericTable</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/fddb2e23-ddb3-48bc-a94e-0ca9a8580b78">RtlLookupElementGenericTableFull</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553134">RtlNumberGenericTableElements</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RTL_GENERIC_TABLE structure%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>