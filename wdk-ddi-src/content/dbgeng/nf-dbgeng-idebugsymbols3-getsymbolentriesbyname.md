---
UID: NF:dbgeng.IDebugSymbols3.GetSymbolEntriesByName
title: IDebugSymbols3::GetSymbolEntriesByName method
author: windows-driver-content
description: The GetSymbolEntriesByName method returns the symbols whose names match a given pattern.
old-location: debugger\getsymbolentriesbyname.htm
old-project: debugger
ms.assetid: 90e6c1aa-30d5-40e7-bc35-92b0359485e0
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetSymbolEntriesByName method [Windows Debugging], GetSymbolEntriesByName method [Windows Debugging], IDebugSymbols3 interface, GetSymbolEntriesByName,IDebugSymbols3.GetSymbolEntriesByName, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetSymbolEntriesByName method, IDebugSymbols3::GetSymbolEntriesByName, IDebugSymbols_4c157d74-d5e8-43d5-87f9-5ad089adb4a0.xml, dbgeng/IDebugSymbols3::GetSymbolEntriesByName, debugger.getsymbolentriesbyname
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugSymbols3.GetSymbolEntriesByName
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::GetSymbolEntriesByName method


## -description


The <b>GetSymbolEntriesByName</b>  method returns the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">symbols</a> whose names match a given pattern.


## -parameters




### -param Symbol [in]

Specifies the pattern used to determine which symbols to return.  This method returns the symbols whose name matches the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558819">string wildcard syntax</a> pattern <i>Symbol</i>.


### -param Flags [in]

Set to zero.


### -param Ids [out, optional]

Receives the symbols.  This is an array of <i>IdsCount</i> entries of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff541511">DEBUG_MODULE_AND_ID</a>.  If <i>Ids</i> is <b>NULL</b>, this information is not returned.


### -param IdsCount [in]

Specifies the number of entries that the array <i>Ids</i> can hold.


### -param Entries [out, optional]

Receives the number of symbols whose names match the pattern <i>Symbol</i>.  If <i>entries</i> is <b>NULL</b>, this information is not returned.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>
 




## -remarks



For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548476">GetSymbolEntriesByOffset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

