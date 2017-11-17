# Declarations in the print technology
This technology  contains these programming interfaces:

Function

| Title        | Description    |
| ------------- |:-------------:|
| [IBidiRequestContainer::GetEnumObject method](..\bidispl\nf-bidispl-ibidirequestcontainer-getenumobject.md) | The IBidiRequestContainer |
| [IBidiSpl::UnbindDevice method](..\bidispl\nf-bidispl-ibidispl-unbinddevice.md) | The IBidiSpl |
| [IBidiRequest::GetEnumCount method](..\bidispl\nf-bidispl-ibidirequest-getenumcount.md) | The IBidiRequest |
| [IBidiSpl2::UnbindDevice method](..\bidispl\nf-bidispl-ibidispl2-unbinddevice.md) | The IBidiSpl2 |
| [IBidiRequest::SetSchema method](..\bidispl\nf-bidispl-ibidirequest-setschema.md) | The IBidiRequest |
| [IBidiSpl2::SendRecvXMLString method](..\bidispl\nf-bidispl-ibidispl2-sendrecvxmlstring.md) | The IBidiSpl2 |
| [IBidiRequestContainer::AddRequest method](..\bidispl\nf-bidispl-ibidirequestcontainer-addrequest.md) | The IBidiRequestContainer |
| [IBidiRequestContainer::GetRequestCount method](..\bidispl\nf-bidispl-ibidirequestcontainer-getrequestcount.md) | The IBidiRequestContainer |
| [IBidiSpl::SendRecv method](..\bidispl\nf-bidispl-ibidispl-sendrecv.md) | The IBidiSpl |
| [IBidiSpl2::SendRecvXMLStream method](..\bidispl\nf-bidispl-ibidispl2-sendrecvxmlstream.md) | The IBidiSpl2 |
| [IBidiRequest::GetOutputData method](..\bidispl\nf-bidispl-ibidirequest-getoutputdata.md) | The IBidiRequest |
| [IBidiSpl2::BindDevice method](..\bidispl\nf-bidispl-ibidispl2-binddevice.md) | The IBidiSpl2 |
| [IBidiSpl::MultiSendRecv method](..\bidispl\nf-bidispl-ibidispl-multisendrecv.md) | The IBidiSpl |
| [IBidiSpl::BindDevice method](..\bidispl\nf-bidispl-ibidispl-binddevice.md) | The IBidiSpl |
| [IBidiRequest::SetInputData method](..\bidispl\nf-bidispl-ibidirequest-setinputdata.md) | The IBidiRequest |
| [IBidiRequest::GetResult method](..\bidispl\nf-bidispl-ibidirequest-getresult.md) | The IBidiRequest |
Interface

| Title        | Description    |
| ------------- |:-------------:|
| [IBidiRequestContainer interface](..\bidispl\nn-bidispl-ibidirequestcontainer~r1.md) | The IBidiRequestContainer interface allows an application or other objects to compose and retrieve a list of bidi requests. |
| [IBidiRequestContainer interface](..\bidispl\nn-bidispl-ibidirequestcontainer.md) | The IBidiRequestContainer interface allows an application or other objects to compose and retrieve a list of bidi requests. |
| [IBidiSpl2 interface](..\bidispl\nn-bidispl-ibidispl2.md) | The IBidiSpl2 interface enables an application or other objects to send one or more bidi requests using one of the Bidi Request Schemas and receive information formatted as one of the Bidi Response Schemas. |
| [IBidiSpl2 interface](..\bidispl\nn-bidispl-ibidispl2~r1.md) | The IBidiSpl2 interface enables an application or other objects to send one or more bidi requests using one of the Bidi Request Schemas and receive information formatted as one of the Bidi Response Schemas. |
| [IBidiRequest interface](..\bidispl\nn-bidispl-ibidirequest.md) | The IBidiRequest interface allows an application or other objects to compose a bidi request. |
| [IBidiSpl interface](..\bidispl\nn-bidispl-ibidispl~r1.md) | The IBidiSpl interface allows an application or other objects to send a single bidi request or a list of bidi requests. |
| [IBidiRequest interface](..\bidispl\nn-bidispl-ibidirequest~r1.md) | The IBidiRequest interface allows an application or other objects to compose a bidi request. |
| [IBidiSpl interface](..\bidispl\nn-bidispl-ibidispl.md) | The IBidiSpl interface allows an application or other objects to send a single bidi request or a list of bidi requests. |
Function

| Title        | Description    |
| ------------- |:-------------:|
| [SetCPSUIUserData function](..\compstui\nf-compstui-setcpsuiuserdata.md) | CPSUI's SetCPSUIUserData function allows CPSUI applications (including printer interface DLLs) to associate nondisplayed data with a property sheet dialog box. |
| [GetCPSUIUserData function](..\compstui\nf-compstui-getcpsuiuserdata.md) | CPSUI's GetCPSUIUserData function retrieves data that was previously stored using the SetCPSUIUserData function. |
Struct

| Title        | Description    |
| ------------- |:-------------:|
| [SETRESULT_INFO structure](..\compstui\ns-compstui--setresult-info.md) | The SETRESULT_INFO structure is used as an input parameter to an application's PFNPROPSHEETUI-typed callback function. |
| [OIEXT structure](..\compstui\ns-compstui--oiext.md) | The OIEXT structure supplies additional, optional information about a property sheet page option that is described by an OPTITEM structure. |
| [EXTCHKBOX structure](..\compstui\ns-compstui--extchkbox.md) | The EXTCHKBOX structure is used by CPSUI applications (including printer interface DLLs) for specifying an extended check box, which can be added to a property sheet page option. |
| [DLGPAGE structure](..\compstui\ns-compstui--dlgpage.md) | The DLGPAGE structure is used for specifying a property sheet page to CPSUI's ComPropSheet function. The structure's address is included in a COMPROPSHEETUI structure, and all member values are supplied by the ComPropSheet caller. |
| [PSPINFO structure](..\compstui\ns-compstui--pspinfo.md) | The PSPINFO structure is used as an input parameter to a property sheet page's dialog box procedure, when the Windows message is WM_INITDIALOG. The dialog box procedure's address is specified in a DLGPAGE structure. |
| [OPTPARAM structure](..\compstui\ns-compstui--optparam.md) | An array of OPTPARAM structures is used by CPSUI applications (including printer interface DLLs) for describing all the parameter values associated with a property sheet option. The array's address is included in an OPTTYPE structure. |
| [COMPROPSHEETUI structure](..\compstui\ns-compstui--compropsheetui.md) | The COMPROPSHEETUI structure is used as an input parameter to CPSUI's ComPropSheet function, if the function code is CPSFUNC_ADD_PCOMPROPSHEETUI. All structure members must be supplied by the caller of ComPropSheet. |
| [PROPSHEETUI_INFO structure](..\compstui\ns-compstui--propsheetui-info.md) | The PROPSHEETUI_INFO structure is used as an input parameter to PFNPROPSHEETUI-typed functions. |
| [PROPSHEETUI_INFO_HEADER structure](..\compstui\ns-compstui--propsheetui-info-header.md) | The PROPSHEETUI_INFO_HEADER structure is used as an input parameter to an application's PFNPROPSHEETUI-typed function, when the function is called with a reason value of PROPSHEETUI_REASON_GET_INFO_HEADER. |
| [OPTTYPE structure](..\compstui\ns-compstui--opttype.md) | The OPTTYPE structure is used by CPSUI applications (including printer interface DLLs) for describing the type and other characteristics of a property sheet option, if the option is specified by an OPTITEM structure. |
| [CPSUIDATABLOCK structure](..\compstui\ns-compstui--cpsuidatablock.md) | The CPSUIDATABLOCK structure is used as a parameter for the ComPropSheet function, if the function code is CPSFUNC_SET_DATABLOCK or CPSFUNC_QUERY_DATABLOCK. |
| [EXTPUSH structure](..\compstui\ns-compstui--extpush.md) | The EXTPUSH structure is used by CPSUI applications (including printer interface DLLs) for specifying an extended push button, which can be added to a property sheet page option. When the button is pushed, a new dialog can be displayed. |
| [OPTCOMBO structure](..\compstui\ns-compstui--optcombo.md) | TBD. |
| [PROPSHEETUI_GETICON_INFO structure](..\compstui\ns-compstui--propsheetui-geticon-info.md) | The PROPSHEETUI_GETICON_INFO structure is used as an input parameter to an application's PFNPROPSHEETUI-typed function, when the function is called with a reason value of PROPSHEETUI_REASON_GET_ICON. |
| [INSERTPSUIPAGE_INFO structure](..\compstui\ns-compstui--insertpsuipage-info.md) | The INSERTPSUIPAGE_INFO structure is used as an input parameter to CPSUI's ComPropSheet function, if the function code is CPSFUNC_INSERT_PSUIPAGE. All member values must be supplied by the ComPropSheet caller. |
| [OPTITEM structure](..\compstui\ns-compstui--optitem.md) | The OPTITEM structure is used by CPSUI applications (including printer interface DLLs) for describing one property sheet option on a property sheet page, if the page is described by a COMPROPSHEETUI structure. |
| [CPSUICBPARAM structure](..\compstui\ns-compstui--cpsuicbparam.md) | The CPSUICBPARAM structure is used as the input parameter to _CPSUICALLBACK-typed callback functions. |
Function

| Title        | Description    |
| ------------- |:-------------:|
| [IXpsPartIterator::Reset method](..\filterpipeline\nf-filterpipeline-ixpspartiterator-reset.md) | The Reset method sets the iterator to the first element. |
| [DrvPopulateFilterServices function](..\filterpipeline\nf-filterpipeline-drvpopulatefilterservices.md) | The DrvPopulateFilterServices function is called by the XPSDrv filter pipeline manager to allow the service provider to instantiate filter service objects in the filter pipeline property bag specified by the pPropertyBag parameter. |
| [IXpsPartIterator::Next method](..\filterpipeline\nf-filterpipeline-ixpspartiterator-next.md) | The Next method advances the iterator to the next part. |
| [IXpsPartIterator::IsDone method](..\filterpipeline\nf-filterpipeline-ixpspartiterator-isdone.md) | The IsDone method determines whether the iterator has finished the iteration. |
| [IPrintPipelineFilter::StartOperation method](..\filterpipeline\nf-filterpipeline-iprintpipelinefilter-startoperation.md) | The StartOperation method starts the operation of a filter. The filter reads, processes, and writes data in this method. |
| [IPrintPipelineFilter::ShutdownOperation method](..\filterpipeline\nf-filterpipeline-iprintpipelinefilter-shutdownoperation.md) | The Pipeline Manager uses the ShutdownOperation method to shut down a filter if the print job is canceled or an error occurs. |
| [IXpsDocumentConsumer::CloseSender method](..\filterpipeline\nf-filterpipeline-ixpsdocumentconsumer-closesender.md) | The CloseSender method tells the Pipeline Manager that the filter is done sending XPS parts. |
| [IPrintWriteStream::Close method](..\filterpipeline\nf-filterpipeline-iprintwritestream-close.md) | The Close method closes a stream and ends the writing to that stream. This method is mandatory. You must call this method when the filter is done writing. |
| [IPartFont2::GetFontRestriction method](..\filterpipeline\nf-filterpipeline-ipartfont2-getfontrestriction.md) | TBD. |
| [IPrintPipelineManagerControl::FilterFinished method](..\filterpipeline\nf-filterpipeline-iprintpipelinemanagercontrol-filterfinished.md) | The FilterFinished method reports that a filter is finished processing. |
Interface

| Title        | Description    |
| ------------- |:-------------:|
| [IPartFont2 interface](..\filterpipeline\nn-filterpipeline-ipartfont2~r1.md) | TBD. |
| [IPartFont2 interface](..\filterpipeline\nn-filterpipeline-ipartfont2.md) | TBD. |
Function

