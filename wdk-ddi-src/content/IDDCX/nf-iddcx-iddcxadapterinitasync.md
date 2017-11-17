---
UID: NF.iddcx.IddCxAdapterInitAsync
title: IddCxAdapterInitAsync
author: windows-driver-content
description: An asynchronous initiation function called by the driver to create a WDDM graphics adapter.
old-location: display\iddcxadapterinitasync.htm
ms.assetid: c23d0d24-b043-4e39-afd3-abab6bb84769
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: display
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IddCxAdapterInitAsync
req.alt-loc: iddcx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: _Must_inspect_result_
ms.keywords: IddCxAdapterInitAsync
req.iface: 
---

# IddCxAdapterInitAsync function



## -description
<p>An asynchronous initiation function called by the driver to create a WDDM graphics adapter.

                </p>


## -syntax

````
NTSTATUS IddCxAdapterInitAsync(
  _In_  const IDARG_IN_ADAPTER_INIT*  pInArgs,
  _Out_       IDARG_OUT_ADAPTER_INIT* pOutArgs
);
````


## -parameters
<dl>

### -param <i>pInArgs</i> [in]

<dd>
<p>Input arguments to the function</p>
</dd>

### -param <i>pOutArgs</i> [out]

<dd>
<p>Output arguments to the function</p>
</dd>
</dl>

## -returns
<p>
(NTSTATUS) The method returns S_OK if the operation succeeds. Otherwise, this method returns an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.
                    </p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Iddcx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>_Must_inspect_result_</p>
</td>
</tr>
</table>