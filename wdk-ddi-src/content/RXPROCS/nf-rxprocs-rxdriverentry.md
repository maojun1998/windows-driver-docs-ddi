---
UID: NF.rxprocs.RxDriverEntry
title: RxDriverEntry
author: windows-driver-content
description: RxDriverEntry is called by a monolithic network mini-redirector driver from its DriverEntry routine to initialize the RDBSS static library.
old-location: ifsk\rxdriverentry.htm
ms.assetid: f100f872-6db2-4b6d-a9c0-abbbfee0a621
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: ifsk
req.header: rxprocs.h
req.include-header: Rxprocs.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxDriverEntry
req.alt-loc: rxprocs.h
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
ms.keywords: RxDriverEntry
req.iface: 
req.product: Windows 10 or later.
---

# RxDriverEntry function



## -description
<p><b>RxDriverEntry</b> is called by a monolithic network mini-redirector driver from its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine to initialize the RDBSS static library.</p>
<p>For non-monolithic drivers, this initialization routine is equivalent to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine of the RDBSS.SYS device driver.</p>


## -syntax

````
NTSTATUS RxDriverEntry(
  _In_ PDRIVER_OBJECT  DriverObject,
  _In_ PUNICODE_STRING RegistryPath
);
````


## -parameters
<dl>

### -param <i>DriverObject</i> [in]

<dd>
<p>A pointer to the driver object of the network mini-redirector driver. Each driver receives a pointer to its driver object in a parameter to its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine. This driver object will be used to create the device object for the network mini-redirector driver. </p>
</dd>

### -param <i>RegistryPath</i> [in]

<dd>
<p>A pointer to a Unicode string containing the registry path to where driver parameters and other configuration data are stored. This registry path is normally located under a services entry for the specific network mini-redirector located under the following key:</p>
<p>HKLM\System\CurrentControlSet\Services</p>
</dd>
</dl>

## -returns
<p><b>RxDriverEntry</b> returns STATUS_SUCCESS on success or one of the following error values on failure: </p><dl>
<dt><b>RXINIT_START</b></dt>
</dl><p>The initialization of RDBSS was started, but an error occurred. This error code is an internal RDBSS enum with a value of 5.</p>

<p> </p>

## -remarks
<p>A monolithic network mini-redirector driver which is linked statically with RDBSSLIB.LIB must call <b>RxDriverEntry</b> from its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine to initialize the copy of the RDBSSLIB library linked with the driver. <b>RxDriverEntry</b> must be called by a monolithic network mini-redirector driver before any other RDBSS routines are called. </p>

<p>After calling <b>RxDriverEntry</b> to initialize the copy of the RDBSS library near the start of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine, the network mini-redirector driver would usually call <a href="https://msdn.microsoft.com/library/windows/hardware/ff554693">RxRegisterMinirdr</a> later in its <i>DriverEntry</i> routine to register with RDBSS. </p>

<p>If the <b>RxDriverEntry</b> call is successful, internal global RDBBS data structures are initialized. Various spinlocks and mutexes are created to protect these data structures. One of these data structures is the RDBSS_DATA structure which is the top structure in the RDBSS-memory data structure. The <i>DriverObject</i> parameter is stored in the <b>DriverObject</b> member of the RDBSS_DATA structure. <b>RxDriverEntry</b> also initializes tracing, logging, and debugging if this is enabled (a checked build, for example). </p>

<p><b>RxDriverEntry</b> will also try to open the registry path passed as the <i>RegistryPath</i> parameter, treating this object as a case-insensitive string. If this registry key can be successfully opened, then an attempt will be made to open a Parameters registry key below this entry. </p>

<p><b>RxDriverEntry</b> will also attempt to open the following registry key:</p>

<p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HKLM\System\CurrentControlSet\Services\LanmanWorkStation\Parameters</pre>
</td>
</tr>
</table></span></div>
</p>

<p>If this key can be opened, then an attempt will be made to read some values under this key depending on the version of the operating system.</p>

<p>On Windows XP and later, <b>RxDriverEntry</b> will attempt to open the following value under the LanmanWorkStation\Parameters key:</p>

<p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DisableByteRangeLockingOnReadOnlyFiles</pre>
</td>
</tr>
</table></span></div>
</p>

<p>This value is a DWORD that is treated as a boolean and stored as the boolean value for DisableByteRangeLockingOnReadOnlyFiles, an RDBSS variable for handling byte range locking on read only files. This variable affects how RDBSS handles a new SRV_OPEN request by the network mini-redirector on an FCB and decides whether it can be collapsed onto an existing SRV_OPEN if the attributes are compatible. If a network mini-redirector driver wants to change this behavior, the driver should set the value of DisableByteRangeLockingOnReadOnlyFiles to the appropriate value after the <b>RxDriverEntry</b> routine has returned. The RDBSSLIB.LIB static library exposes DisableByteRangeLockingOnReadOnlyFiles as an external variable.</p>

