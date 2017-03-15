---
title: "데이터 개체 및 데이터 소스: 조작 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "클립보드[C++], 사용 가능한 형식 확인"
  - "클립보드[C++], 형식 정보 전달"
  - "데이터 개체[C++], 조작"
  - "데이터 소스[C++], 데이터 작업"
  - "데이터 소스[C++], 사용 가능한 형식 확인"
  - "데이터 소스[C++], 데이터 삽입"
  - "지연된 렌더링[C++]"
  - "OLE[C++], 데이터 개체"
  - "OLE[C++], 데이터 소스"
ms.assetid: f7f27e77-bb5d-4131-b819-d71bf929ebaf
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 데이터 개체 및 데이터 소스: 조작
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

After a data object or data source has been created, you can perform a number of common operations on the data, such as inserting and removing data, enumerating the formats the data is in, and more.  This article describes the techniques necessary to complete the most common operations.  다음 내용을 다룹니다.  
  
-   [Inserting data into a data source](#_core_inserting_data_into_a_data_source)  
  
-   [Determining the formats available in a data object](#_core_determining_the_formats_available_in_a_data_object)  
  
-   [Retrieving data from a data object](#_core_retrieving_data_from_a_data_object)  
  
##  <a name="_core_inserting_data_into_a_data_source"></a> Inserting Data into a Data Source  
 How data is inserted into a data source depends on whether the data is supplied immediately or on demand, and in which medium it is supplied.  The possibilities are as follows.  
  
### Supplying Data Immediately \(Immediate Rendering\)  
  
-   Call `COleDataSource::CacheGlobalData` repeatedly for every Clipboard format in which you are supplying data.  Pass the Clipboard format to be used, a handle to the memory containing the data and, optionally, a **FORMATETC** structure describing the data.  
  
     또는  
  
-   If you want to work directly with **STGMEDIUM** structures, you call `COleDataSource::CacheData` instead of `COleDataSource::CacheGlobalData` in the option above.  
  
### Supplying Data on Demand \(Delayed Rendering\)  
 This is an advanced topic.  
  
-   Call `COleDataSource::DelayRenderData` repeatedly for every Clipboard format in which you are supplying data.  Pass the Clipboard format to be used and, optionally, a **FORMATETC** structure describing the data.  When the data is requested, the framework will call `COleDataSource::OnRenderData`, which you must override.  
  
     또는  
  
-   If you use a `CFile` object to supply the data, call `COleDataSource::DelayRenderFileData` instead of `COleDataSource::DelayRenderData` in the previous option.  When the data is requested, the framework will call `COleDataSource::OnRenderFileData`, which you must override.  
  
##  <a name="_core_determining_the_formats_available_in_a_data_object"></a> Determining the Formats Available in a Data Object  
 Before an application allows the user to paste data into it, it needs to know if there are formats on the Clipboard that it can handle.  To do this, your application should do the following:  
  
1.  Create a `COleDataObject` object and a **FORMATETC** structure.  
  
2.  Call the data object's `AttachClipboard` member function to associate the data object with the data on the Clipboard.  
  
3.  다음 작업 중 하나를 수행합니다.  
  
    -   Call the data object's `IsDataAvailable` member function if there are only one or two formats you need.  This will save you time in cases where the data on the Clipboard supports significantly more formats than your application.  
  
         또는  
  
    -   Call the data object's `BeginEnumFormats` member function to start enumerating the formats available on the Clipboard.  Then call `GetNextFormat` until the Clipboard returns a format your application supports or there are no more formats.  
  
 If you are using `ON_UPDATE_COMMAND_UI`, you can now enable the Paste and, possibly, Paste Special items on the Edit menu.  To do this, call either `CMenu::EnableMenuItem` or `CCmdUI::Enable`.  For more information about what container applications should do with menu items and when, see [Menus and Resources: Container Additions](../mfc/menus-and-resources-container-additions.md).  
  
##  <a name="_core_retrieving_data_from_a_data_object"></a> 데이터 개체에서 데이터 검색  
 Once you have decided on a data format, all that remains is to retrieve the data from the data object.  To do this, the user decides where to put the data, and the application calls the appropriate function.  The data will be available in one of the following mediums:  
  
|Medium|Function to call|  
|------------|----------------------|  
|Global Memory \(`HGLOBAL`\)|`COleDataObject::GetGlobalData`|  
|File \(`CFile`\)|`COleDataObject::GetFileData`|  
|**STGMEDIUM** structure \(`IStorage`\)|`COleDataObject::GetData`|  
  
 Commonly, the medium will be specified along with its Clipboard format.  For example, a **CF\_EMBEDDEDSTRUCT** object is always in an `IStorage` medium that requires an **STGMEDIUM** structure.  Therefore, you would use `GetData` because it is the only one of these functions that can accept an **STGMEDIUM** structure.  
  
 For cases where the Clipboard format is in an `IStream` or `HGLOBAL` medium, the framework can provide a `CFile` pointer that references the data.  The application can then use file read to get the data in much the same way as it might import data from a file.  Essentially, this is the client\-side interface to the `OnRenderData` and `OnRenderFileData` routines in the data source.  
  
 The user can now insert data into the document just like for any other data in the same format.  
  
### 추가 정보  
  
-   [끌어서 놓기](../mfc/drag-and-drop-ole.md)  
  
-   [클립보드](../mfc/clipboard.md)  
  
## 참고 항목  
 [데이터 개체 및 데이터 소스\(OLE\)](../mfc/data-objects-and-data-sources-ole.md)   
 [COleDataObject Class](../mfc/reference/coledataobject-class.md)   
 [COleDataSource Class](../mfc/reference/coledatasource-class.md)