| Title        | Description    |
| ------------- |:-------------:|
| [WcsEnumColorProfiles function](..\icm\nf-icm-wcsenumcolorprofiles.md) | The WcsEnumColorProfiles function enumerates all color profiles that satisfy the enumeration criteria in the specified profile management scope. |
| [WcsGetUsePerUserProfiles function](..\icm\nf-icm-wcsgetuseperuserprofiles.md) | The WcsGetUsePerUserProfiles function determines whether the user has chosen to use a per-user profile association list for the specified device. |
| [WcsGetDefaultColorProfileSize function](..\icm\nf-icm-wcsgetdefaultcolorprofilesize.md) | The WcsGetDefaultColorProfileSize function returns the size, in bytes, of the default color profile name for a device, including the NULL terminator. |
| [WcsSetUsePerUserProfiles function](..\icm\nf-icm-wcssetuseperuserprofiles.md) | The WcsSetUsePerUserProfiles function allows the user to specify whether or not to use a per-user profile association list for the specified device. |
| [WcsSetDefaultColorProfile function](..\icm\nf-icm-wcssetdefaultcolorprofile.md) | The WcsSetDefaultColorProfile function sets the default color profile name of the specified profile type in the specified profile management scope. |
| [WcsCreateIccProfile function](..\icm\nf-icm-wcscreateiccprofile.md) | The WcsCreateIccProfile function converts a WCS profile into an ICC profile. |
| [WcsAssociateColorProfileWithDevice function](..\icm\nf-icm-wcsassociatecolorprofilewithdevice.md) | The WcsAssociateColorProfileWithDevice function associates a specified WCS color profile with a specified device. |
| [WcsGetDefaultColorProfile function](..\icm\nf-icm-wcsgetdefaultcolorprofile.md) | The WcsGetDefaultColorProfile function retrieves the default color profile for a device, or the device-independent default if the device is not specified. |
| [WcsTranslateColors function](..\icm\nf-icm-wcstranslatecolors.md) | The WcsTranslateColors function translates an array of colors from the source color space to the destination color space as defined by a color transform. |
| [WcsCheckColors function](..\icm\nf-icm-wcscheckcolors.md) | The WcsCheckColors function determines whether the colors in an array lie within the output gamut of a specified WCS color transform. |
| [WcsDisassociateColorProfileFromDevice function](..\icm\nf-icm-wcsdisassociatecolorprofilefromdevice.md) | The WcsDisassociateColorProfileFromDevice function disassociates a specified WCS color profile from a specified device. |
| [WcsEnumColorProfilesSize function](..\icm\nf-icm-wcsenumcolorprofilessize.md) | The WcsEnumColorProfilesSize function returns the size, in bytes, of the buffer required by the WcsEnumColorProfiles function to enumerate color profiles. |
Enum

| Title        | Description    |
| ------------- |:-------------:|
| [COLORDATATYPE enumeration](..\icm\ne-icm-colordatatype.md) | The values of the COLORDATATYPE enumeration are used by WCS functions to indicate the data type of vector content. |
| [COLORTYPE enumeration](..\icm\ne-icm-colortype.md) | The values of the COLORTYPE enumeration are used by WCS functions to indicate the format of vector content. Most values have equivalent structures that are contained in the ICM COLOR structure (described in the Microsoft Windows SDK documentation). |
| [COLORPROFILESUBTYPE enumeration](..\icm\ne-icm-colorprofilesubtype.md) | The COLORPROFILESUBTYPE enumeration is used to specify the subtype of color profile. |
| [BMFORMAT enumeration](..\icm\ne-icm-bmformat.md) | The values of the BMFORMAT enumeration are used by WCS functions to indicate the format that particular bitmaps are in. This data type is extended from BMFORMAT that is available in versions of Windows released before Windows Vista. |
| [WCS_PROFILE_MANAGEMENT_SCOPE enumeration](..\icm\ne-icm-wcs-profile-management-scope.md) | The WCS_PROFILE_MANAGEMENT_SCOPE enumeration is used to specify the scope of a profile management operation, such as associating a profile with a device. |
| [COLORPROFILETYPE enumeration](..\icm\ne-icm-colorprofiletype.md) | The COLORPROFILETYPE enumeration is used to specify the type of color profile. |
Function

| Title        | Description    |
| ------------- |:-------------:|
| [MxdcGetPDEVAdjustment function](..\mxdc\nf-mxdc-mxdcgetpdevadjustment.md) | The MxdcGetPDEVAdjustment function is exported by a printer interface DLL and supplies printer configuration data for the Microsoft XPS Document Converter (MXDC). |
Function