<p>On Windows 2000 and Windows XP, <b>RxDriverEntry</b> will attempt to open the following value under the LanmanWorkStation\Parameters key:</p>

<p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>ReadAheadGranularity</pre>
</td>
</tr>
</table></span></div>
</p>

<p>This value is a DWORD that is treated as a number and stored as the value for an internal RDBSS option on the number of PAGE_SIZE pages for read ahead used by the Cache Manager. Any registry value greater than 16 is treated as if this value were limited to 16 (the maximum value currently allowed). This internal option is stored as the number of pages times the PAGE_SIZE on the processor (a maximum of 0x10000 or 64K for a 4K PAGE_SIZE, for example). On Windows 2000 and Windows XP, RDBSS calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff539224">CcSetReadAheadGranularity</a> with this option for various create, read, and write operations. If a network mini-redirector driver wants to change this behavior, the driver should set the value of ReadAheadGranularity to the appropriate value after the <b>RxDriverEntry</b> routine has returned. The RDBSSLIB.LIB static library exposes ReadAheadGranularity as an external variable. </p>

<p>On X86 systems, 64K is the largest write that will be issued by the Memory Manager when issuing a paging write (flushes of the cache will be paging writes through the Memory Manager). For remote file systems, 64K is not the best choice. The most data that can be transferred in a single TDI network request would be less than 64K because of overhead for protocol information. </p>

<p>On Windows Server 2003, a registry value to set ReadAheadGranularity is not exposed and RDBSS defaults to 32K (8 4K PAGE_SIZE pages). This is the same default value adopted for local files systems.</p>

<p><b>RxDriverEntry</b> retrieves a pointer to the kernel process that is running by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff559933">PsGetCurrentProcess</a> and stores this value in an internal RDBSS data structure. This kernel process is sometimes called the file system process.</p>

<p><b>RxDriverEntry</b> then copies a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554468">RxFsdDispatch</a> routine over all of the entries in the driver dispatch table. So if a monolithic network mini-redirector driver needs to receive specific IRPs for special processing before the RDBSS library, then a copy of its original driver dispatch table should be saved before calling <b>RxDriverEntry</b> and any routine pointers restored after the call to <b>RxDriverEntry</b> has returned. Note that RDBSS will also copy <b>RxFsdDispatch</b> to all the driver dispatch table entries when <a href="https://msdn.microsoft.com/library/windows/hardware/ff554693">RxRegisterMiniRdr</a> is called unless an option is set to prevent this behavior..</p>

<p>For a non-monolithic network mini-redirector driver (the Microsoft SMB redirector), the RDBSS.SYS device driver is initialized in its own <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine when loaded which internally calls <b>RxDriverEntry</b>. On a monolithic driver, the <b>RxDriverEntry</b> routine is exported from the RDBSSLIB.LIB static library and must be called explicitly by the network mini-redirector. </p>

<p>A monolithic network mini-redirector driver which is linked statically with RDBSSLIB.LIB must call <b>RxDriverEntry</b> from its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine to initialize the copy of the RDBSSLIB library linked with the driver. <b>RxDriverEntry</b> must be called by a monolithic network mini-redirector driver before any other RDBSS routines are called. </p>

<p>After calling <b>RxDriverEntry</b> to initialize the copy of the RDBSS library near the start of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine, the network mini-redirector driver would usually call <a href="https://msdn.microsoft.com/library/windows/hardware/ff554693">RxRegisterMinirdr</a> later in its <i>DriverEntry</i> routine to register with RDBSS. </p>

<p>If the <b>RxDriverEntry</b> call is successful, internal global RDBBS data structures are initialized. Various spinlocks and mutexes are created to protect these data structures. One of these data structures is the RDBSS_DATA structure which is the top structure in the RDBSS-memory data structure. The <i>DriverObject</i> parameter is stored in the <b>DriverObject</b> member of the RDBSS_DATA structure. <b>RxDriverEntry</b> also initializes tracing, logging, and debugging if this is enabled (a checked build, for example). </p>

<p><b>RxDriverEntry</b> will also try to open the registry path passed as the <i>RegistryPath</i> parameter, treating this object as a case-insensitive string. If this registry key can be successfully opened, then an attempt will be made to open a Parameters registry key below this entry. </p>

