---
UID: NS.storport._DESCRIPTOR_SENSE_DATA
title: DESCRIPTOR_SENSE_DATA
author: windows-driver-content
description: 
ms.assetid: 45145635-eded-4443-a83a-f79353c11a62
ms.author: windowsdriverdev
ms.date: 
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: DESCRIPTOR_SENSE_DATA, DESCRIPTOR_SENSE_DATA, *PDESCRIPTOR_SENSE_DATA
req.header: storport.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.alt-api:
req.alt-loc:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
---

# DESCRIPTOR_SENSE_DATA structure

## -description



## -struct-fields

### -field UCHAR  : 7 ErrorCode			
 	
### -field UCHAR  : 1 Reserved1			
 	
### -field UCHAR  : 4 SenseKey			
 	
### -field UCHAR  : 4 Reserved2			
 	
### -field UCHAR AdditionalSenseCode			
 	
### -field UCHAR AdditionalSenseCodeQualifier			
 	
### -field UCHAR [3] Reserved3			
 	
### -field UCHAR AdditionalSenseLength			
 	
### -field UCHAR [ANYSIZE_ARRAY] DescriptorBuffer			
 	
## -remarks

## -see-also