| Title        | Description    |
| ------------- |:-------------:|
| [IPrintOemUI::DriverEvent method](..\prcomoem\nf-prcomoem-iprintoemui-driverevent.md) | The printer driver's DrvDriverEvent function calls a user interface plug-in's IPrintOemUI |
| [IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace method](..\prcomoem\nf-prcomoem-iprintoemprintticketprovider-querydevicedefaultnamespace.md) | The IPrintOemPrintTicketProvider |
| [IPrintCorePS2::GetOptionAttribute method](..\prcomoem\nf-prcomoem-iprintcoreps2-getoptionattribute.md) | The IPrintCorePS2 |
| [IPrintOemPrintTicketProvider::ValidatePrintTicket method](..\prcomoem\nf-prcomoem-iprintoemprintticketprovider-validateprintticket.md) | The IPrintOemPrintTicketProvider |
| [IPrintCoreHelperPS::SetOptions method](..\prcomoem\nf-prcomoem-iprintcorehelperps-setoptions.md) | The IPrintCoreHelperPS |
| [IPrintCorePS2::DrvWriteSpoolBuf method](..\prcomoem\nf-prcomoem-iprintcoreps2-drvwritespoolbuf.md) | The IPrintCorePS2 |
| [IPrintOemUni::HalftonePattern method](..\prcomoem\nf-prcomoem-iprintoemuni-halftonepattern.md) | The IPrintOemUni |
| [IPrintCoreHelper::WhyConstrained method](..\prcomoem\nf-prcomoem-iprintcorehelper-whyconstrained.md) | The IPrintCoreHelper |
| [IPrintCoreUI2::SetOptions method](..\prcomoem\nf-prcomoem-iprintcoreui2-setoptions.md) | The IPrintCoreUI2 |
| [IPrintOemPS::DevMode method](..\prcomoem\nf-prcomoem-iprintoemps-devmode.md) | The IPrintOemPS |
| [IPrintOemUni::DownloadFontHeader method](..\prcomoem\nf-prcomoem-iprintoemuni-downloadfontheader.md) | The IPrintOemUni |
| [IPrintOemUIMXDC::AdjustDPI method](..\prcomoem\nf-prcomoem-iprintoemuimxdc-adjustdpi.md) | The IPrintOemUIMXDC |
| [IPrintOemUni::DevMode method](..\prcomoem\nf-prcomoem-iprintoemuni-devmode.md) | The IPrintOemUni |
| [IPrintCoreUI2::DrvGetDriverSetting method](..\prcomoem\nf-prcomoem-iprintcoreui2-drvgetdriversetting.md) | The IPrintCoreUI2 |
| [IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface method](..\prcomoem\nf-prcomoem-iprintoemprintticketprovider-publishprinttickethelperinterface.md) | The IPrintOemPrintTicketProvider |
| [IPrintCoreUI2::DrvUpgradeRegistrySetting method](..\prcomoem\nf-prcomoem-iprintcoreui2-drvupgraderegistrysetting.md) | The IPrintCoreUI2 |
| [IPrintOemDriverUni::DrvWriteAbortBuf method](..\prcomoem\nf-prcomoem-iprintoemdriveruni-drvwriteabortbuf.md) | The IPrintOemDriverUni |
| [IPrintCoreHelperPS::GetGlobalAttribute method](..\prcomoem\nf-prcomoem-iprintcorehelperps-getglobalattribute.md) | The IPrintCoreHelperPS |
| [IPrintOemUni::DownloadCharGlyph method](..\prcomoem\nf-prcomoem-iprintoemuni-downloadcharglyph.md) | The IPrintOemUni |
| [IPrintOemUI::PublishDriverInterface method](..\prcomoem\nf-prcomoem-iprintoemui-publishdriverinterface.md) | The IPrintOemUI |
| [IPrintOemPS::PublishDriverInterface method](..\prcomoem\nf-prcomoem-iprintoemps-publishdriverinterface.md) | The IPrintOemPS |
| [IPrintCoreHelper::EnumFeatures method](..\prcomoem\nf-prcomoem-iprintcorehelper-enumfeatures.md) | The IPrintCoreHelper |
| [IPrintCoreUI2::QuerySimulationSupport method](..\prcomoem\nf-prcomoem-iprintcoreui2-querysimulationsupport.md) | The IPrintCoreUI2 |
| [IPrintCoreHelper::EnumOptions method](..\prcomoem\nf-prcomoem-iprintcorehelper-enumoptions.md) | The IPrintCoreHelper |
| [IPrintOemEngine::DisableDriver method](..\prcomoem\nf-prcomoem-iprintoemengine-disabledriver.md) | TBD. |
| [IPrintCoreHelperUni::CreateGDLSnapshot method](..\prcomoem\nf-prcomoem-iprintcorehelperuni-creategdlsnapshot.md) | The IPrintCoreHelperUni |
| [IPrintOemUni::OutputCharStr method](..\prcomoem\nf-prcomoem-iprintoemuni-outputcharstr.md) | The IPrintOemUni |
| [IPrintOemDriverUI::DrvUpgradeRegistrySetting method](..\prcomoem\nf-prcomoem-iprintoemdriverui-drvupgraderegistrysetting.md) | The IPrintOemDriverUI |
| [IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket method](..\prcomoem\nf-prcomoem-iprintoemprintticketprovider-convertdevmodetoprintticket.md) | The IPrintOemPrintTicketProvider |
| [IPrintOemUni2::GetImplementedMethod method](..\prcomoem\nf-prcomoem-iprintoemuni2-getimplementedmethod.md) | The IPrintOemUni2 |
| [IPrintOemPrintTicketProvider::CompletePrintCapabilities method](..\prcomoem\nf-prcomoem-iprintoemprintticketprovider-completeprintcapabilities.md) | The IPrintOemPrintTicketProvider |
| [IPrintOemUni::GetImplementedMethod method](..\prcomoem\nf-prcomoem-iprintoemuni-getimplementedmethod.md) | The IPrintOemUni |
| [IPrintOemUI::QueryColorProfile method](..\prcomoem\nf-prcomoem-iprintoemui-querycolorprofile.md) | The IPrintOemUI |
| [IPrintCoreHelperUni::SetOptions method](..\prcomoem\nf-prcomoem-iprintcorehelperuni-setoptions.md) | The IPrintCoreHelperUni |
| [IPrintOemPS2::WritePrinter method](..\prcomoem\nf-prcomoem-iprintoemps2-writeprinter.md) | The IPrintOemPS2 |
| [IPrintCoreUI2::EnumConstrainedOptions method](..\prcomoem\nf-prcomoem-iprintcoreui2-enumconstrainedoptions.md) | The IPrintCoreUI2 |
| [IPrintCoreHelperUni::EnumConstrainedOptions method](..\prcomoem\nf-prcomoem-iprintcorehelperuni-enumconstrainedoptions.md) | The IPrintCoreHelperUni |
| [IPrintCorePS2::GetOptions method](..\prcomoem\nf-prcomoem-iprintcoreps2-getoptions.md) | The IPrintCorePS2 |
| [IPrintCoreUI2::WhyConstrained method](..\prcomoem\nf-prcomoem-iprintcoreui2-whyconstrained.md) | The IPrintCoreUI2 |
| [IPrintOemEngine::EnablePDEV method](..\prcomoem\nf-prcomoem-iprintoemengine-enablepdev.md) | TBD. |
| [IPrintOemUIMXDC::AdjustImageableArea method](..\prcomoem\nf-prcomoem-iprintoemuimxdc-adjustimageablearea.md) | The IPrintOemUIMXDC |
| [IPrintOemPrintTicketProvider::ExpandIntentOptions method](..\prcomoem\nf-prcomoem-iprintoemprintticketprovider-expandintentoptions.md) | The IPrintOemPrintTicketProvider |
| [IPrintOemUni::ImageProcessing method](..\prcomoem\nf-prcomoem-iprintoemuni-imageprocessing.md) | The IPrintOemUni |
| [IPrintOemDriverUni::DrvGetGPDData method](..\prcomoem\nf-prcomoem-iprintoemdriveruni-drvgetgpddata.md) | The IPrintOemDriverUni |
| [IPrintOemPS2::GetPDEVAdjustment method](..\prcomoem\nf-prcomoem-iprintoemps2-getpdevadjustment.md) | The IPrintOemPS2 |
| [IPrintOemUni::ResetPDEV method](..\prcomoem\nf-prcomoem-iprintoemuni-resetpdev.md) | The IPrintOemUni |
| [IPrintCoreUI2::GetFeatureAttribute method](..\prcomoem\nf-prcomoem-iprintcoreui2-getfeatureattribute.md) | The IPrintCoreUI2 |
| [IPrintCoreHelperPS::EnumConstrainedOptions method](..\prcomoem\nf-prcomoem-iprintcorehelperps-enumconstrainedoptions.md) | The IPrintCoreHelperPS |
| [IPrintOemPrintTicketProvider::BindPrinter method](..\prcomoem\nf-prcomoem-iprintoemprintticketprovider-bindprinter.md) | The IPrintOemPrintTicketProvider |
| [IPrintCoreUI2::EnumOptions method](..\prcomoem\nf-prcomoem-iprintcoreui2-enumoptions.md) | The IPrintCoreUI2 |
| [IPrintCoreHelperPS::GetOption method](..\prcomoem\nf-prcomoem-iprintcorehelperps-getoption.md) | The IPrintCoreHelperPS |
| [IPrintOemUI::DeviceCapabilities method](..\prcomoem\nf-prcomoem-iprintoemui-devicecapabilities.md) | The IPrintOemUI |
| [IPrintCoreHelper::SetOptions method](..\prcomoem\nf-prcomoem-iprintcorehelper-setoptions.md) | The IPrintCoreHelper |
| [IPrintCoreHelperUni::GetOption method](..\prcomoem\nf-prcomoem-iprintcorehelperuni-getoption.md) | The IPrintCoreHelperUni |
| [IPrintOemUI::PrinterEvent method](..\prcomoem\nf-prcomoem-iprintoemui-printerevent.md) | The IPrintOemUI |
| [IPrintCoreHelperUni::EnumFeatures method](..\prcomoem\nf-prcomoem-iprintcorehelperuni-enumfeatures.md) | The IPrintCoreHelperUni |
| [IPrintCoreHelperUni::GetFontSubstitution method](..\prcomoem\nf-prcomoem-iprintcorehelperuni-getfontsubstitution.md) | The IPrintCoreHelperUni |
| [IPrintCoreHelperUni::SetFontSubstitution method](..\prcomoem\nf-prcomoem-iprintcorehelperuni-setfontsubstitution.md) | The IPrintCoreHelperUni |
| [IPrintOemUI::DevicePropertySheets method](..\prcomoem\nf-prcomoem-iprintoemui-devicepropertysheets.md) | The IPrintOemUI |
| [IPrintOemUni::MemoryUsage method](..\prcomoem\nf-prcomoem-iprintoemuni-memoryusage.md) | The IPrintOemUni |
| [IPrintOemUni::Compression method](..\prcomoem\nf-prcomoem-iprintoemuni-compression.md) | The IPrintOemUni |
| [IPrintOemUI::UpgradePrinter method](..\prcomoem\nf-prcomoem-iprintoemui-upgradeprinter.md) | The IPrintOemUI |
| [IPrintCoreHelper::CreateInstanceOfMSXMLObject method](..\prcomoem\nf-prcomoem-iprintcorehelper-createinstanceofmsxmlobject.md) | The IPrintCoreHelper |
| [IPrintOemEngine::EnableDriver method](..\prcomoem\nf-prcomoem-iprintoemengine-enabledriver.md) | TBD. |
| [IPrintOemUI::DevQueryPrintEx method](..\prcomoem\nf-prcomoem-iprintoemui-devqueryprintex.md) | The IPrintOemUI |
| [IPrintOemDriverPS::DrvGetDriverSetting method](..\prcomoem\nf-prcomoem-iprintoemdriverps-drvgetdriversetting.md) | The IPrintOemDriverPS |
| [IPrintOemUni::SendFontCmd method](..\prcomoem\nf-prcomoem-iprintoemuni-sendfontcmd.md) | The IPrintOemUni |
| [IPrintCoreUI2::GetOptions method](..\prcomoem\nf-prcomoem-iprintcoreui2-getoptions.md) | The IPrintCoreUI2 |
| [IPrintOemDriverUni::DrvGetDriverSetting method](..\prcomoem\nf-prcomoem-iprintoemdriveruni-drvgetdriversetting.md) | The IPrintOemDriverUni |
| [IPrintOemPS::GetInfo method](..\prcomoem\nf-prcomoem-iprintoemps-getinfo.md) | A rendering plug-in's IPrintOemPS |
| [IPrintOemUni::TTYGetInfo method](..\prcomoem\nf-prcomoem-iprintoemuni-ttygetinfo.md) | The IPrintOemUni |
| [IPrintOemEngine::DisablePDEV method](..\prcomoem\nf-prcomoem-iprintoemengine-disablepdev.md) | TBD. |
| [IPrintOemUIMXDC::AdjustImageCompression method](..\prcomoem\nf-prcomoem-iprintoemuimxdc-adjustimagecompression.md) | The IPrintOemUIMXDC |
| [IPrintOemDriverPS::DrvWriteSpoolBuf method](..\prcomoem\nf-prcomoem-iprintoemdriverps-drvwritespoolbuf.md) | The IPrintOemDriverPS |
| [IPrintOemDriverUI::DrvGetDriverSetting method](..\prcomoem\nf-prcomoem-iprintoemdriverui-drvgetdriversetting.md) | The IPrintOemDriverUI |
| [IPrintOemUI::CommonUIProp method](..\prcomoem\nf-prcomoem-iprintoemui-commonuiprop.md) | The IPrintOemUI |
| [IPrintOemPS::ResetPDEV method](..\prcomoem\nf-prcomoem-iprintoemps-resetpdev.md) | The IPrintOemPS |
| [IPrintOemDriverUI::DrvUpdateUISetting method](..\prcomoem\nf-prcomoem-iprintoemdriverui-drvupdateuisetting.md) | The IPrintOemDriverUI |
| [IPrintCoreHelper::GetOption method](..\prcomoem\nf-prcomoem-iprintcorehelper-getoption.md) | The IPrintCoreHelper |
| [IPrintCoreHelperPS::EnumOptions method](..\prcomoem\nf-prcomoem-iprintcorehelperps-enumoptions.md) | The IPrintCoreHelperPS |
| [IPrintOemUI::DevMode method](..\prcomoem\nf-prcomoem-iprintoemui-devmode.md) | The IPrintOemUI |
| [IPrintOemUI2::HideStandardUI method](..\prcomoem\nf-prcomoem-iprintoemui2-hidestandardui.md) | The IPrintOemUI2 |
| [IPrintOemUni3::GetImplementedMethod method](..\prcomoem\nf-prcomoem-iprintoemuni3-getimplementedmethod.md) | The IPrintOemUni3 |
| [IPrintOemPS::EnablePDEV method](..\prcomoem\nf-prcomoem-iprintoemps-enablepdev.md) | The IPrintOemPS |
| [IPrintCoreHelper::GetFontSubstitution method](..\prcomoem\nf-prcomoem-iprintcorehelper-getfontsubstitution.md) | The IPrintCoreHelper |
| [IPrintOemUI::UpdateExternalFonts method](..\prcomoem\nf-prcomoem-iprintoemui-updateexternalfonts.md) | The IPrintOemUI |
| [IPrintOemUI::GetInfo method](..\prcomoem\nf-prcomoem-iprintoemui-getinfo.md) | A user interface plug-in's IPrintOemUI |
| [IPrintCoreHelperUni::EnumOptions method](..\prcomoem\nf-prcomoem-iprintcorehelperuni-enumoptions.md) | The IPrintCoreHelperUni |
| [IPrintOemUni::DriverDMS method](..\prcomoem\nf-prcomoem-iprintoemuni-driverdms.md) | The IPrintOemUni |
| [IPrintOemUni::EnablePDEV method](..\prcomoem\nf-prcomoem-iprintoemuni-enablepdev.md) | The IPrintOemUni |
| [IPrintCoreHelperPS::GetOptionAttribute method](..\prcomoem\nf-prcomoem-iprintcorehelperps-getoptionattribute.md) | The IPrintCoreHelperPS |
| [IPrintCoreHelperUni::CreateDefaultGDLSnapshot method](..\prcomoem\nf-prcomoem-iprintcorehelperuni-createdefaultgdlsnapshot.md) | The IPrintCoreHelperUni |
| [IPrintCoreHelperPS::GetFeatureAttribute method](..\prcomoem\nf-prcomoem-iprintcorehelperps-getfeatureattribute.md) | The IPrintCoreHelperPS |
| [IPrintCoreUI2::GetOptionAttribute method](..\prcomoem\nf-prcomoem-iprintcoreui2-getoptionattribute.md) | The IPrintCoreUI2 |
| [IPrintCoreHelper::EnumConstrainedOptions method](..\prcomoem\nf-prcomoem-iprintcorehelper-enumconstrainedoptions.md) | The IPrintCoreHelper |
| [IPrintCoreHelperPS::EnumFeatures method](..\prcomoem\nf-prcomoem-iprintcorehelperps-enumfeatures.md) | The IPrintCoreHelperPS |
| [IPrintOemPrintTicketProvider::ConvertPrintTicketToDevMode method](..\prcomoem\nf-prcomoem-iprintoemprintticketprovider-convertprinttickettodevmode.md) | The IPrintOemPrintTicketProvider |
| [IPrintOemUni::PublishDriverInterface method](..\prcomoem\nf-prcomoem-iprintoemuni-publishdriverinterface.md) | The IPrintOemUni |
| [IPrintOemPS::DisablePDEV method](..\prcomoem\nf-prcomoem-iprintoemps-disablepdev.md) | The IPrintOemPS |
| [IPrintOemUni::TextOutAsBitmap method](..\prcomoem\nf-prcomoem-iprintoemuni-textoutasbitmap.md) | The IPrintOemUni |
| [IPrintCoreUI2::GetGlobalAttribute method](..\prcomoem\nf-prcomoem-iprintcoreui2-getglobalattribute.md) | The IPrintCoreUI2 |
| [IPrintOemUni2::WritePrinter method](..\prcomoem\nf-prcomoem-iprintoemuni2-writeprinter.md) | The IPrintOemUni2 |
| [IPrintOemUni3::SetBandSize method](..\prcomoem\nf-prcomoem-iprintoemuni3-setbandsize.md) | The IPrintOemUni3 |
| [IPrintOemDriverUni::DrvGetStandardVariable method](..\prcomoem\nf-prcomoem-iprintoemdriveruni-drvgetstandardvariable.md) | The IPrintOemDriverUni |
| [IPrintOemUI2::QueryJobAttributes method](..\prcomoem\nf-prcomoem-iprintoemui2-queryjobattributes.md) | The IPrintOemUI2 |
| [IPrintCoreHelperUni::CreateInstanceOfMSXMLObject method](..\prcomoem\nf-prcomoem-iprintcorehelperuni-createinstanceofmsxmlobject.md) | The IPrintCoreHelperUni |
| [IPrintCoreHelperPS::CreateInstanceOfMSXMLObject method](..\prcomoem\nf-prcomoem-iprintcorehelperps-createinstanceofmsxmlobject.md) | The IPrintCoreHelperPS |
| [IPrintOemPS::DisableDriver method](..\prcomoem\nf-prcomoem-iprintoemps-disabledriver.md) | The IPrintOemPS |
| [IPrintCorePS2::GetFeatureAttribute method](..\prcomoem\nf-prcomoem-iprintcoreps2-getfeatureattribute.md) | The IPrintCorePS2 |
| [IPrintOemUni::EnableDriver method](..\prcomoem\nf-prcomoem-iprintoemuni-enabledriver.md) | The IPrintOemUni |
| [IPrintCoreHelperUni::WhyConstrained method](..\prcomoem\nf-prcomoem-iprintcorehelperuni-whyconstrained.md) | The IPrintCoreHelperUni |
| [IPrintCoreHelperPS::GetFontSubstitution method](..\prcomoem\nf-prcomoem-iprintcorehelperps-getfontsubstitution.md) | The IPrintCoreHelperPS |
| [IPrintOemUI::DocumentPropertySheets method](..\prcomoem\nf-prcomoem-iprintoemui-documentpropertysheets.md) | The IPrintOemUI |
| [IPrintOemUI2::DocumentEvent method](..\prcomoem\nf-prcomoem-iprintoemui2-documentevent.md) | The IPrintOemUI2 |
| [IPrintCorePS2::EnumOptions method](..\prcomoem\nf-prcomoem-iprintcoreps2-enumoptions.md) | The IPrintCorePS2 |
| [IPrintOemDriverUni::DrvUniTextOut method](..\prcomoem\nf-prcomoem-iprintoemdriveruni-drvunitextout.md) | The IPrintOemDriverUni |
| [IPrintOemUni::DisablePDEV method](..\prcomoem\nf-prcomoem-iprintoemuni-disablepdev.md) | The IPrintOemUni |
| [IPrintOemUni3::DownloadPattern method](..\prcomoem\nf-prcomoem-iprintoemuni3-downloadpattern.md) | The IPrintOemUni3 |
| [IPrintOemEngine::ResetPDEV method](..\prcomoem\nf-prcomoem-iprintoemengine-resetpdev.md) | TBD. |
| [IPrintOemUni::DisableDriver method](..\prcomoem\nf-prcomoem-iprintoemuni-disabledriver.md) | The IPrintOemuNI |
| [IPrintCoreUI2::DrvUpdateUISetting method](..\prcomoem\nf-prcomoem-iprintcoreui2-drvupdateuisetting.md) | The IPrintCoreUI2 |
| [IPrintCorePS2::EnumFeatures method](..\prcomoem\nf-prcomoem-iprintcoreps2-enumfeatures.md) | The IPrintCorePS2 |
| [IPrintOemUni3::GetPDEVAdjustment method](..\prcomoem\nf-prcomoem-iprintoemuni3-getpdevadjustment.md) | The IPrintOemUni3 |
| [IPrintCoreUI2::EnumFeatures method](..\prcomoem\nf-prcomoem-iprintcoreui2-enumfeatures.md) | The IPrintCoreUI2 |
| [IPrintCoreHelperPS::WhyConstrained method](..\prcomoem\nf-prcomoem-iprintcorehelperps-whyconstrained.md) | The IPrintCoreHelperPS |
| [IPrintOemPS::EnableDriver method](..\prcomoem\nf-prcomoem-iprintoemps-enabledriver.md) | The IPrintOemPS |
| [IPrintOemDriverUni::DrvWriteSpoolBuf method](..\prcomoem\nf-prcomoem-iprintoemdriveruni-drvwritespoolbuf.md) | The IPrintOemDriverUni |
| [IPrintOemUni::GetInfo method](..\prcomoem\nf-prcomoem-iprintoemuni-getinfo.md) | A rendering plug-in's IPrintOemUni |
| [IPrintOemDriverUni::DrvXMoveTo method](..\prcomoem\nf-prcomoem-iprintoemdriveruni-drvxmoveto.md) | The IPrintOemDriverUni |
| [IPrintOemUni::TTDownloadMethod method](..\prcomoem\nf-prcomoem-iprintoemuni-ttdownloadmethod.md) | The IPrintOemUni |
| [IPrintOemPrintTicketProvider::GetSupportedVersions method](..\prcomoem\nf-prcomoem-iprintoemprintticketprovider-getsupportedversions.md) | The IPrintOemPrintTicketProvider |
| [IPrintCorePS2::GetGlobalAttribute method](..\prcomoem\nf-prcomoem-iprintcoreps2-getglobalattribute.md) | The IPrintCorePS2 |
| [IPrintOemUni::CommandCallback method](..\prcomoem\nf-prcomoem-iprintoemuni-commandcallback.md) | The IPrintOemUni |
| [IPrintCoreHelper::SetFontSubstitution method](..\prcomoem\nf-prcomoem-iprintcorehelper-setfontsubstitution.md) | The IPrintCoreHelper |
| [IPrintOemDriverUni::DrvYMoveTo method](..\prcomoem\nf-prcomoem-iprintoemdriveruni-drvymoveto.md) | The IPrintOemDriverUni |
| [IPrintOemUI::FontInstallerDlgProc method](..\prcomoem\nf-prcomoem-iprintoemui-fontinstallerdlgproc.md) | A user interface plug-in's IPrintOemUI |
| [IPrintCoreHelperPS::SetFontSubstitution method](..\prcomoem\nf-prcomoem-iprintcorehelperps-setfontsubstitution.md) | The IPrintCoreHelperPS |
| [IPrintOemPS::Command method](..\prcomoem\nf-prcomoem-iprintoemps-command.md) | The IPrintOemPS |
| [IPrintOemUni::FilterGraphics method](..\prcomoem\nf-prcomoem-iprintoemuni-filtergraphics.md) | The IPrintOemUni |
Struct