<p><b>RxDriverEntry</b> will also attempt to open the following registry key:</p>

<p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HKLM\System\CurrentControlSet\Services\LanmanWorkStation\Parameters</pre>
</td>
</tr>
</table></span></div>
</p>

<p>If this key can be opened, then an attempt will be made to read some values under this key depending on the version of the operating system.</p>

<p>On Windows XP and later, <b>RxDriverEntry</b> will attempt to open the following value under the LanmanWorkStation\Parameters key:</p>

<p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DisableByteRangeLockingOnReadOnlyFiles</pre>
</td>
</tr>
</table></span></div>
</p>

<p>This value is a DWORD that is treated as a boolean and stored as the boolean value for DisableByteRangeLockingOnReadOnlyFiles, an RDBSS variable for handling byte range locking on read only files. This variable affects how RDBSS handles a new SRV_OPEN request by the network mini-redirector on an FCB and decides whether it can be collapsed onto an existing SRV_OPEN if the attributes are compatible. If a network mini-redirector driver wants to change this behavior, the driver should set the value of DisableByteRangeLockingOnReadOnlyFiles to the appropriate value after the <b>RxDriverEntry</b> routine has returned. The RDBSSLIB.LIB static library exposes DisableByteRangeLockingOnReadOnlyFiles as an external variable.</p>

<p>On Windows 2000 and Windows XP, <b>RxDriverEntry</b> will attempt to open the following value under the LanmanWorkStation\Parameters key:</p>

<p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>ReadAheadGranularity</pre>
</td>
</tr>
</table></span></div>
</p>

<p>This value is a DWORD that is treated as a number and stored as the value for an internal RDBSS option on the number of PAGE_SIZE pages for read ahead used by the Cache Manager. Any registry value greater than 16 is treated as if this value were limited to 16 (the maximum value currently allowed). This internal option is stored as the number of pages times the PAGE_SIZE on the processor (a maximum of 0x10000 or 64K for a 4K PAGE_SIZE, for example). On Windows 2000 and Windows XP, RDBSS calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff539224">CcSetReadAheadGranularity</a> with this option for various create, read, and write operations. If a network mini-redirector driver wants to change this behavior, the driver should set the value of ReadAheadGranularity to the appropriate value after the <b>RxDriverEntry</b> routine has returned. The RDBSSLIB.LIB static library exposes ReadAheadGranularity as an external variable. </p>

<p>On X86 systems, 64K is the largest write that will be issued by the Memory Manager when issuing a paging write (flushes of the cache will be paging writes through the Memory Manager). For remote file systems, 64K is not the best choice. The most data that can be transferred in a single TDI network request would be less than 64K because of overhead for protocol information. </p>

<p>On Windows Server 2003, a registry value to set ReadAheadGranularity is not exposed and RDBSS defaults to 32K (8 4K PAGE_SIZE pages). This is the same default value adopted for local files systems.</p>

<p><b>RxDriverEntry</b> retrieves a pointer to the kernel process that is running by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff559933">PsGetCurrentProcess</a> and stores this value in an internal RDBSS data structure. This kernel process is sometimes called the file system process.</p>

<p><b>RxDriverEntry</b> then copies a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554468">RxFsdDispatch</a> routine over all of the entries in the driver dispatch table. So if a monolithic network mini-redirector driver needs to receive specific IRPs for special processing before the RDBSS library, then a copy of its original driver dispatch table should be saved before calling <b>RxDriverEntry</b> and any routine pointers restored after the call to <b>RxDriverEntry</b> has returned. Note that RDBSS will also copy <b>RxFsdDispatch</b> to all the driver dispatch table entries when <a href="https://msdn.microsoft.com/library/windows/hardware/ff554693">RxRegisterMiniRdr</a> is called unless an option is set to prevent this behavior..</p>

<p>For a non-monolithic network mini-redirector driver (the Microsoft SMB redirector), the RDBSS.SYS device driver is initialized in its own <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine when loaded which internally calls <b>RxDriverEntry</b>. On a monolithic driver, the <b>RxDriverEntry</b> routine is exported from the RDBSSLIB.LIB static library and must be called explicitly by the network mini-redirector. </p>

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
<dt>Rxprocs.h (include Rxprocs.h)</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539224">CcSetReadAheadGranularity</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559933">PsGetCurrentProcess</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554693">RxRegisterMinirdr</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554718">RxSetDomainForMailslotBroadcast</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554736">RxStartMinirdr</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554743">RxStopMinirdr</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554662">RxpUnregisterMinirdr</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554744">RxUnregisterMinirdr</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557374">__RxFillAndInstallFastIoDispatch</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxDriverEntry routine%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>