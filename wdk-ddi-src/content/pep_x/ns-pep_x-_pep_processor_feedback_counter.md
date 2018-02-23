---
UID: NS:pep_x._PEP_PROCESSOR_FEEDBACK_COUNTER
title: "_PEP_PROCESSOR_FEEDBACK_COUNTER"
author: windows-driver-content
description: The PEP_PROCESSOR_FEEDBACK_COUNTER structure describes a feedback counter to the operating system.
old-location: kernel\pep_processor_feedback_counter.htm
old-project: kernel
ms.assetid: 275AE285-6309-4A03-A02C-DBE8D44727CE
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PPEP_PROCESSOR_FEEDBACK_COUNTER, *PPEP_PROCESSOR_FEEDBACK_COUNTER, PROCESSOR_FEEDBACK_TYPE_INSTANTANEOUS, PROCESSOR_FEEDBACK_COUNTER_PERFORMANCE, pepfx/PPEP_PROCESSOR_FEEDBACK_COUNTER, PROCESSOR_FEEDBACK_COUNTER_FREQUENCY, PROCESSOR_FEEDBACK_TYPE_RELATIVE, PEP_PROCESSOR_FEEDBACK_COUNTER structure [Kernel-Mode Driver Architecture], PEP_PROCESSOR_FEEDBACK_COUNTER, pepfx/PEP_PROCESSOR_FEEDBACK_COUNTER, kernel.pep_processor_feedback_counter, _PEP_PROCESSOR_FEEDBACK_COUNTER, PPEP_PROCESSOR_FEEDBACK_COUNTER structure pointer [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_PROCESSOR_FEEDBACK_COUNTER
product: Windows
targetos: Windows
req.typenames: "*PPEP_PROCESSOR_FEEDBACK_COUNTER, PEP_PROCESSOR_FEEDBACK_COUNTER"
---

# _PEP_PROCESSOR_FEEDBACK_COUNTER structure
The <b>PEP_PROCESSOR_FEEDBACK_COUNTER</b> structure describes a feedback counter to the operating system.

## Syntax
````
typedef struct _PEP_PROCESSOR_FEEDBACK_COUNTER {
  struct {
    ULONG Affinitized  :1;
    ULONG Type  :2;
    ULONG Counter  :4;
    ULONG Reserved  :25;
  };
  ULONG  NominalRate;
} PEP_PROCESSOR_FEEDBACK_COUNTER, *PPEP_PROCESSOR_FEEDBACK_COUNTER;
````

## Members


`NominalRate`

Specifies the nominal rate of the counter.

## Remarks
This structure

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pep_x.h (include Pep_x.h) |

## See Also

<a href="https://msdn.microsoft.com/478E1AB1-B888-4EC2-A9C3-A33475E499E3">PEP structures</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186825">PEP_NOTIFY_PPM_QUERY_PERF_CAPABILITIES notification</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PROCESSOR_FEEDBACK_COUNTER structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>