| Title        | Description    |
| ------------- |:-------------:|
| [PRINT_FEATURE_OPTION structure](..\prcomoem\ns-prcomoem--print-feature-option.md) | The PRINT_FEATURE_OPTION structure contains information about a feature-option pair, where the option is one option of a particular feature. |
Interface

| Title        | Description    |
| ------------- |:-------------:|
| [IPrintOemEngine interface](..\prcomoem\nn-prcomoem-iprintoemengine.md) | TBD. |
Interface

| Title        | Description    |
| ------------- |:-------------:|
| [IPrinterExtensionEventArgs interface](..\printerextension\nn-printerextension-iprinterextensioneventargs.md) | Represents the context for the desktop printer extension activation. |
| [IPrintJob interface](..\printerextension\nn-printerextension-iprintjob.md) | Contains properties that represent a print job. |
| [IPrintSchemaPageMediaSizeOption interface](..\printerextension\nn-printerextension-iprintschemapagemediasizeoption~r1.md) | Exposes a Print Schema PageMediaSize Option element. |
| [IPrinterQueueViewEvent interface](..\printerextension\nn-printerextension-iprinterqueueviewevent~r1.md) | Provides the signature of the event handler. |
| [IPrintSchemaCapabilities2 interface](..\printerextension\nn-printerextension-iprintschemacapabilities2~r1.md) | The IPrintSchemaCapabilities2 interface represents an extension to the IPrintSchemaCapabilities object, which provides wrapper methods over a print capabilities document. |
| [IPrinterExtensionAsyncOperation interface](..\printerextension\nn-printerextension-iprinterextensionasyncoperation.md) | Provides the context associated with an asynchronous operation. |
| [IPrinterExtensionContextCollection interface](..\printerextension\nn-printerextension-iprinterextensioncontextcollection.md) | Exposes a collection of IPrinterExtensionContext objects. |
| [IPrintSchemaTicket2 interface](..\printerextension\nn-printerextension-iprintschematicket2.md) | The IPrintSchemaTicket2 interface is an extension to the IPrintSchemaTicket interface, which provides wrapper methods over a print ticket document. |
| [IPrinterExtensionRequest interface](..\printerextension\nn-printerextension-iprinterextensionrequest.md) | Completes the given extension event with either a cancellation or success. |
| [IPrinterScriptablePropertyBag interface](..\printerextension\nn-printerextension-iprinterscriptablepropertybag.md) | The IPrinterScriptablePropertyBag interface is the property bag interface passed to script clients. |
| [IPrintSchemaAsyncOperation interface](..\printerextension\nn-printerextension-iprintschemaasyncoperation.md) | Represents an asynchronous operation context for validation, merge or commit operations. |
| [IPrinterScriptableStream interface](..\printerextension\nn-printerextension-iprinterscriptablestream~r1.md) | The IPrinterScriptableStream interface builds on IPrinterScriptableSequentialStream and adds IStream-like semantics. |
| [IPrintSchemaParameterDefinition interface](..\printerextension\nn-printerextension-iprintschemaparameterdefinition~r1.md) | The IPrintSchemaParameterDefinition interface represents a parameter definition, as defined in the Print Schema Specification. |
| [IPrinterExtensionContext interface](..\printerextension\nn-printerextension-iprinterextensioncontext.md) | Represents the context for the activation of a UWP device app for printers. |
| [IPrinterScriptablePropertyBag2 interface](..\printerextension\nn-printerextension-iprinterscriptablepropertybag2.md) | TBD. |
| [IPrinterQueue interface](..\printerextension\nn-printerextension-iprinterqueue.md) | Represents a single printer queue. |
| [IPrinterQueue2 interface](..\printerextension\nn-printerextension-iprinterqueue2~r1.md) | Represents a single printer queue. |
| [IPrintSchemaCapabilities interface](..\printerextension\nn-printerextension-iprintschemacapabilities~r1.md) | Provides the primary method to access PrintCapabilities. |
| [IPrintJobCollection interface](..\printerextension\nn-printerextension-iprintjobcollection.md) | This interfaces provides an enumeration of the jobs in the print queue. |
| [IPrintSchemaAsyncOperationEvent interface](..\printerextension\nn-printerextension-iprintschemaasyncoperationevent.md) | Exposes a validation, merge, or commit completion event delegate. |
| [IPrintSchemaTicket interface](..\printerextension\nn-printerextension-iprintschematicket.md) | Provides the primary method to access and validate a PrintTicket. |
| [IPrinterQueue interface](..\printerextension\nn-printerextension-iprinterqueue~r1.md) | Represents a single printer queue. |
| [IPrinterQueueView interface](..\printerextension\nn-printerextension-iprinterqueueview.md) | Provides a way to change the range of print jobs being monitored. |
| [IPrintSchemaDisplayableElement interface](..\printerextension\nn-printerextension-iprintschemadisplayableelement.md) | Provides the displayable string for a PrintCapabilites PrintSchema element. |
| [IPrinterScriptablePropertyBag2 interface](..\printerextension\nn-printerextension-iprinterscriptablepropertybag2~r1.md) | TBD. |
| [IPrintSchemaOption interface](..\printerextension\nn-printerextension-iprintschemaoption.md) | Exposes a Print Schema Option object. |
| [IPrintSchemaTicket2 interface](..\printerextension\nn-printerextension-iprintschematicket2~r1.md) | The IPrintSchemaTicket2 interface is an extension to the IPrintSchemaTicket interface, which provides wrapper methods over a print ticket document. |
| [IPrintSchemaElement interface](..\printerextension\nn-printerextension-iprintschemaelement.md) | Provides access to the underlying XML node and &#0034;name&#0034; attribute information for a Print Schema element. |
| [IPrintSchemaTicket interface](..\printerextension\nn-printerextension-iprintschematicket~r1.md) | Provides the primary method to access and validate a PrintTicket. |
| [IPrintSchemaOptionCollection interface](..\printerextension\nn-printerextension-iprintschemaoptioncollection~r1.md) | Exposes a collection of IPrintSchemaOption objects. |
| [IPrinterExtensionRequest interface](..\printerextension\nn-printerextension-iprinterextensionrequest~r1.md) | Completes the given extension event with either a cancellation or success. |
| [IPrinterQueueView interface](..\printerextension\nn-printerextension-iprinterqueueview~r1.md) | Provides a way to change the range of print jobs being monitored. |
| [IPrintSchemaAsyncOperation interface](..\printerextension\nn-printerextension-iprintschemaasyncoperation~r1.md) | Represents an asynchronous operation context for validation, merge or commit operations. |
| [IPrintSchemaFeature interface](..\printerextension\nn-printerextension-iprintschemafeature~r1.md) | Exposes a Print Schema Feature element. |
| [IPrintSchemaPageMediaSizeOption interface](..\printerextension\nn-printerextension-iprintschemapagemediasizeoption.md) | Exposes a Print Schema PageMediaSize Option element. |
| [IPrinterQueueEvent interface](..\printerextension\nn-printerextension-iprinterqueueevent.md) | Provides the event delegate for printer queue events. |
| [IPrinterScriptablePropertyBag interface](..\printerextension\nn-printerextension-iprinterscriptablepropertybag~r1.md) | The IPrinterScriptablePropertyBag interface is the property bag interface passed to script clients. |
| [IPrinterScriptableStream interface](..\printerextension\nn-printerextension-iprinterscriptablestream.md) | The IPrinterScriptableStream interface builds on IPrinterScriptableSequentialStream and adds IStream-like semantics. |
| [IPrinterExtensionEventArgs interface](..\printerextension\nn-printerextension-iprinterextensioneventargs~r1.md) | Represents the context for the desktop printer extension activation. |
| [IPrintSchemaDisplayableElement interface](..\printerextension\nn-printerextension-iprintschemadisplayableelement~r1.md) | Provides the displayable string for a PrintCapabilites PrintSchema element. |
| [IPrintSchemaCapabilities2 interface](..\printerextension\nn-printerextension-iprintschemacapabilities2.md) | The IPrintSchemaCapabilities2 interface represents an extension to the IPrintSchemaCapabilities object, which provides wrapper methods over a print capabilities document. |
| [IPrinterScriptContext interface](..\printerextension\nn-printerextension-iprinterscriptcontext~r1.md) | Passed to all third-party constraints JavaScript functions, and provides access to relevant objects. |
| [IPrintSchemaFeature interface](..\printerextension\nn-printerextension-iprintschemafeature.md) | Exposes a Print Schema Feature element. |
| [IPrintSchemaPageImageableSize interface](..\printerextension\nn-printerextension-iprintschemapageimageablesize~r1.md) | Exposes the PageImageableSize property of PrintCapabilities. The properties of this interface map directly to those in the PageImageableSize property of PrintCapabilities. |
| [IPrinterPropertyBag interface](..\printerextension\nn-printerextension-iprinterpropertybag.md) | Provides strongly-typed get and set methods. |
| [IPrintSchemaAsyncOperationEvent interface](..\printerextension\nn-printerextension-iprintschemaasyncoperationevent~r1.md) | Exposes a validation, merge, or commit completion event delegate. |
| [IPrintSchemaElement interface](..\printerextension\nn-printerextension-iprintschemaelement~r1.md) | Provides access to the underlying XML node and &#0034;name&#0034; attribute information for a Print Schema element. |
| [IPrintSchemaParameterDefinition interface](..\printerextension\nn-printerextension-iprintschemaparameterdefinition.md) | The IPrintSchemaParameterDefinition interface represents a parameter definition, as defined in the Print Schema Specification. |
| [IPrinterPropertyBag interface](..\printerextension\nn-printerextension-iprinterpropertybag~r1.md) | Provides strongly-typed get and set methods. |
| [IPrintSchemaParameterInitializer interface](..\printerextension\nn-printerextension-iprintschemaparameterinitializer.md) | The IPrintSchemaParameterInitializer interface represents a parameter initialization value, as defined in the print schema specification. |
| [IPrintJobCollection interface](..\printerextension\nn-printerextension-iprintjobcollection~r1.md) | This interfaces provides an enumeration of the jobs in the print queue. |
| [IPrinterExtensionAsyncOperation interface](..\printerextension\nn-printerextension-iprinterextensionasyncoperation~r1.md) | Provides the context associated with an asynchronous operation. |
| [IPrinterExtensionContext interface](..\printerextension\nn-printerextension-iprinterextensioncontext~r1.md) | Represents the context for the activation of a UWP device app for printers. |
| [IPrintSchemaOptionCollection interface](..\printerextension\nn-printerextension-iprintschemaoptioncollection.md) | Exposes a collection of IPrintSchemaOption objects. |
| [IPrintSchemaCapabilities interface](..\printerextension\nn-printerextension-iprintschemacapabilities.md) | Provides the primary method to access PrintCapabilities. |
| [IPrintSchemaParameterInitializer interface](..\printerextension\nn-printerextension-iprintschemaparameterinitializer~r1.md) | The IPrintSchemaParameterInitializer interface represents a parameter initialization value, as defined in the print schema specification. |
| [IPrintSchemaPageImageableSize interface](..\printerextension\nn-printerextension-iprintschemapageimageablesize.md) | Exposes the PageImageableSize property of PrintCapabilities. The properties of this interface map directly to those in the PageImageableSize property of PrintCapabilities. |
| [IPrintJob interface](..\printerextension\nn-printerextension-iprintjob~r1.md) | Contains properties that represent a print job. |
| [IPrinterExtensionContextCollection interface](..\printerextension\nn-printerextension-iprinterextensioncontextcollection~r1.md) | Exposes a collection of IPrinterExtensionContext objects. |
| [IPrinterBidiSetRequestCallback interface](..\printerextension\nn-printerextension-iprinterbidisetrequestcallback.md) | Describes the signature of the callback object that receives the Bidi response. |
| [IPrinterQueueViewEvent interface](..\printerextension\nn-printerextension-iprinterqueueviewevent.md) | Provides the signature of the event handler. |
| [IPrinterBidiSetRequestCallback interface](..\printerextension\nn-printerextension-iprinterbidisetrequestcallback~r1.md) | Describes the signature of the callback object that receives the Bidi response. |
| [IPrinterScriptContext interface](..\printerextension\nn-printerextension-iprinterscriptcontext.md) | Passed to all third-party constraints JavaScript functions, and provides access to relevant objects. |
| [IPrintSchemaOption interface](..\printerextension\nn-printerextension-iprintschemaoption~r1.md) | Exposes a Print Schema Option object. |
| [IPrinterQueue2 interface](..\printerextension\nn-printerextension-iprinterqueue2.md) | Represents a single printer queue. |
| [IPrinterQueueEvent interface](..\printerextension\nn-printerextension-iprinterqueueevent~r1.md) | Provides the event delegate for printer queue events. |
Function

