---
title: "데이터 개체 및 데이터 소스: 생성 및 소멸 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "데이터 개체[C++], 만들기"
  - "데이터 개체[C++], 소멸"
  - "데이터 소스 개체[C++], 만들기"
  - "데이터 소스 개체[C++], 소멸"
  - "데이터 소스[C++], 및 데이터 개체"
  - "데이터 소스[C++], 만들기"
  - "데이터 소스[C++], 소멸"
  - "데이터 소스[C++], 역할"
  - "데이터 개체 제거"
  - "소멸[C++], 데이터 개체"
  - "소멸[C++], 데이터 소스"
  - "개체 만들기[C++], 데이터 소스 개체"
ms.assetid: ac216d54-3ca5-4ce7-850d-cd1f6a90d4f1
caps.latest.revision: 14
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 데이터 개체 및 데이터 소스: 생성 및 소멸
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

문서 [데이터 개체 및 데이터 소스\(OLE\)](../mfc/data-objects-and-data-sources-ole.md)에 설명된 대로 데이터 개체와 데이터 소스는 데이터 전송의 양쪽을 나타냅니다.  이 문서에서는 다음을 포함하여 데이터 전송을 제대로 수행하기 위해 이들 개체 및 소스를 만들고 제거할 경우에 대해 설명합니다.  
  
