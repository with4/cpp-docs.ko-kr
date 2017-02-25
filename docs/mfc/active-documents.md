---
title: "액티브 문서 | Microsoft Docs"
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
  - "활성 문서[C++]"
  - "활성 문서[C++], 요구 사항"
  - "활성 문서[C++], 뷰"
  - "OLE[C++], 활성 문서"
  - "뷰 개체, 요구 사항"
  - "뷰[C++], 활성 문서"
ms.assetid: 1378f18e-aaa6-420b-8501-4b974905baa0
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 액티브 문서
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

활성 문서는 OLE의 복합 문서 기술을 확장합니다.  이러한 확장은 보기를 관리하는 추가 인터페이스의 형태로 제공됩니다. 따라서 개체는 컨테이너 안에서 기능할 수 있으며, 디스플레이 및 인쇄 함수에 대한 제어를 여전히 유지할 수 있습니다.  이 프로세스는 외부 프레임\(예:Microsoft Office Binder 또는 Microsoft Internet Explorer\) 및 그리고 원시 프레임\(예:제품 자체의 보기 포트\)에서 문서를 표시하기 위해 이것을 가능하게 합니다.  
  
 이 부분은 기능 위주의 [액티브 문서의 요구 사항](#requirements_for_active_documents)을 설명합니다.  활성 문서는 데이터 집합을 소유하고 데이터가 저장되고 검색되는 저장소의 접근 권한을 가집니다.  그들의 데이터에서 하나 또는 그 이상의 보기를 생성하거나 관리할 수 있습니다.  일반적인 임베딩 및 OLE 문서의 현재 위치 활성화 인터페이스를 지원하는 것에 덧붙여, 활성 문서는 `IOleDocument`를 통해 보기를 생성하는 능력을 통신합니다.  이 인터페이스를 통해, 컨테이너는 활성 문서가 표시할 수 있는 보기를 생성\(가능한 경우 열거\)하는 것을 요청할 수 있습니다.  이 인터페이스를 통해, 활성 문서는 그것이 많은 보기 또는 복잡한 사각형을 지원하는지 여부와 같은 그 스스로에 대한 여러 가지 정보 또한 제공할 수 있습니다.  
  
 다음은 **IOleDocument**  인터페이스입니다.  **IEnumOleDocumentViews** 인터페이스는 **IOleDocumentView \*** 형식을 위한 표준 OLE 열거자라는 것을 참조하십시오.  
  
 `interface IOleDocument : IUnknown`  
  
 `{`  
  
 `HRESULT CreateView(`  
  
 `[in] IOleInPlaceSite *pIPSite,`  
  
 `[in] IStream *pstm,`  
  
 `[in] DWORD dwReserved,`  
  
 `[out] IOleDocumentView **ppView);`  
  
 `HRESULT GetDocMiscStatus([out] DWORD *pdwStatus);`  
  
 `HRESULT EnumViews(`  
  
 `[out] IEnumOleDocumentViews **ppEnum,`  
  
 `[out] IOleDocumentView **ppView);`  
  
 `}`  
  
 모든 활성 문서는 인터페이스를 사용한 보기 프레임 공급자가 있어야 합니다.  문서가 컨테이너에 포함되어 있지 않으면, 활성 문서 서버 스스로가 보기 프레임을 제공해야 합니다.  그러나 활성 문서가 활성 문서 컨테이너에 포함될 때, 컨테이너는 보기 프레임을 제공합니다.  
  
 활성 문서는 하나 또는 그것의 데이터의 [보기](#requirements_for_view_objects)의 여러 형식을 생성할수 있습니다.\(예:일반, 외곽선, 페이지 레이아웃 등\)  보기는 보여진 데이터를 통하여 필터처럼 동작합니다.  문서가 오직 하나의 보기 형식을 가지고 있으면, 사용자는 새 창 기능 지원의 수단으로서 많은 보기를 지원하는 것을 원할 수 있습니다.\(예: 오피스 응용 프로그램의 **창** 메뉴에서 **새 창** 항목\)  
  
##  <a name="requirements_for_active_documents"></a> 액티브 문서에 대한 요구 사항  
 활성 문서 컨테이너에서 표시된 활성 문서는 다음 작업을 수행해야 합니다.  
  
-   OLE의 복합 파일을 `IPersistStorage`을 구현을 통해 그들의 저장 메커니즘으로서 사용합니다.  
  
-   **Create From File**을 포함하여, OLE 문서의 기본 기능 포함을 지원합니다.  이것은 인터페이스 `IPersistFile`, `IOleObject` 및 `IDataObject`을 필요하게 만듭니다.  
  
-   각각 현재 위치에서 활성화가 가능한 하나 또는 그 이상의 보기를 지원합니다.  그것은, 보기는 인터페이스 `IOleInPlaceObject` 및 `IOleInPlaceActiveObject` 뿐만 아니라 인터페이스 `IOleDocumentView`를 지원해야 합니다. \(컨테이너의 **IOleInPlaceSite** 및 **IOleInPlaceFrame** 인터페이스를 사용합니다\)  
  
-   표준 활성화 문서 인터페이스 `IOleDocument`, `IOleCommandTarget` 및 `IPrint`을 지원합니다.  
  
 요구 사항에 내재된 컨테이너 쪽 인터페이스를 언제, 어떻게 사용하느냐에 대한 정보입니다.  
  
##  <a name="requirements_for_view_objects"></a> 보기 개체에 대한 요구사항  
 활성 문서는 하나 이상의 데이터 보기를 만들 수 있습니다.  기능적으로, 이러한 보기는 데이터를 표시하기 위해 특정 메서드로 가는 포트와 비슷합니다.  활성 문서가 오직 단일 보기만 지원하면, 활성 문서 및 단일 보기는 구체적인 단일 클래스를 사용하여 구현될 수 있습니다.  **IOleDocument::CreateView** 같은 개체의 `IOleDocumentView` 인터페이스 포인터를 반환합니다.  
  
 활성 문서 컨테이너 내에서 표시되기 위해, 보기 구성 요소는 `IOleDocumentView`에 더하여 **IOleInPlaceObject**  및 **IOleInPlaceActiveObject**을 지원해야 합니다.  
  
 `interface IOleDocumentView : IUnknown`  
  
 `{`  
  
 `HRESULT SetInPlaceSite([in] IOleInPlaceSite *pIPSite);`  
  
 `HRESULT GetInPlaceSite([out] IOleInPlaceSite **ppIPSite);`  
  
 `HRESULT GetDocument([out] IUnknown **ppunk);`  
  
 `[input_sync] HRESULT SetRect([in] LPRECT prcView);`  
  
 `HRESULT GetRect([in] LPRECT prcView);`  
  
 `[input_sync] HRESULT SetRectComplex(`  
  
 `[in] LPRECT prcView,`  
  
 `[in] LPRECT prcHScroll,`  
  
 `[in] LPRECT prcVScroll,`  
  
 `[in] LPRECT prcSizeBox);`  
  
 `HRESULT Show([in] BOOL fShow);`  
  
 `HRESULT UIActivate([in] BOOL fUIActivate);`  
  
 `HRESULT Open(void);`  
  
 `HRESULT CloseView([in] DWORD dwReserved);`  
  
 `HRESULT SaveViewState([in] IStream *pstm);`  
  
 `HRESULT ApplyViewState([in] IStream *pstm);`  
  
 `HRESULT Clone(`  
  
 `[in] IOleInPlaceSite *pIPSiteNew,`  
  
 `[out] IOleDocumentView **ppViewNew);`  
  
 `}`  
  
 모든 보기는 보기 프레임 및 보기 포트\(HWND 및 그 창의 사각형 영역\)을 캡슐화하는 관련된 보기 사이트를 가집니다.  사이트는 표준 **IOleInPlaceSite** 인터페이스를 통하여 이 기능을 공개합니다.  단일 HWND에서 둘 이상의 보기 포트를 가지는 것이 가능하다는 것을 참조하십시오.  
  
 일반적으로, 각 보기 형식은 다른 인쇄된 표현을 가집니다.  따라서 `IPrint` 및 `IContinueCallback`가 각각인 경우, 보기 및 해당 보기 사이트는 인쇄 인터페이스를 구현해야 합니다.  인쇄가 시작되었을 때, 보기 프레임은 머리글, 바닥글, 여백 및 관련된 요소가 올바르게 인쇄되도록 **IPrint**를 통하여 보기 공급자와 협상해야 합니다.  보기 공급자는 `IContinueCallback`를 통해 인쇄 관련 이벤트를 알립니다.  이러한 인터페이스 사용에 대한 자세한 내용은 [프로그래밍 방식 인쇄](../mfc/programmatic-printing.md)을 참조하십시오.  
  
 활성 문서가 오직 단일 보기만 지원하면, 그 때 활성 문서 및 단일 보기는 구체적인 단일 클래스를 사용하여 구현될 수 있다는 것을 참고하십시오.  **IOleDocument::CreateView** 간단하게 같은 개체의 `IOleDocumentView` 인터페이스 포인터를 반환합니다.  결론적으로, 오직 하나의 보기가 요구된다면 두 개의 분리된 개체 인스턴스가 필요하지 않습니다.  
  
 보기 개체는 또한 명령 대상이 될 수 있습니다.  `IOleCommandTarget`를 구현하여, 보기는 컨테이너의 유저 인터페이스\(**New**, **Open**, **Save As**, **File** 메뉴에서 **Print** 및 **Edit**메뉴에서 **Copy**, **Paste**, **Undo**와 같은\)에서 유래된 명령을 받을 수 있습니다.  자세한 내용은 [메시지 처리 및 명령 대상](../mfc/message-handling-and-command-targets.md)을 참조하십시오.  
  
## 참고 항목  
 [액티브 문서 포함](../mfc/active-document-containment.md)