| Title        | Description    |
| ------------- |:-------------:|
| [IPrinterQueue::GetProperties method](..\printerextension\nf-printerextension-iprinterqueue-getproperties.md) | Gets the properties in the property bag for the queue. |
| [IPrintSchemaTicket::GetFeatureByKeyName method](..\printerextension\nf-printerextension-iprintschematicket-getfeaturebykeyname.md) | Gets a feature from the PrintTicket based on the specified key name. |
| [IPrinterScriptablePropertyBag::GetInt32 method](..\printerextension\nf-printerextension-iprinterscriptablepropertybag-getint32.md) | Gets an integer property. |
| [IPrintJobCollection::GetAt method](..\printerextension\nf-printerextension-iprintjobcollection-getat.md) | Gets a pointer to an IPrintJob object. |
| [IPrinterPropertyBag::SetString method](..\printerextension\nf-printerextension-iprinterpropertybag-setstring.md) | Writes a string property. |
| [IPrinterPropertyBag::GetWriteStream method](..\printerextension\nf-printerextension-iprinterpropertybag-getwritestream.md) | Gets a stream in order to write a stream property. |
| [IPrintSchemaAsyncOperationEvent::Completed method](..\printerextension\nf-printerextension-iprintschemaasyncoperationevent-completed.md) | Is called when asynchronous PrintSchema operation that is represented by an IPrintSchemaAsyncOperation context is completed. |
| [IPrinterExtensionManager::DisableEvents method](..\printerextension\nf-printerextension-iprinterextensionmanager-disableevents.md) | Disallows events to be generated. |
| [IPrinterBidiSetRequestCallback::Completed method](..\printerextension\nf-printerextension-iprinterbidisetrequestcallback-completed.md) | Invoked when the Bidi “Set”” operation is completed. |
| [IPrintJob::RequestCancel method](..\printerextension\nf-printerextension-iprintjob-requestcancel.md) | Requests the cancellation of a print job. |
| [IPrintSchemaTicket2::GetParameterInitializer method](..\printerextension\nf-printerextension-iprintschematicket2-getparameterinitializer.md) | The GetParameterInitializer method retrieves the IPrintSchemaParameterInitializer object, and it represents the &lt;psf |
| [IPrinterScriptablePropertyBag::GetWriteStream method](..\printerextension\nf-printerextension-iprinterscriptablepropertybag-getwritestream.md) | Gets a stream and uses it to write to a stream property. |
| [IPrinterQueueViewEvent::OnChanged method](..\printerextension\nf-printerextension-iprinterqueueviewevent-onchanged.md) | Provides an IPrintJobCollection object that provides a snapshot of a range of print jobs in the queue. |
| [IPrinterScriptablePropertyBag::GetBool method](..\printerextension\nf-printerextension-iprinterscriptablepropertybag-getbool.md) | Gets a specified boolean property. |
| [IPrinterPropertyBag::GetBool method](..\printerextension\nf-printerextension-iprinterpropertybag-getbool.md) | Reads a specified boolean property. |
| [IPrinterQueueEvent::OnBidiResponseReceived method](..\printerextension\nf-printerextension-iprinterqueueevent-onbidiresponsereceived.md) | Called when a bidi response is received. |
| [IPrinterScriptablePropertyBag::GetBytes method](..\printerextension\nf-printerextension-iprinterscriptablepropertybag-getbytes.md) | Gets a byte array property. |
| [IPrinterExtensionManager::EnableEvents method](..\printerextension\nf-printerextension-iprinterextensionmanager-enableevents.md) | The EnableEvents method allows events to be generated for the specified printer driver until DisableEvents is called. |
| [IPrinterScriptablePropertyBag::SetBytes method](..\printerextension\nf-printerextension-iprinterscriptablepropertybag-setbytes.md) | Writes a byte array property. |
| [IPrinterScriptablePropertyBag::SetInt32 method](..\printerextension\nf-printerextension-iprinterscriptablepropertybag-setint32.md) | Writes an integer property. |
| [IPrinterExtensionRequest::Cancel method](..\printerextension\nf-printerextension-iprinterextensionrequest-cancel.md) | Completes the extension event with a cancellation. |
| [IPrinterExtensionAsyncOperation::Cancel method](..\printerextension\nf-printerextension-iprinterextensionasyncoperation-cancel.md) | Cancels the asynchronous operation. |
| [IPrintSchemaCapabilities::GetFeature method](..\printerextension\nf-printerextension-iprintschemacapabilities-getfeature.md) | Gets a named feature from the PrintCapabilities, by name and full namespace URI. |
| [IPrintSchemaTicket::GetFeature method](..\printerextension\nf-printerextension-iprintschematicket-getfeature.md) | Gets a named feature from the PrintTicket, by name and full namespace URI. |
| [IPrinterPropertyBag::SetBool method](..\printerextension\nf-printerextension-iprinterpropertybag-setbool.md) | Writes a specified boolean property value. |
| [IPrinterExtensionContextCollection::GetAt method](..\printerextension\nf-printerextension-iprinterextensioncontextcollection-getat.md) | Gets a pointer to an IPrinterExtensionContext object. |
| [IPrinterPropertyBag::GetInt32 method](..\printerextension\nf-printerextension-iprinterpropertybag-getint32.md) | Reads an integer property. |
| [IPrinterScriptablePropertyBag::GetReadStream method](..\printerextension\nf-printerextension-iprinterscriptablepropertybag-getreadstream.md) | Gets a read stream and uses it to read from a property. |
| [IPrinterPropertyBag::GetReadStream method](..\printerextension\nf-printerextension-iprinterpropertybag-getreadstream.md) | Gets a stream in order to read from a stream property. |
| [IPrinterQueue2::SendBidiSetRequestAsync method](..\printerextension\nf-printerextension-iprinterqueue2-sendbidisetrequestasync.md) | Uses an XML string value to send a Bidi Set request as an asynchronous operation. |
| [IPrinterQueue::SendBidiQuery method](..\printerextension\nf-printerextension-iprinterqueue-sendbidiquery.md) | Performs an asynchronous refresh operation with the specified query, and invokes the IPrinterQueueEvent |
| [IPrinterScriptablePropertyBag2::GetReadStreamAsXML method](..\printerextension\nf-printerextension-iprinterscriptablepropertybag2-getreadstreamasxml.md) | TBD. |
| [IPrinterScriptablePropertyBag::SetBool method](..\printerextension\nf-printerextension-iprinterscriptablepropertybag-setbool.md) | Writes a specified boolean property value. |
| [IPrinterScriptablePropertyBag::GetString method](..\printerextension\nf-printerextension-iprinterscriptablepropertybag-getstring.md) | Gets a string property. |
| [IPrinterExtensionRequest::Complete method](..\printerextension\nf-printerextension-iprinterextensionrequest-complete.md) | Completes the extension event. |
| [IPrinterPropertyBag::GetBytes method](..\printerextension\nf-printerextension-iprinterpropertybag-getbytes.md) | Reads a byte array property. |
| [IPrinterQueue2::GetPrinterQueueView method](..\printerextension\nf-printerextension-iprinterqueue2-getprinterqueueview.md) | Retrieves an IPrinterQueueView object, and initializes the object with the range of jobs to be monitored. |
| [IPrinterExtensionEvent::OnPrinterQueuesEnumerated method](..\printerextension\nf-printerextension-iprinterextensionevent-onprinterqueuesenumerated.md) | Called when printer queues are enumerated. |
| [IPrintSchemaTicket::NotifyXmlChanged method](..\printerextension\nf-printerextension-iprintschematicket-notifyxmlchanged.md) | Notifies the print system that the XML DOM object has changed. |
| [IPrinterPropertyBag::GetString method](..\printerextension\nf-printerextension-iprinterpropertybag-getstring.md) | Reads a string property. |
| [IPrintSchemaCapabilities::GetOptions method](..\printerextension\nf-printerextension-iprintschemacapabilities-getoptions.md) | Gets all the options of a feature. |
| [IPrintSchemaAsyncOperation::Cancel method](..\printerextension\nf-printerextension-iprintschemaasyncoperation-cancel.md) | Cancels the asynchronous PrintSchema operation. |
| [IPrintSchemaCapabilities2::GetParameterDefinition method](..\printerextension\nf-printerextension-iprintschemacapabilities2-getparameterdefinition.md) | The GetParameterDefinition method retrieves the IPrintSchemaParameterDefinition object, and it represents the &lt;psf |
| [IPrinterScriptablePropertyBag::SetString method](..\printerextension\nf-printerextension-iprinterscriptablepropertybag-setstring.md) | Writes a string property. |
| [IPrintSchemaOptionCollection::GetAt method](..\printerextension\nf-printerextension-iprintschemaoptioncollection-getat.md) | Gets a pointer to an IPrintSchemaOption object. |
| [IPrinterScriptableStream::Commit method](..\printerextension\nf-printerextension-iprinterscriptablestream-commit.md) | Commits the operation. |
| [IPrintSchemaCapabilities::GetFeatureByKeyName method](..\printerextension\nf-printerextension-iprintschemacapabilities-getfeaturebykeyname.md) | Gets a feature from the PrintCapabilities based on a given key name. |
| [IPrinterQueueView::SetViewRange method](..\printerextension\nf-printerextension-iprinterqueueview-setviewrange.md) | Sets the range of print jobs being monitored. |
| [IPrintSchemaAsyncOperation::Start method](..\printerextension\nf-printerextension-iprintschemaasyncoperation-start.md) | Starts the asynchronous PrintSchema operation. |
| [IPrinterScriptableStream::Seek method](..\printerextension\nf-printerextension-iprinterscriptablestream-seek.md) | Sets the seek pointer. |
| [IPrinterPropertyBag::SetBytes method](..\printerextension\nf-printerextension-iprinterpropertybag-setbytes.md) | Writes a byte array property. |
| [IPrintSchemaOption::GetPropertyValue method](..\printerextension\nf-printerextension-iprintschemaoption-getpropertyvalue.md) | Gets the XML node for the &#0034;value&#0034; child element of a &#0034;Property&#0034; or a &#0034;ScoredProperty&#0034; element with the given name. |
| [IPrintSchemaFeature::GetOption method](..\printerextension\nf-printerextension-iprintschemafeature-getoption.md) | Gets the option with the given name. |
| [IPrinterPropertyBag::SetInt32 method](..\printerextension\nf-printerextension-iprinterpropertybag-setint32.md) | Writes an integer property. |
| [IPrintSchemaCapabilities::GetSelectedOptionInPrintTicket method](..\printerextension\nf-printerextension-iprintschemacapabilities-getselectedoptioninprintticket.md) | Gets the selected option for a feature in IPrintSchemaTicket. |
| [IPrinterScriptableStream::SetSize method](..\printerextension\nf-printerextension-iprinterscriptablestream-setsize.md) | Sets the size of the scriptable stream, in bytes. |
Struct