-   [데이터 개체 만들기](#_core_creating_data_objects)  
  
-   [데이터 개체 제거](#_core_destroying_data_objects)  
  
-   [데이터 소스 만들기](#_core_creating_data_sources)  
  
-   [데이터 소스 제거](#_core_destroying_data_sources)  
  
##  <a name="_core_creating_data_objects"></a> 데이터 개체 만들기  
 데이터 개체는 대상 응용 프로그램인 클라이언트 또는 서버에서 사용됩니다.  대상 응용 프로그램의 데이터 개체는 소스 응용 프로그램과 대상 응용 프로그램 간 연결의 한쪽 끝입니다.  대상 응용 프로그램의 데이터 개체는 데이터 소스의 데이터에 액세스하고 데이터와 상호 작용하는 데 사용됩니다.  
  
 데이터 개체를 필요한 두 가지 일반적인 경우가 있습니다.  첫 번째 상황은 끌어서 놓기를 사용하여 응용 프로그램에서 데이터를 삭제하는 경우입니다.  두 번째 상황은 편집 메뉴에서 붙여넣기 또는 선택하여 붙여넣기를 선택하는 경우입니다.  
  
 끌어서 놓기 상황에서는 데이터 개체를 만들 필요가 없습니다.  기존 데이터 개체에 대한 포인터는 `OnDrop` 함수에 전달됩니다.  이 데이터 개체는 프레임워크를 통해 끌어서 놓기 작업 일부로 만들어지고 프레임워크를 통해 제거됩니다.  다른 메서드에서 붙여넣기가 수행될 때 항상 이 경우에 해당하는 것은 아닙니다.  자세한 내용은 [데이터 개체 제거](#_core_destroying_data_objects)를 참조하세요.  
  
 응용 프로그램에서 붙여넣기 또는 선택하여 붙여넣기 작업을 수행할 경우 `COleDataObject` 개체를 만들고 해당 `AttachClipboard` 멤버 함수를 호출해야 합니다.  이렇게 하면 데이터 개체가 클립보드의 데이터와 연결됩니다.  그런 다음 붙여넣기 함수에서 이 데이터 개체를 사용할 수 있습니다.  
  
##  <a name="_core_destroying_data_objects"></a> 데이터 개체 제거  
 [데이터 개체 만들기](#_core_creating_data_objects)에 설명된 체계를 따를 경우 데이터 개체 제거는 데이터 전송의 사소한 측면입니다.  붙여넣기 함수에서 만들어진 데이터 개체는 붙여넣기 함수가 반환될 때 MFC를 통해 제거됩니다.  
  
 붙여넣기 작업을 처리하는 또 다른 방법을 따를 경우 붙여넣기 작업이 완료된 후 데이터 개체가 제거되어야 합니다.  데이터 개체가 제거될 때까지 응용 프로그램에서는 데이터를 클립보드에 복사할 수 없습니다.  
  
##  <a name="_core_creating_data_sources"></a> 데이터 소스 만들기  
 데이터 소스는 데이터 전송의 클라이언트 또는 서버 쪽이 될 수 있는 데이터 전송의 소스에서 사용됩니다.  소스 응용 프로그램의 데이터 소스는 소스 응용 프로그램과 대상 응용 프로그램 간 연결의 한쪽 끝입니다.  대상 응용 프로그램의 데이터 개체는 데이터 소스의 데이터와 상호 작용하는 데 사용됩니다.  
  
 데이터 소스는 응용 프로그램에서 데이터를 클립보드에 복사해야 할 때 생성됩니다.  다음과 같은 일반적인 시나리오가 실행됩니다.  
  
1.  사용자가 일부 데이터를 선택합니다.  
  
2.  사용자가 **편집** 메뉴에서 **복사**\(또는 **잘라내기**\)를 선택하거나 끌어서 놓기 작업을 시작합니다.  
  
3.  프로그램의 디자인에 따라 응용 프로그램에서는 `COleDataSource` 개체 또는 `COleDataSource`에서 파생 클래스 개체를 만듭니다.  
  
4.  선택한 데이터는 `COleDataSource::CacheData` 또는 `COleDataSource::DelayRenderData` 그룹의 함수 중 하나를 호출하는 방식으로 데이터 소스에 삽입됩니다.  
  
5.  응용 프로그램에서는 3단계에서 생성된 개체에 속한 `SetClipboard` 멤버 함수\(또는 끌어서 놓기 작업인 경우 `DoDragDrop` 멤버 함수\)를 호출합니다.  
  
6.  **잘라내기** 작업이거나 `DoDragDrop`이 `DROPEFFECT_MOVE`를 반환할 경우 1단계에서 선택한 데이터가 문서에서 삭제됩니다.  
  
 이 시나리오는 MFC OLE 샘플 [OCLIENT](../top/visual-cpp-samples.md) 및 [HIERSVR](../top/visual-cpp-samples.md)을 통해 구현됩니다.  `GetClipboardData` 및 `OnGetClipboardData` 함수 외에 모든 함수에 대한 각 응용 프로그램의 `CView` 파생 클래스 소스를 살펴봅니다.  이들 두 함수는 `COleClientItem` 또는 `COleServerItem` 파생 클래스 구현이 포함됩니다.  이들 샘플 프로그램에서는 이러한 개념을 구현하는 방법의 좋은 예를 제공합니다.  
  
 `COleDataSource` 개체를 만들어야 할 한 가지 다른 상황은 끌어서 놓기 작업의 기본 동작을 수정할 경우 발생합니다.  자세한 내용은 [끌어서 놓기: 사용자 지정](../mfc/drag-and-drop-customizing.md) 문서를 참조하세요.  
  
##  <a name="_core_destroying_data_sources"></a> 데이터 소스 제거  
 데이터 소스는 현재 데이터 소스를 처리해야 하는 응용 프로그램을 통해 제거되어야 합니다.  [COleDataSource::DoDragDrop](../Topic/COleDataSource::DoDragDrop.md)을 호출하는 것과 같이 데이터 소스를 OLE에 전달하는 경우에는 **pDataSrc\-\>InternalRelease**를 호출해야 합니다.  예:  
  
 [!code-cpp[NVC_MFCListView#1](../mfc/codesnippet/CPP/data-objects-and-data-sources-creation-and-destruction_1.cpp)]  
  
 데이터를 OLE에 전달하지 않은 경우에는 사용자가 일반적인 C\+\+ 개체를 제거하는 것처럼 데이터 소스를 제거해야 합니다.  
  
 자세한 내용은 [끌어서 놓기](../mfc/drag-and-drop-ole.md), [클립보드](../mfc/clipboard.md) 및 [데이터 개체 및 데이터 소스 조작](../mfc/data-objects-and-data-sources-manipulation.md)을 참조하세요.  
  
## 참고 항목  
 [데이터 개체 및 데이터 소스\(OLE\)](../mfc/data-objects-and-data-sources-ole.md)   
 [COleDataObject Class](../mfc/reference/coledataobject-class.md)   
 [COleDataSource Class](../mfc/reference/coledatasource-class.md)