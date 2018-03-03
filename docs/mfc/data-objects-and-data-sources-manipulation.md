---
title: "데이터 개체 및 데이터 소스: 조작 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- data objects [MFC], manipulating
- data sources [MFC], data operations
- data sources [MFC], inserting data
- Clipboard [MFC], determining available formats
- OLE [MFC], data objects
- Clipboard [MFC], passing format information
- data sources [MFC], determining available formats
- delayed rendering [MFC]
- OLE [MFC], data sources
ms.assetid: f7f27e77-bb5d-4131-b819-d71bf929ebaf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 40bd83b2e472ff1b1e5d277c27a801b0750fb160
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="data-objects-and-data-sources-manipulation"></a>데이터 개체 및 데이터 소스: 조작
데이터 개체 또는 데이터 소스를 만든 후에 다양 한이 다음에 데이터 형식을 열거 데이터 삽입 및 제거 등의 데이터 등에 대 한 일반적인 작업을 수행할 수 있습니다. 이 문서에는 가장 일반적인 작업을 완료 하는 데 필요한 기술을 설명 합니다. 다음과 같은 내용을 다룹니다.  
  
-   [데이터 원본에 데이터 삽입](#_core_inserting_data_into_a_data_source)  
  
-   [데이터 개체에서 사용할 수 있는 형식 확인](#_core_determining_the_formats_available_in_a_data_object)  
  
-   [데이터 개체에서 데이터 검색](#_core_retrieving_data_from_a_data_object)  
  
##  <a name="_core_inserting_data_into_a_data_source"></a>데이터 원본에 데이터 삽입  
 데이터가 즉시 제공 여부에 따라 달라 집니다 데이터 소스에 데이터를 삽입 하는 방법 또는 필요에 따라 및는 미디어에서 제공 합니다. 이 속성은 다음과 같습니다.  
  
### <a name="supplying-data-immediately-immediate-rendering"></a>즉시 데이터 (즉시 렌더링)를 제공합니다.  
  
-   호출 `COleDataSource::CacheGlobalData` 반복 해 서 데이터를 제공 하는 모든 클립보드 형식에 대 한 합니다. 사용 되는 클립보드 형식 전달 데이터를 포함 하는 메모리에 대 한 핸들 및 선택적으로 **FORMATETC** 데이터를 설명 하는 구조입니다.  
  
     또는  
  
-   직접 사용 하려는 경우 **STGMEDIUM** 호출 하는 구조를 `COleDataSource::CacheData` 대신 `COleDataSource::CacheGlobalData` 위의 옵션입니다.  
  
### <a name="supplying-data-on-demand-delayed-rendering"></a>(지연 된 렌더링) 요청 시 데이터 제공  
 고급 항목입니다.  
  
-   호출 `COleDataSource::DelayRenderData` 반복 해 서 데이터를 제공 하는 모든 클립보드 형식에 대 한 합니다. 사용 되는 클립보드 형식 전달 및 필요에 따라 한 **FORMATETC** 데이터를 설명 하는 구조입니다. 데이터 요청 되 면 프레임 워크를 호출 합니다 `COleDataSource::OnRenderData`를 재정의 해야 하 합니다.  
  
     또는  
  
-   사용 하는 경우는 `CFile` 데이터를 제공 하는 개체 호출 `COleDataSource::DelayRenderFileData` 대신 `COleDataSource::DelayRenderData` 이전 옵션에 있습니다. 데이터 요청 되 면 프레임 워크를 호출 합니다 `COleDataSource::OnRenderFileData`를 재정의 해야 하 합니다.  
  
##  <a name="_core_determining_the_formats_available_in_a_data_object"></a>데이터 개체에서 사용할 수 있는 형식 확인  
 응용 프로그램을 사용 하면 데이터를 붙여, 전에 처리할 수 있는 클립보드에 형식이 있는지 확인 해야 합니다. 응용 프로그램이이 수행 하려면 다음을 수행 해야 합니다.  
  
1.  만들기는 `COleDataObject` 개체 및 **FORMATETC** 구조입니다.  
  
2.  데이터 개체의 `AttachClipboard` 를 클립보드에 데이터와 데이터 개체를 연결 하려면 멤버 함수입니다.  
  
3.  다음 작업 중 하나를 수행합니다.  
  
    -   데이터 개체의 `IsDataAvailable` 만 하나 또는 두 형식을 지정 하는 경우 멤버 함수에 필요 합니다. 시간을 절약할 수 있는 응용 프로그램 보다 훨씬 많은 형식의 지 원하는 클립보드에 데이터의 경우이 됩니다.  
  
         또는  
  
    -   데이터 개체의 `BeginEnumFormats` 멤버 함수를 클립보드에 사용할 수 있는 형식 열거를 시작 합니다. 그런 다음 호출 `GetNextFormat` 클립보드 반환 될 때까지 형식 응용 프로그램에서 지원 또는 자세한 형식이 없습니다.  
  
 사용 중인 경우 `ON_UPDATE_COMMAND_UI`, 이제는 붙여넣기에 있는 항목과, 예를 들어, 붙여넣기 편집 메뉴를 사용할 수 있습니다. 이 작업을 수행 하려면 하나를 호출 `CMenu::EnableMenuItem` 또는 `CCmdUI::Enable`합니다. 컨테이너에 대 한 자세한 내용은 응용 프로그램 해야 메뉴 항목을 사용 하 여 수행할 및 시기, 참조 [메뉴 및 리소스: 컨테이너 추가](../mfc/menus-and-resources-container-additions.md)합니다.  
  
##  <a name="_core_retrieving_data_from_a_data_object"></a>데이터 개체에서 데이터 검색  
 데이터 형식에 결정 했으면, 남았습니다 데이터 개체에서 데이터를 검색 합니다. 이 수행 하려면 사용자가을 데이터를 저장할 위치를 결정 하 고 응용 프로그램에서 적절 한 함수를 호출 합니다. 데이터는 다음 미디어 중 하나에서 사용할 수 있습니다.  
  
|중간|호출할 함수|  
|------------|----------------------|  
|전역 메모리 (`HGLOBAL`)|`COleDataObject::GetGlobalData`|  
|파일 (`CFile`)|`COleDataObject::GetFileData`|  
|**STGMEDIUM** 구조 (`IStorage`)|`COleDataObject::GetData`|  
  
 일반적으로 미디어 함께 클립보드 형식으로 지정 됩니다. 예를 들어 한 **CF_EMBEDDEDSTRUCT** 개체는 항상는 `IStorage` 보통 필요로 하는 **STGMEDIUM** 구조입니다. 따라서 사용 `GetData` 수락할 수 있는 이러한 함수 중 하나만 있기 때문에 프로그램 **STGMEDIUM** 구조입니다.  
  
 클립보드 형식에 있는 경우에는 `IStream` 또는 `HGLOBAL` 보통, 프레임 워크를 제공할 수 있습니다는 `CFile` 데이터를 참조 하는 포인터입니다. 응용 프로그램을 파일에서 데이터를 가져올 때 해당 데이터를 동일한 방식으로 얻기 위해 읽을 파일을 유도할 수 있습니다. 기본적으로,이에 대 한 클라이언트 쪽 인터페이스는 `OnRenderData` 및 `OnRenderFileData` 데이터 원본의 루틴입니다.  
  
 사용자에는 동일한 형식의 다른 모든 데이터에 대 한 문서에 데이터 삽입 마찬가지로 이제 수 있습니다.  
  
### <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [끌어서 놓기](../mfc/drag-and-drop-ole.md)  
  
-   [클립보드](../mfc/clipboard.md)  
  
## <a name="see-also"></a>참고 항목  
 [데이터 개체 및 데이터 소스 (OLE)](../mfc/data-objects-and-data-sources-ole.md)   
 [COleDataObject 클래스](../mfc/reference/coledataobject-class.md)   
 [COleDataSource 클래스](../mfc/reference/coledatasource-class.md)