| Title        | Description    |
| ------------- |:-------------:|
| [GETINFO_STDVAR structure](..\printoem\ns-printoem--getinfo-stdvar.md) | The GETINFO_STDVAR structure is used as input to the UNIFONTOBJ_GetInfo callback function. |
| [PSCRIPT5_PRIVATE_DEVMODE structure](..\printoem\ns-printoem--pscript5-private-devmode.md) | The PSCRIPT5_PRIVATE_DEVMODE structure enables Pscript5 plug-ins to determine the size of the private portion of Pscript5's DEVMODEW structure. |
| [OEMUIPSPARAM structure](..\printoem\ns-printoem--oemuipsparam.md) | The OEMUIPSPARAM structure is passed to a user interface plug-in's IPrintOemUI |
| [OEM_DMEXTRAHEADER structure](..\printoem\ns-printoem--oem-dmextraheader.md) | The OEM_DMEXTRAHEADER structure must be used to define the first members of a set of private DEVMODEW structure members. |
| [GETINFO_FONTOBJ structure](..\printoem\ns-printoem--getinfo-fontobj.md) | The GETINFO_FONTOBJ structure is used as input to the UNIFONTOBJ_GetInfo callback function. |
| [PDEV_USE_TRUE_COLOR structure](..\printoem\ns-printoem--pdev-use-true-color.md) | The PDEV_USE_TRUE_COLOR structure indicates whether the output color space should be color or grayscale. |
| [PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA structure](..\printoem\ns-printoem--pdev-adjust-imageable-origin-area.md) | The PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA structure specifies the imageable origin area. |
| [OEMCUIPPARAM structure](..\printoem\ns-printoem--oemcuipparam~r1.md) | The OEMCUIPPARAM structure is used as an input parameter to a user interface plug-in's IPrintOemUI |
| [OEMDMPARAM structure](..\printoem\ns-printoem--oemdmparam.md) | The OEMDMPARAM structure is used as an input parameter to the IPrintOemUI |
| [SIMULATE_CAPS_1 structure](..\printoem\ns-printoem--simulate-caps-1.md) | The SIMULATE_CAPS_1 structure contains information about the types of simulations a spooler supports. |
| [GETINFO_GLYPHSTRING structure](..\printoem\ns-printoem--getinfo-glyphstring.md) | The GETINFO_GLYPHSTRING structure is used as input to the UNIFONTOBJ_GetInfo callback function. |
| [PIPPARAMS structure](..\printoem\ns-printoem-pipparams.md) | The IPPARAMS structure is used as an input parameter to a rendering plug-in's IPrintOemUni |
| [GETINFO_MEMORY structure](..\printoem\ns-printoem--getinfo-memory.md) | The GETINFO_MEMORY structure is used as input to the UNIFONTOBJ_GetInfo callback function. |
| [GETINFO_GLYPHBITMAP structure](..\printoem\ns-printoem--getinfo-glyphbitmap.md) | The GETINFO_GLYPHBITMAP structure is used as input to the UNIFONTOBJ_GetInfo callback function. |
| [POEMMEMORYUSAGE structure](..\printoem\ns-printoem-poemmemoryusage.md) | The OEMMEMORYUSAGE structure is used as an input parameter to a rendering plug-in's IPrintOemUni |
| [PDEV_HOSTFONT_ENABLED structure](..\printoem\ns-printoem--pdev-hostfont-enabled.md) | The PDEV_HOSTFONT_ENABLED structure indicates whether the Hostfont feature is enabled. |
| [UNIDRV_PRIVATE_DEVMODE structure](..\printoem\ns-printoem--unidrv-private-devmode.md) | The UNIDRV_PRIVATE_DEVMODE structure enables Unidrv plug-ins to determine the size of the private portion of Unidrv's DEVMODEW structure. |
| [PUBLISHERINFO structure](..\printoem\ns-printoem--publisherinfo.md) | The PUBLISHERINFO structure is used as an input parameter to the IPrintOemPS |
| [GETINFO_GLYPHWIDTH structure](..\printoem\ns-printoem--getinfo-glyphwidth.md) | The GETINFO_GLYPHWIDTH structure is used as input to the UNIFONTOBJ_GetInfo callback function. |
| [USERDATA structure](..\printoem\ns-printoem--userdata.md) | The USERDATA structure is used by Unidrv and Pscript to specify additional information about printer features. A USERDATA structure pointer is supplied as the UserData member for each OPTITEM structure. |
| [OEMUIPROCS structure](..\printoem\ns-printoem--oemuiprocs.md) | The OEMUIPROCS structure is obsolete.The OEMUIPROCS structure contains the address of the DrvGetDriverSetting and DrvUpdateUISetting functions that are exported by Microsoft printer drivers. |
| [PDEV_ADJUST_GRAPHICS_RESOLUTION structure](..\printoem\ns-printoem--pdev-adjust-graphics-resolution.md) | The PDEV_ADJUST_GRAPHICS_RESOLUTION structure specifies a graphics resolution value. |
| [DEVOBJ structure](..\printoem\ns-printoem--devobj~r1.md) | The DEVOBJ structure is used as an input argument to several of a rendering plug-in's COM interface methods. |
| [PDEV_ADJUST_PAPER_MARGIN structure](..\printoem\ns-printoem--pdev-adjust-paper-margin.md) | The PDEV_ADJUST_PAPER_MARGIN structure specifies the imageable printing area. |
| [FINVOCATION structure](..\printoem\ns-printoem--finvocation.md) | The FINVOCATION structure is used as input to the IPrintOemUni |
| [UNIFONTOBJ structure](..\printoem\ns-printoem--unifontobj.md) | The UNIFONTOBJ structure is used as an input parameter to font functions in rendering plug-ins. |
| [CUSTOMSIZEPARAM structure](..\printoem\ns-printoem--customsizeparam.md) | The CUSTOMSIZEPARAM structure holds information pertaining to a single custom page size parameter for a printer. |
| [OEMUIOBJ structure](..\printoem\ns-printoem--oemuiobj.md) | The OEMUIOBJ structure is used as an input argument to several of the methods exported by user interface plug-ins. |
Enum

| Title        | Description    |
| ------------- |:-------------:|
| [STDVARIABLEINDEX enumeration](..\printoem\ne-printoem--stdvariableindex.md) | TBD. |
| [EATTRIBUTE_DATATYPE enumeration](..\printoem\ne-printoem--eattribute-datatype.md) | The EATTRIBUTE_DATATYPE enumerates the possible data types for a global attribute, feature attribute or option attribute. |
Function

| Title        | Description    |
| ------------- |:-------------:|
| [RouterRegisterForPrintAsyncNotifications function](..\prnasntp\nf-prnasntp-routerregisterforprintasyncnotifications.md) | The RouterRegisterForPrintAsyncNotifications function registers for asynchronous notifications associated with a printer or print server. |
| [RouterUnregisterForPrintAsyncNotifications function](..\prnasntp\nf-prnasntp-routerunregisterforprintasyncnotifications.md) | The RouterUnregisterForPrintAsyncNotifications function unregisters for receiving asynchronous notifications associated with a printer or print server. |
| [RouterGetPrintClassObject function](..\prnasntp\nf-prnasntp-routergetprintclassobject.md) | The RouterGetPrintClassObject function enumerates the list of print providers, searching for the print provider with the specified name and interface ID. |
Struct

| Title        | Description    |
| ------------- |:-------------:|
| [CONFIG_INFO_DATA_1 structure](..\tcpxcv\ns-tcpxcv--config-info-data-1.md) | The XcvData function uses a CONFIG_INFO_DATA_1 structure when it obtains configuration data for a particular port. |
| [DELETE_PORT_DATA_1 structure](..\tcpxcv\ns-tcpxcv--delete-port-data-1.md) | The XcvData function uses a DELETE_PORT_DATA_1 structure when it deletes a port. |
| [PORT_DATA_1 structure](..\tcpxcv\ns-tcpxcv--port-data-1.md) | The XcvData function uses a PORT_DATA_1 structure when it adds a port or configures an existing port. |
Struct

| Title        | Description    |
| ------------- |:-------------:|
| [ATTRIBUTE_INFO_1 structure](..\winddiui\ns-winddiui--attribute-info-1.md) | The ATTRIBUTE_INFO_1 structure is used as a parameter for a printer interface DLL's DrvQueryJobAttributes function. All member values are function-supplied. |
| [PRINTER_EVENT_ATTRIBUTES_INFO structure](..\winddiui\ns-winddiui--printer-event-attributes-info.md) | The PRINTER_EVENT_ATTRIBUTES_INFO structure contains the former attributes and the new attributes for a printer. |
| [DRIVER_UPGRADE_INFO_2 structure](..\winddiui\ns-winddiui--driver-upgrade-info-2.md) | The DRIVER_UPGRADE_INFO_2 structure is used as an input to a printer interface DLL's DrvUpgradePrinter function. |
| [DOCEVENT_FILTER structure](..\winddiui\ns-winddiui--docevent-filter.md) | The DOCEVENT_FILTER structure contains a list of document events to which the printer driver will respond. See DrvDocumentEvent for a complete list of the document events. |
| [ATTRIBUTE_INFO_4 structure](..\winddiui\ns-winddiui--attribute-info-4.md) | The ATTRIBUTE_INFO_4 structure is used as a parameter for a printer interface DLL's DrvQueryJobAttributes function. |
| [DEVICEPROPERTYHEADER structure](..\winddiui\ns-winddiui--devicepropertyheader.md) | The DEVICEPROPERTYHEADER structure is used as an input parameter to a printer interface DLL's DrvDevicePropertySheets function. |
| [ATTRIBUTE_INFO_2 structure](..\winddiui\ns-winddiui--attribute-info-2.md) | The ATTRIBUTE_INFO_2 structure is used as a parameter for a printer interface DLL's DrvQueryJobAttributes function. All member values are function-supplied. |
| [ATTRIBUTE_INFO_3 structure](..\winddiui\ns-winddiui--attribute-info-3.md) | The ATTRIBUTE_INFO_3 structure is used as a parameter for a printer interface DLL's DrvQueryJobAttributes function. All member values are function-supplied. |
| [DOCEVENT_CREATEDCPRE structure](..\winddiui\ns-winddiui--docevent-createdcpre.md) | The DOCEVENT_CREATEDCPRE structure contains a set of values used in certain calls to DrvDocumentEvent and IPrintOemUI2 |
| [DOCEVENT_ESCAPE structure](..\winddiui\ns-winddiui--docevent-escape.md) | The DOCEVENT_ESCAPE structure is a container for values used as parameters for the ExtEscape function. |
| [DEVQUERYPRINT_INFO structure](..\winddiui\ns-winddiui--devqueryprint-info.md) | The DEVQUERYPRINT_INFO structure is used as an input parameter to a printer interface DLL's DevQueryPrintEx function. |
| [DOCUMENTPROPERTYHEADER structure](..\winddiui\ns-winddiui--documentpropertyheader.md) | The DOCUMENTPROPERTYHEADER structure is used as an input parameter to a printer interface DLL's DrvDocumentPropertySheets function. |
| [DRIVER_UPGRADE_INFO_1 structure](..\winddiui\ns-winddiui--driver-upgrade-info-1.md) | The DRIVER_UPGRADE_INFO_1 structure is used as an input to a printer interface DLL's DrvUpgradePrinter function. |
Function

