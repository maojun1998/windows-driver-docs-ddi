---
UID: NS:ks.KSATTRIBUTE
title: KSATTRIBUTE
author: windows-driver-content
description: The KSATTRIBUTE structure defines an additional attribute of a data format or data range that is not covered by the KSDATAFORMAT and KSDATARANGE structures or the extended information based on the format and range specifiers.
old-location: stream\ksattribute.htm
old-project: stream
ms.assetid: 985d9f12-11c6-40e6-9cb6-572196bc04f4
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSATTRIBUTE, KSATTRIBUTE, KSATTRIBUTE structure [Streaming Media Devices], PKSATTRIBUTE, PKSATTRIBUTE structure pointer [Streaming Media Devices], ks-struct_02cb064e-813f-4d67-8cf3-a33e05af7421.xml, ks/KSATTRIBUTE, ks/PKSATTRIBUTE, stream.ksattribute"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSATTRIBUTE
product:
- Windows
targetos: Windows
req.typenames: KSATTRIBUTE, *PKSATTRIBUTE
---

# KSATTRIBUTE structure


## -description


The KSATTRIBUTE structure defines an additional attribute of a data format or data range that is not covered by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561656">KSDATAFORMAT</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff561658">KSDATARANGE</a> structures or the extended information based on the format and range specifiers.


## -struct-fields




### -field Size

Specifies the size of the attribute. This is at least the size of the KSATTRIBUTE structure and may be more if there is extended information based on the identifying GUID in the <b>Attribute</b> field.


### -field Flags

Specifies the flags of the attribute. The only used flag is KSATTRIBUTE_REQUIRED; this flag specifies that an attribute is required. If this flag is not set, the attribute is optional. Note that the topmost bit is reserved for internal use in KS.


### -field Attribute

Specifies the unique identifier of the attribute.


## -remarks



Note that KSATTRIBUTE is used in conjunction with data formats and data ranges; attributes on data formats and ranges are taken into consideration when determining if a data format is acceptable to a given pin or if a data range intersects with another data range.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561656">KSDATAFORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561658">KSDATARANGE</a>
 

 

