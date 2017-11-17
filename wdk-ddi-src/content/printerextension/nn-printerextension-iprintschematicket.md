---
UID: NN.printerextension.IPrintSchemaTicket
title: IPrintSchemaTicket
author: windows-driver-content
description: Provides the primary method to access and validate a PrintTicket.
old-location: print\iprintschematicket_interface.htm
ms.assetid: 190B0B88-6018-4B43-8699-78427421D6FF
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: interface
ms.prod: windows-hardware
ms.technology: print
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintSchemaTicket
req.alt-loc: Printerextension.h
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
ms.keywords: IPrintSchemaTicket2, GetParameterInitializer, IPrintSchemaTicket2::GetParameterInitializer
req.iface: IPrintSchemaTicket2
req.product: Windows 10 or later.
---

# IPrintSchemaTicket interface



## -description
<p>Provides the primary method to access and validate a PrintTicket.</p>


## -inheritance
<p>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaTicket</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/hh451270">IPrintSchemaElement</a>. <b>IPrintSchemaTicket</b> also has these types of members:</p>

<p>The <b>IPrintSchemaTicket</b> interface has these methods.</p>

<p>Gets an  asynchronous PrintTicket commit operation context.</p>

<p>Gets an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451256">IPrintSchemaCapabilities</a> object that represents the printer capabilities based on the current settings of this <b>IPrintSchemaTicket</b> object.</p>

<p>Gets a named feature from the PrintTicket, by name and full namespace URI.</p>

<p>Gets a feature from the PrintTicket based on the specified key name.</p>

<p>Notifies the print system that the XML DOM object has changed.</p>

<p>Gets an asynchronous PrintTicket validation operation context.</p>

<p> </p>

<p>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaTicket</b> interface has these properties.</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh973238">JobCopiesAllDocuments</a>
</p>

<p>Read-only</p>

<p>Gets the copy count.</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh973238">JobCopiesAllDocuments</a>
</p>

<p>Write-only</p>

<p>Sets the copy count.</p>

<p> </p>

## -members
<p>The <b>IPrintSchemaTicket</b> interface has these methods.</p><table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451382">CommitAsync</a>
</td>
<td align="left" width="63%">
<p>Gets an  asynchronous PrintTicket commit operation context.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451391">GetCapabilities</a>
</td>
<td align="left" width="63%">
<p>Gets an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451256">IPrintSchemaCapabilities</a> object that represents the printer capabilities based on the current settings of this <b>IPrintSchemaTicket</b> object.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451385">GetFeature</a>
</td>
<td align="left" width="63%">
<p>Gets a named feature from the PrintTicket, by name and full namespace URI.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451388">GetFeatureByKeyName</a>
</td>
<td align="left" width="63%">
<p>Gets a feature from the PrintTicket based on the specified key name.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh846202">NotifyXmlChanged</a>
</td>
<td align="left" width="63%">
<p>Notifies the print system that the XML DOM object has changed.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451448">ValidateAsync</a>
</td>
<td align="left" width="63%">
<p>Gets an asynchronous PrintTicket validation operation context.</p>
</td>
</tr>
</table><p>Gets an  asynchronous PrintTicket commit operation context.</p>

<p>Gets an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451256">IPrintSchemaCapabilities</a> object that represents the printer capabilities based on the current settings of this <b>IPrintSchemaTicket</b> object.</p>

<p>Gets a named feature from the PrintTicket, by name and full namespace URI.</p>

<p>Gets a feature from the PrintTicket based on the specified key name.</p>

<p>Notifies the print system that the XML DOM object has changed.</p>

<p>Gets an asynchronous PrintTicket validation operation context.</p>

<p> </p>

<p>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaTicket</b> interface has these properties.</p><table class="members" id="memberListProperties">
<tr>
<th align="left" width="27%">Property</th>
<th align="left" width="10%">Access type</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh973238">JobCopiesAllDocuments</a>
</p>
</td>
<td align="left" width="10%">
<p>Read-only</p>
</td>
<td align="left" width="63%">
<p>Gets the copy count.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh973238">JobCopiesAllDocuments</a>
</p>
</td>
<td align="left" width="10%">
<p>Write-only</p>
</td>
<td align="left" width="63%">
<p>Sets the copy count.</p>
</td>
</tr>
</table><p>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh973238">JobCopiesAllDocuments</a>
</p>

<p>Read-only</p>

<p>Gets the copy count.</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh973238">JobCopiesAllDocuments</a>
</p>

<p>Write-only</p>

<p>Sets the copy count.</p>

<p> </p>

## -remarks
<p>To obtain an IXMLDOMDocument2 object for the PrintTicket object, you must first dereference the <i>ppXmlNode</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh969196">XmlNode</a> property (using *ppXmlNode ). This retrieves a pointer to an interface of type <b>IUnknown</b>. Use this pointer to  call the <b>QueryInterface</b> method of the PrintTicket object to access the underlying  IXMLDOMDocument2 object.</p>

<p>To obtain an IXMLDOMDocument2 object for the PrintTicket object, you must first dereference the <i>ppXmlNode</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh969196">XmlNode</a> property (using *ppXmlNode ). This retrieves a pointer to an interface of type <b>IUnknown</b>. Use this pointer to  call the <b>QueryInterface</b> method of the PrintTicket object to access the underlying  IXMLDOMDocument2 object.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Printerextension.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451270">IPrintSchemaElement</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/B1599F21-D6DD-497D-9CD8-6C637ABAA33A">IPrintSchemaAsyncOperationEvent::Completed</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451256">IPrintSchemaCapabilities</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/5E7F2292-1F71-4581-8E34-86F1464EC08F">IPrintSchemaElement::XmlNode</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaTicket interface%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>