| Title        | Description    |
| ------------- |:-------------:|
| [DevQueryPrintEx function](..\winddiui\nf-winddiui-devqueryprintex.md) | A printer interface DLL's DevQueryPrintEx function determines if a specified print job is compatible with the printer's current configuration and can therefore be printed. |
| [DrvDevicePropertySheets function](..\winddiui\nf-winddiui-drvdevicepropertysheets.md) | A printer interface DLL's DrvDevicePropertySheets function is responsible for creating property sheet pages that describe a printer's properties. |
| [DrvDocumentEvent function](..\winddiui\nf-winddiui-drvdocumentevent.md) | A printer interface DLL's DrvDocumentEvent function can handle certain events associated with printing a document. |
| [DrvConvertDevMode function](..\winddiui\nf-winddiui-drvconvertdevmode.md) | A printer interface DLL's DrvConvertDevMode function converts a printer's DEVMODEW structure from one version to another. |
| [DrvDriverEvent function](..\winddiui\nf-winddiui-drvdriverevent.md) | The print spooler calls a printer interface DLL's DrvDriverEvent function when the spooler processes driver-specific events that might require action by the printer driver. |
| [DrvPrinterEvent function](..\winddiui\nf-winddiui-drvprinterevent.md) | A printer interface DLL's DrvPrinterEvent function is called by the print spooler when processing printer-specific events that might require action by the printer driver. |
| [DrvDeviceCapabilities function](..\winddiui\nf-winddiui-drvdevicecapabilities.md) | A printer interface DLL's DrvDeviceCapabilities function returns requested information about a printer's capabilities. |
| [DrvSplDeviceCaps function](..\winddiui\nf-winddiui-drvspldevicecaps.md) | A printer interface DLL's DrvSplDeviceCaps function queries a printer for its capabilities. |
| [DrvUpgradePrinter function](..\winddiui\nf-winddiui-drvupgradeprinter.md) | A printer interface DLL's DrvUpgradePrinter function is used for updating a printer's registry settings when a new version of the driver is added to a system. |
| [DrvQueryJobAttributes function](..\winddiui\nf-winddiui-drvqueryjobattributes.md) | The DrvQueryJobAttributes function allows a printer interface DLL to specify support for such capabilities as printing multiple document pages on a physical page (&#0034;N-up&#0034; printing), printing multiple copies of each page, collating pages, and printing pages in reverse order. |
| [DrvDocumentPropertySheets function](..\winddiui\nf-winddiui-drvdocumentpropertysheets.md) | A printer interface DLL's DrvDocumentPropertySheets function is responsible for creating property sheet pages that describe a print document's properties. |
| [DrvQueryColorProfile function](..\winddiui\nf-winddiui-drvquerycolorprofile.md) | The DrvQueryColorProfile function allows a printer interface DLL to specify an ICC profile to use for color management. |
Function

| Title        | Description    |
| ------------- |:-------------:|
| [GdiGetDC function](..\winppi\nf-winppi-gdigetdc.md) | The GdiGetDC function returns a handle to a printer's device context. |
| [GdiGetSpoolFileHandle function](..\winppi\nf-winppi-gdigetspoolfilehandle.md) | The GdiGetSpoolFileHandle function returns a handle to a print job's EMF file. |
| [GdiGetPageCount function](..\winppi\nf-winppi-gdigetpagecount.md) | The GdiGetPageCount function returns the number of pages in a print job. |
| [GdiGetDevmodeForPage function](..\winppi\nf-winppi-gdigetdevmodeforpage.md) | The GdiGetDevmodeForPage function returns DEVMODEW structures for the specified and previous pages of a print job. |
| [GdiResetDCEMF function](..\winppi\nf-winppi-gdiresetdcemf.md) | The GdiResetDCEMF function resets a printer's device context during playback of a spooled EMF print job. |
| [GdiStartDocEMF function](..\winppi\nf-winppi-gdistartdocemf.md) | The GdiStartDocEMF function performs initialization operations for an EMF-formatted print job. |
| [GdiDeleteSpoolFileHandle function](..\winppi\nf-winppi-gdideletespoolfilehandle.md) | The GdiDeleteSpoolFileHandle function releases a spool file handle. |
| [GdiPlayPageEMF function](..\winppi\nf-winppi-gdiplaypageemf.md) | The GdiPlayPageEMF function plays the EMF records within a specified rectangle for one document page of a spooled print job. |
| [GdiEndDocEMF function](..\winppi\nf-winppi-gdienddocemf.md) | The GdiEndDocEMF function ends EMF playback operations for an EMF-formatted print job. |
| [GdiGetPageHandle function](..\winppi\nf-winppi-gdigetpagehandle.md) | The GdiGetPageHandle function returns a handle to the specified page within a print job. |
| [GdiEndPageEMF function](..\winppi\nf-winppi-gdiendpageemf.md) | The GdiEndPageEMF function ends EMF playback operations for a physical page of an EMF-formatted print job. |
| [GdiStartPageEMF function](..\winppi\nf-winppi-gdistartpageemf.md) | The GdiStartPageEMF function performs initialization operations for a physical page of an EMF-formatted print job. |
Function

| Title        | Description    |
| ------------- |:-------------:|
| [GetPrintProcessorCapabilities function](..\winsplp\nf-winsplp-getprintprocessorcapabilities.md) | A print processor's GetPrintProcessorCapabilities function returns capabilities associated with a specified input data type. |
| [ProvidorFindClosePrinterChangeNotification function](..\winsplp\nf-winsplp-providorfindcloseprinterchangenotification.md) | TBD. |
| [ReplyPrinterChangeNotification function](..\winsplp\nf-winsplp-replyprinterchangenotification.md) | The print spooler's ReplyPrinterChangeNotification function allows a print provider to update the spooler's database of print queue events associated with a notification handle, and to notify the client that print queue events have occurred. |
| [SplDeleteSpoolerPortEnd function](..\winsplp\nf-winsplp-spldeletespoolerportend.md) | TBD. |
| [InitializePrintMonitorUI function](..\winsplp\nf-winsplp-initializeprintmonitorui.md) | A port monitor UI DLL's InitializePrintMonitorUI function supplies the print spooler with addresses of DLL functions. |
| [OpenPrintProcessor function](..\winsplp\nf-winsplp-openprintprocessor.md) | A print processor's OpenPrintProcessor function prepares the print processor for printing a job and returns a handle. |
| [RevertToPrinterSelf function](..\winsplp\nf-winsplp-reverttoprinterself.md) | When RevertToPrinterSelf is called on an impersonating thread, it returns the token for the thread that is being impersonated. |
| [SpoolerFindNextPrinterChangeNotification function](..\winsplp\nf-winsplp-spoolerfindnextprinterchangenotification.md) | TBD. |
| [XcvDataPort function](..\winsplp\nf-winsplp-xcvdataport.md) | A port monitor server DLL's XcvDataPort function receives information from, and returns information to, the port monitor's UI DLL. |
| [SpoolerFindClosePrinterChangeNotification function](..\winsplp\nf-winsplp-spoolerfindcloseprinterchangenotification.md) | TBD. |
| [InitializePrintMonitor2 function](..\winsplp\nf-winsplp-initializeprintmonitor2.md) | A print monitor's InitializePrintMonitor2 function initializes a print monitor for use with clustered print servers. |
| [RouterAllocPrinterNotifyInfo function](..\winsplp\nf-winsplp-routerallocprinternotifyinfo.md) | The print spooler's RouterAllocPrinterNotifyInfo function allocates a PRINTER_NOTIFY_INFO structure and an array of PRINTER_NOTIFY_INFO_DATA structures. |
| [GetJobAttributes function](..\winsplp\nf-winsplp-getjobattributes.md) | Warning  Starting with Windows 10, the APIs which support third-party print providers are deprecated. |
| [SplDeleteSpoolerPortStart function](..\winsplp\nf-winsplp-spldeletespoolerportstart.md) | TBD. |
| [CreatePrinterIC function](..\winsplp\nf-winsplp-createprinteric.md) | TBD. |
| [ClosePrintProcessor function](..\winsplp\nf-winsplp-closeprintprocessor.md) | A print processor's ClosePrintProcessor function completes the printing of a print job and makes the associated handle invalid. |
| [ClosePort function](..\winsplp\nf-winsplp-closeport.md) | A language or port monitor's ClosePort function closes a printer port. |
| [ProvidorFindFirstPrinterChangeNotification function](..\winsplp\nf-winsplp-providorfindfirstprinterchangenotification.md) | TBD. |
| [RouterFreePrinterNotifyInfo function](..\winsplp\nf-winsplp-routerfreeprinternotifyinfo.md) | The print spooler's RouterFreePrinterNotifyInfo function deallocates a specified PRINTER_NOTIFY_INFO structure and its associated PRINTER_NOTIFY_INFO_DATA structure array. |
| [SpoolerFreePrinterNotifyInfo function](..\winsplp\nf-winsplp-spoolerfreeprinternotifyinfo.md) | TBD. |
| [CallRouterFindFirstPrinterChangeNotification function](..\winsplp\nf-winsplp-callrouterfindfirstprinterchangenotification.md) | TBD. |
| [ReplyPrinterChangeNotificationEx function](..\winsplp\nf-winsplp-replyprinterchangenotificationex.md) | TBD. |
| [AppendPrinterNotifyInfoData function](..\winsplp\nf-winsplp-appendprinternotifyinfodata.md) | The print spooler's AppendPrinterNotifyInfoData function adds the contents of a specified PRINTER_NOTIFY_INFO_DATA structure to a specified PRINTER_NOTIFY_INFO structure. |
| [PartialReplyPrinterChangeNotification function](..\winsplp\nf-winsplp-partialreplyprinterchangenotification.md) | The print spooler's PartialReplyPrinterChangeNotification function allows a print provider to update the spooler's database of printer changes associated with a notification handle. |
| [XcvClosePort function](..\winsplp\nf-winsplp-xcvcloseport.md) | A port monitor server DLL's XcvClosePort function closes a printer port that was opened by XcvOpenPort. |
| [PrintDocumentOnPrintProcessor function](..\winsplp\nf-winsplp-printdocumentonprintprocessor.md) | A print processor's PrintDocumentOnPrintProcessor function converts a print job from a spooled format into raw data that can be sent to a print monitor. |
| [GenerateCopyFilePaths function](..\winsplp\nf-winsplp-generatecopyfilepaths.md) | A Point and Print DLL's GenerateCopyFilePaths function is used for modifying the source and destination paths used by print spoolers when they copy print queue-associated files to a print client. |
| [ReadPort function](..\winsplp\nf-winsplp-readport.md) | A port monitor's ReadPort function reads data from a printer port. |
| [LogJobInfoForBranchOffice function](..\winsplp\nf-winsplp-logjobinfoforbranchoffice.md) | Allows Branch Office clients to send job events to the host print server. |
| [WritePort function](..\winsplp\nf-winsplp-writeport.md) | A port monitor's WritePort function writes data to a printer port. |
| [SpoolerRefreshPrinterChangeNotification function](..\winsplp\nf-winsplp-spoolerrefreshprinterchangenotification.md) | TBD. |
| [SplPromptUIInUsersSession function](..\winsplp\nf-winsplp-splpromptuiinuserssession.md) | The SplPromptUIInUsersSession function displays a standard message box in the session indicated by the printer handle and job ID. |
| [SplIsSessionZero function](..\winsplp\nf-winsplp-splissessionzero.md) | The SplIsSessionZero function determines whether a certain print job (print handle plus job ID) was issued in session zero. |
| [GetJobAttributesEx function](..\winsplp\nf-winsplp-getjobattributesex.md) | Warning  Starting with Windows 10, the APIs which support third-party print providers are deprecated. |
| [DevQueryPrint function](..\winsplp\nf-winsplp-devqueryprint.md) | TBD. |
| [SpoolerCopyFileEvent function](..\winsplp\nf-winsplp-spoolercopyfileevent.md) | A Point and Print DLL's SpoolerCopyFileEvent function receives notifications of events associated with copying print queue-associated files to a print client, when the client connects to a print server. |
| [SpoolerFindFirstPrinterChangeNotification function](..\winsplp\nf-winsplp-spoolerfindfirstprinterchangenotification.md) | TBD. |
| [XcvOpenPort function](..\winsplp\nf-winsplp-xcvopenport.md) | A port monitor server DLL's XcvOpenPort function opens a port for configuration operations. |
| [RouterAllocBidiResponseContainer function](..\winsplp\nf-winsplp-routerallocbidiresponsecontainer.md) | RouterAllocBidiResponseContainer allocates a BIDI_RESPONSE_CONTAINER structure containing a list of bidi responses. The bidi response list is an array of BIDI_RESPONSE_DATA structures. |
| [ImpersonatePrinterClient function](..\winsplp\nf-winsplp-impersonateprinterclient.md) | ImpersonatePrinterClient resumes impersonation of the client, completing the operation begun by RevertToPrinterSelf. |
| [ControlPrintProcessor function](..\winsplp\nf-winsplp-controlprintprocessor.md) | A print processor's ControlPrintProcessor function allows the spooler to control a print job. |
| [InitializePrintMonitor function](..\winsplp\nf-winsplp-initializeprintmonitor.md) | The InitializePrintMonitor function is obsolete and is supported only for compatibility purposes. |
| [RouterAllocBidiMem function](..\winsplp\nf-winsplp-routerallocbidimem.md) | RouterAllocBidiMem allocates a block of memory of a specified size. This function is used by the port monitor to allocate memory for strings and binary objects. |
| [InitializePrintProvidor function](..\winsplp\nf-winsplp-initializeprintprovidor.md) | Warning  Starting with Windows 10, the APIs which support third-party print providers are deprecated. |
| [RouterFreeBidiMem function](..\winsplp\nf-winsplp-routerfreebidimem.md) | RouterFreeBidiMem frees a block of memory that was previously allocated by RouterAllocBidiMem. |
| [RouterFreeBidiResponseContainer function](..\winsplp\nf-winsplp-routerfreebidiresponsecontainer.md) | RouterFreeBidiResponseContainer frees a BIDI_RESPONSE_CONTAINER structure previously allocated by RouterAllocBidiResponseContainer. |
| [PlayGdiScriptOnPrinterIC function](..\winsplp\nf-winsplp-playgdiscriptonprinteric.md) | TBD. |
| [DeletePrinterIC function](..\winsplp\nf-winsplp-deleteprinteric.md) | TBD. |
Struct

| Title        | Description    |
| ------------- |:-------------:|
| [SPLCLIENT_INFO_3_VISTA structure](..\winsplp\ns-winsplp--splclient-info-3-vista.md) | Contains a super-set of the information in both a SPLCLIENT_INFO_1 and SPLCLIENT_INFO_2 structure. It also contains additional information needed by the provider. |
| [NOTIFICATION_CONFIG_1 structure](..\winsplp\ns-winsplp--notification-config-1.md) | TBD. |
| [PBranchOfficeJobDataPrinted structure](..\winsplp\ns-winsplp-pbranchofficejobdataprinted.md) | Contains the necessary data for logging a branch office job completed event on a remote server. This is based on standard job-related data available to the spooler. |
| [PBranchOfficeJobData structure](..\winsplp\ns-winsplp-pbranchofficejobdata.md) | This structure contains the type of event to log (eEventType), the job ID, and the data required by the event. |
| [PBranchOfficeJobDataError structure](..\winsplp\ns-winsplp-pbranchofficejobdataerror.md) | This structure contains the necessary data for logging a branch office job failure event on a remote server. This is based on standard job-related data available to the spooler. |
| [MONITORINIT structure](..\winsplp\ns-winsplp--monitorinit.md) | The MONITORINIT structure is used as an input parameter to a print monitor's InitializePrintMonitor2 function. |
| [SPLCLIENT_INFO_2_V2 structure](..\winsplp\ns-winsplp--splclient-info-2-v2.md) | TBD. |
| [PRINTER_NOTIFY_INIT structure](..\winsplp\ns-winsplp--printer-notify-init.md) | TBD. |
| [MONITOR structure](..\winsplp\ns-winsplp--monitor.md) | The MONITOR structure is obsolete and is supported only for compatibility reasons. |
| [MONITORREG structure](..\winsplp\ns-winsplp--monitorreg.md) | The MONITORREG structure supplies print monitors with the address of registry functions to use instead of Win32 registry API functions. |
| [SPLCLIENT_INFO_1 structure](..\winsplp\ns-winsplp--splclient-info-1.md) | The SPLCLIENT_INFO_1 structure is used as input to the GenerateCopyFilePaths function that is exported by Point and Print DLLs. |
| [MONITORUI structure](..\winsplp\ns-winsplp--monitorui.md) | The MONITORUI structure contains pointers to the functions within a port monitor UI DLL that the print spooler calls. |
| [PBranchOfficeLogOfflineFileFull structure](..\winsplp\ns-winsplp-pbranchofficelogofflinefilefull.md) | Contains the necessary data for logging that the offline log archive on the current client overflowed at some point. |
| [PRINTPROCESSOROPENDATA structure](..\winsplp\ns-winsplp--printprocessoropendata.md) | The PRINTPROCESSOROPENDATA structure is used as an input parameter to a print processor's OpenPrintProcessor function. |
| [MONITOREX structure](..\winsplp\ns-winsplp--monitorex.md) | The MONITOREX structure is obsolete and supported for compatibility purposes only. |
| [PBranchOfficeJobDataPipelineFailed structure](..\winsplp\ns-winsplp-pbranchofficejobdatapipelinefailed.md) | Contains the necessary data for logging a branch office job Pipeline Rendering Failed event on a remote server. This is based on standard job-related data available to the spooler. |
| [PSHOWUIPARAMS structure](..\winsplp\ns-winsplp-pshowuiparams.md) | The SplPromptUIInUsersSession function uses the SHOWUIPARAMS structure to hold information about the appearance and behavior of a message box. |
| [PBranchOfficeJobDataRendered structure](..\winsplp\ns-winsplp-pbranchofficejobdatarendered.md) | Contains the necessary data for logging a branch office job Pipeline Rendering Event on a remote server. This is based on job-related data available to the spooler. |
| [LPBranchOfficeJobDataContainer structure](..\winsplp\ns-winsplp-lpbranchofficejobdatacontainer.md) | This structure defines a container for one or more BranchOfficeJobData structures to sent to a server. |
| [SPLCLIENT_INFO_2_V1 structure](..\winsplp\ns-winsplp--splclient-info-2-v1.md) | Contains the handle for the server-side printer that is used to make direct API calls from the client to the server without the overhead of the RPC. |
| [PMESSAGEBOX_PARAMS structure](..\winsplp\ns-winsplp-pmessagebox-params.md) | The MESSAGEBOX_PARAMS structure is used by the SplPromptUIInUsersSession function to hold information about the appearance and behavior of a message box. |
| [SPLCLIENT_INFO_2_V3 structure](..\winsplp\ns-winsplp--splclient-info-2-v3.md) | TBD. |
Callback

| Title        | Description    |
| ------------- |:-------------:|
| [ROUTER_NOTIFY_CALLBACK callback](..\winsplp\nc-winsplp-router-notify-callback.md) | TBD. |
Enum

| Title        | Description    |
| ------------- |:-------------:|
| [NOTIFICATION_CALLBACK_COMMANDS enumeration](..\winsplp\ne-winsplp--notification-callback-commands.md) | TBD. |
| [UI_TYPE enumeration](..\winsplp\ne-winsplp-ui-type.md) | TBD. |
| [NOTIFICATION_CONFIG_FLAGS enumeration](..\winsplp\ne-winsplp--notification-config-flags.md) | TBD. |
Function

| Title        | Description    |
| ------------- |:-------------:|
| [FindFirstPrinterChangeNotification function](..\winspool\nf-winspool-findfirstprinterchangenotification.md) | Warning  Starting with Windows 10, the APIs which support third-party print providers are deprecated. |
| [PrinterMessageBoxW function](..\winspool\nf-winspool-printermessageboxw.md) | TBD. |
| [GetPrintOutputInfo function](..\winspool\nf-winspool-getprintoutputinfo.md) | TBD. |
| [PrinterMessageBoxA function](..\winspool\nf-winspool-printermessageboxa.md) | TBD. |
| [ExtDeviceMode function](..\winspool\nf-winspool-extdevicemode.md) | The ExtDeviceMode function is provided only for compatibility with 16-bit applications. |
| [GetJobNamedPropertyValue function](..\winspool\nf-winspool-getjobnamedpropertyvalue.md) | Retrieves the value of the named property for the specified print job on the specified printer. |
| [WaitForPrinterChange function](..\winspool\nf-winspool-waitforprinterchange.md) | TBD. |
| [FreePrintPropertyValue function](..\winspool\nf-winspool-freeprintpropertyvalue.md) | Frees the value that is retrieved using GetJobNamedPropertyValue function. |
| [EnumJobNamedProperties function](..\winspool\nf-winspool-enumjobnamedproperties.md) | TBD. |
| [SetJobNamedProperty function](..\winspool\nf-winspool-setjobnamedproperty.md) | TBD. |
| [DeleteJobNamedProperty function](..\winspool\nf-winspool-deletejobnamedproperty.md) | Deletes the named property for the specified print job on the specified printer. |
| [FreePrintNamedPropertyArray function](..\winspool\nf-winspool-freeprintnamedpropertyarray.md) | TBD. |
Struct

| Title        | Description    |
| ------------- |:-------------:|
| [PrintPropertyValue structure](..\winspool\ns-winspool-printpropertyvalue.md) | TBD. |
| [BIDI_DATA structure](..\winspool\ns-winspool--bidi-data.md) | The BIDI_DATA structure is used to store the values of a bidi schema. |
| [BIDI_RESPONSE_DATA structure](..\winspool\ns-winspool--bidi-response-data.md) | The BIDI_RESPONSE_DATA structure holds a single bidi response. |
| [PrintPropertiesCollection structure](..\winspool\ns-winspool-printpropertiescollection.md) | TBD. |
| [BIDI_RESPONSE_CONTAINER structure](..\winspool\ns-winspool--bidi-response-container.md) | The BIDI_RESPONSE_CONTAINER structure is a container for a list of bidi responses. |
| [BIDI_REQUEST_CONTAINER structure](..\winspool\ns-winspool--bidi-request-container.md) | The BIDI_REQUEST_CONTAINER structure is a container for a list of bidi requests. |
| [BIDI_REQUEST_DATA structure](..\winspool\ns-winspool--bidi-request-data.md) | The BIDI_REQUEST_DATA structure holds a single bidi request. |
| [BINARY_CONTAINER structure](..\winspool\ns-winspool--binary-container.md) | The BINARY_CONTAINER structure is a container for binary data. |
| [PrintNamedProperty structure](..\winspool\ns-winspool-printnamedproperty.md) | TBD. |
Enum

| Title        | Description    |
| ------------- |:-------------:|
| [BIDI_TYPE enumeration](..\winspool\ne-winspool-bidi-type.md) | The BIDI_TYPE enumeration lists the possible values of data transferred in a bidi operation. |
Function

| Title        | Description    |
| ------------- |:-------------:|
| [IXpsRasterizationFactory2::CreateRasterizer method](..\xpsrassvc\nf-xpsrassvc-ixpsrasterizationfactory2-createrasterizer.md) | The CreateRasterizer method creates an XPS rasterizer object that can convert content from XPS to PWG Raster using the XPS Rasterization Service. PWG Raster supports non-square DPIs. |
| [IXpsRasterizerNotificationCallback::Continue method](..\xpsrassvc\nf-xpsrassvc-ixpsrasterizernotificationcallback-continue.md) | The Continue method tells the caller (the XPS rasterization service) whether to continue rasterizing the current XPS fixed page. |
| [IXpsRasterizer::SetMinimalLineWidth method](..\xpsrassvc\nf-xpsrassvc-ixpsrasterizer-setminimallinewidth.md) | The SetMinimalLineWidth method allows the caller to set the minimum thickness (in pixels) of the lines that the device can render. |
| [IXpsRasterizationFactory::CreateRasterizer method](..\xpsrassvc\nf-xpsrassvc-ixpsrasterizationfactory-createrasterizer.md) | The CreateRasterize method creates an XPS rasterizer object. |
| [IXpsRasterizer::RasterizeRect method](..\xpsrassvc\nf-xpsrassvc-ixpsrasterizer-rasterizerect.md) | The RasterizeRect method rasterizes an axis-aligned, rectangular region of an XPS fixed page. |


This technology is in the following headers:


| Header        | 

| [bidispl](..\bidispl\~PORTAL~bidispl.md) | 

| [compstui](..\compstui\~PORTAL~compstui.md) | 

| [filterpipeline](..\filterpipeline\~PORTAL~filterpipeline.md) | 

| [icm](..\icm\~PORTAL~icm.md) | 

| [mxdc](..\mxdc\~PORTAL~mxdc.md) | 

| [prcomoem](..\prcomoem\~PORTAL~prcomoem.md) | 

| [prdrvcom](..\prdrvcom\~PORTAL~prdrvcom.md) | 

| [printerextension](..\printerextension\~PORTAL~printerextension.md) | 

| [printoem](..\printoem\~PORTAL~printoem.md) | 

| [prnasntp](..\prnasntp\~PORTAL~prnasntp.md) | 

| [tcpxcv](..\tcpxcv\~PORTAL~tcpxcv.md) | 

| [winddiui](..\winddiui\~PORTAL~winddiui.md) | 

| [winppi](..\winppi\~PORTAL~winppi.md) | 

| [winsplp](..\winsplp\~PORTAL~winsplp.md) | 

| [winspool](..\winspool\~PORTAL~winspool.md) | 

| [xpsrassvc](..\xpsrassvc\~PORTAL~xpsrassvc.md) | 