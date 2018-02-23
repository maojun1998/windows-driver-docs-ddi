---
UID: NN:ksproxy.IKsPropertySet
title: IKsPropertySet
author: windows-driver-content
description: The IKsPropertySet interface provides methods that access properties of KS objects that are implemented in a KS minidriver.
old-location: stream\ikspropertyset.htm
old-project: stream
ms.assetid: 9999d6ec-977c-4425-ad38-0c5478272c76
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: stream.ikspropertyset, IKsPropertySet interface [Streaming Media Devices], IKsPropertySet interface [Streaming Media Devices], described, IKsPropertySet, dsound/IKsPropertySet, ksproxy_5f6316c6-5bcf-4155-b4a5-976a0cee8aa5.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Windows
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
req.lib: Ksproxy.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dsound.h
apiname:
-	IKsPropertySet
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsPropertySet interface

The <b>IKsPropertySet</b> interface provides methods that access properties of KS objects that are implemented in a KS minidriver.

The IID for this interface is IID_IKsPropertySet.
<div class="alert"><b>Note</b>    Header files <i>ksproxy.h</i> and <i>dsound.h</i> define similar but incompatible versions of the <b>IKsPropertySet</b> interface. Applications that require the KS proxy module should use the version defined in <i>ksproxy.h</i>. The DirectSound version of <b>IKsPropertySet</b> is described in the DirectSound reference pages in the Microsoft Windows SDK documentation.<p class="note">If an application must include both <i>ksproxy.h</i> and <i>dsound.h</i>, whichever header file the compiler scans first is the one whose definition of <b>IKsPropertySet</b> is used by the compiler.

</div><div> </div>

## Methods

<p>The <b>IKsPropertySet</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [ksproxy.IKsPropertySet.Get](nf-ksproxy-ikspropertyset-get.md) | The Get method retrieves a property identified by a property-set GUID and a property identifier. |
| [ksproxy.IKsPropertySet.QuerySupported](nf-ksproxy-ikspropertyset-querysupported.md) | The QuerySupported method determines whether a KS object supports a property set and the type of that support. |
| [ksproxy.IKsPropertySet.Set](nf-ksproxy-ikspropertyset-set.md) | The Set method sets a property identified by a property-set GUID and a property identifier. |

## Remarks

The <b>IKsPropertySet</b> interface methods translate user-mode property requests into kernel-mode property sets that are used by KS minidrivers. 

KS objects include, for example, KS filters, KS pins, and KS clocks.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ksproxy.h (include Ksproxy.h) |