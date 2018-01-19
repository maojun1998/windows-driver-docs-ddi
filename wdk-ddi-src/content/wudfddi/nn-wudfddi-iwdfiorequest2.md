---
UID : NN:wudfddi.IWDFIoRequest2
title : IWDFIoRequest2
author : windows-driver-content
description : To obtain the IWDFIoRequest2 interface, drivers call IWDFIoRequest::QueryInterface.
old-location : wdf\iwdfiorequest2.htm
old-project : wdf
ms.assetid : 6a6285c9-8366-4487-a1c5-38aa24d172a9
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : IWDFWorkItem, IWDFWorkItem::GetParentObject, GetParentObject
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : interface
req.header : wudfddi.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 1.9
req.alt-api : IWDFIoRequest2
req.alt-loc : WUDFx.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : Unavailable in UMDF 2.0 and later.
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : WUDFx.dll
req.irql : 
req.typenames : "*PPOWER_ACTION, POWER_ACTION"
req.product : Windows 10 or later.
---

# IWDFIoRequest2 interface

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

To obtain the <b>IWDFIoRequest2</b> interface, drivers call <b>IWDFIoRequest::QueryInterface</b>.

## Methods

<p>The <b>IWDFIoRequest2</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [wudfddi.IWDFIoRequest2.GetCreateParametersEx](nf-wudfddi-iwdfiorequest2-getcreateparametersex.md) | The GetCreateParametersEx method retrieves file creation parameters that are associated with a file that is being created or opened. |
| [wudfddi.IWDFIoRequest2.GetEffectiveIoType](nf-wudfddi-iwdfiorequest2-geteffectiveiotype.md) | The GetEffectiveIoType method returns the buffer access method that UMDF is using for the data buffers of the I/O request that the IWDFIoRequest2 interface represents. |
| [wudfddi.IWDFIoRequest2.GetQueryInformationParameters](nf-wudfddi-iwdfiorequest2-getqueryinformationparameters.md) | The GetQueryInformationParameters method retrieves parameters that are associated with a WdfRequestQueryInformation-typed I/O request. |
| [wudfddi.IWDFIoRequest2.GetRequestorMode](nf-wudfddi-iwdfiorequest2-getrequestormode.md) | The GetRequestorMode method indicates whether an I/O request came from a kernel-mode driver or a user-mode component (either an application or a user-mode driver). |
| [wudfddi.IWDFIoRequest2.GetSetInformationParameters](nf-wudfddi-iwdfiorequest2-getsetinformationparameters.md) | The GetSetInformationParameters method retrieves parameters that are associated with a WdfRequestSetInformation-typed I/O request. |
| [wudfddi.IWDFIoRequest2.GetStatus](nf-wudfddi-iwdfiorequest2-getstatus.md) | The GetStatus method returns the status of an I/O request. |
| [wudfddi.IWDFIoRequest2.IsCanceled](nf-wudfddi-iwdfiorequest2-iscanceled.md) | The IsCanceled method determines whether the I/O manager has attempted to cancel an I/O request. |
| [wudfddi.IWDFIoRequest2.IsFromUserModeDriver](nf-wudfddi-iwdfiorequest2-isfromusermodedriver.md) | The IsFromUserModeDriver method indicates whether an I/O request came from a user-mode driver or an application. |
| [wudfddi.IWDFIoRequest2.Requeue](nf-wudfddi-iwdfiorequest2-requeue.md) | The Requeue method returns an I/O request to the head of the I/O queue from which it was delivered to the driver. |
| [wudfddi.IWDFIoRequest2.RetrieveInputBuffer](nf-wudfddi-iwdfiorequest2-retrieveinputbuffer.md) | The RequestRetrieveInputBuffer method retrieves an I/O request's input buffer. |
| [wudfddi.IWDFIoRequest2.RetrieveInputMemory](nf-wudfddi-iwdfiorequest2-retrieveinputmemory.md) | The RetrieveInputMemory method retrieves the IWDFMemory interface of a framework memory object that represents an I/O request's input buffer. |
| [wudfddi.IWDFIoRequest2.RetrieveOutputBuffer](nf-wudfddi-iwdfiorequest2-retrieveoutputbuffer.md) | The RequestRetrieveOutputBuffer method retrieves an I/O request's output buffer. |
| [wudfddi.IWDFIoRequest2.RetrieveOutputMemory](nf-wudfddi-iwdfiorequest2-retrieveoutputmemory.md) | The RetrieveOutputMemory method retrieves the IWDFMemory interface of a framework memory object that represents an I/O request's output buffer. |
| [wudfddi.IWDFIoRequest2.Reuse](nf-wudfddi-iwdfiorequest2-reuse.md) | The Reuse method reinitializes a framework request object so that it can be reused. |
| [wudfddi.IWDFIoRequest2.StopAcknowledge](nf-wudfddi-iwdfiorequest2-stopacknowledge.md) | The StopAcknowledge method informs the framework that the driver has stopped processing a specified I/O request. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum UMDF version** | 1.9 |
| **Header** | wudfddi.h |
| **DLL** | WUDFx.dll |