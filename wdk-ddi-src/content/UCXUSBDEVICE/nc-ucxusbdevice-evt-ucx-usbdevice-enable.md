---
UID: NC.ucxusbdevice.EVT_UCX_USBDEVICE_ENABLE
title: EVT_UCX_USBDEVICE_ENABLE
author: windows-driver-content
description: 
ms.assetid: 5a400871-58c4-447d-b20f-5a4df051ccb1
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: ucxusbdevice.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
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

# EVT_UCX_USBDEVICE_ENABLE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

EVT_UCX_USBDEVICE_ENABLE EvtUcxUsbdeviceEnable; 

// Definition

VOID EvtUcxUsbdeviceEnable 
(
	UCXCONTROLLER UcxController
	WDFREQUEST Request
)
{...}

EVT_UCX_USBDEVICE_ENABLE PFN_UCX_USBDEVICE_ENABLE


```

## -parameters

### -param UcxController: 
### -param Request: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also