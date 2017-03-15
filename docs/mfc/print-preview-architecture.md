---
title: "인쇄 미리 보기 아키텍처 | Microsoft Docs"
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
  - "인쇄 미리 보기"
  - "인쇄 미리 보기, 아키텍처"
  - "인쇄 미리 보기, MFC 수정"
  - "인쇄 미리 보기, 프로세스"
  - "인쇄[MFC], 인쇄 미리 보기"
ms.assetid: 0efc87e6-ff8d-43c5-9d72-9b729a169115
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 인쇄 미리 보기 아키텍처
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 MFC 프레임 워크가 인쇄 미리보기 기능을 구현하는 방법을 설명합니다.  다음 내용에 대해 다룹니다.  
  
-   [인쇄 미리보기 프로세스](#_core_the_print_preview_process)  
  
-   [인쇄 미리보기 수정](#_core_modifying_print_preview)  
  
 인쇄 미리보기는 장치에서 이미지를 직접 그리는 대신에, 응용 프로그램이 화면을 사용하여 프린터를 시뮬레이션 해야하기 때문에 화면 표시 및 인쇄와는 다소 차이가 있습니다.  이것을 수용하기 위해, MFC 라이브러리는 [CDC 클래스](../mfc/reference/cdc-class.md)에서 파생된, **CPreviewDC**라는 이름의 특수\(문서화 되지 않은\) 클래스를 정의합니다.  모든 `CDC` 개체는 두 개의 디바이스 컨텍스트를 포함하지만, 그들은 일반적으로 동일합니다.  **CPreviewDC**에서, 이는 다릅니다 : 첫 번째는 프린터가 시뮬레이션 중임을 나타내며, 두 번째는 실제로 표시되는 출력 화면을 나타냅니다.  
  
##  <a name="_core_the_print_preview_process"></a> 인쇄 미리보기 프로세스  
 **File** 메뉴에서 사용자가 프린터 미리보기 커맨드를 선택할 때, framework는 **CPreviewDC** 개체를 생성합니다.  응용 프로그램이 프린터 디바이스 컨텍스트의 특성을 설정하는 작업을 수행할 때마다, framework도 화면 디바이스 컨텍스트에서 비슷한 작업을 수행합니다.  예를 들어, 응용 프로그램이 인쇄용 글꼴을 선택하면, framework는 인쇄 글꼴을 시뮬레이션하는 화면 표시용 글꼴을 선택합니다.  응용 프로그램이 프린터에 출력을 전송할 때마다, framework는 대신 스크린으로 출력을 전송합니다.  
  
 각 문서 페이지를 그리는 인쇄 미리보기는 인쇄와 순서가 다릅니다.  인쇄하는 동안, 특정 페이지의 범위가 렌더링될 때까지 framework는 인쇄를 계속 반복합니다.  인쇄 미리보기 중, 하나 또는 두 개의 페이지가 언제나 표시된 다음, 응용 프로그램은 대기합니다. 그리고 사용자가 응답할 때까지 더 이상의 페이지가 표시되지 않습니다.  인쇄 미리보기 중, 일반 화면 디스플레이가 그러하듯 응용 프로그램도 `WM_PAINT` 메세지에 응답해야 합니다.  
  
 미리보기 모드가 호출되었을 때, 인쇄 작업의 시작 부분에서와 마찬가지로 [CView::OnPreparePrinting](../Topic/CView::OnPreparePrinting.md) 함수가 호출됩니다.  이 함수에 전달되는 [CPrintInfo Structure](../mfc/reference/cprintinfo-structure.md)구조체는 몇몇 멤버를 포함합니다. 멤버의 값은 인쇄 미리보기 작업의 특정 성질을 조정하도록 설정할 수 있습니다.  예를 들어, 한 페이지 또는 두 페이지 모드에서 문서 미리보기를 원하는지 여부를 지정하기 위해 **m\_nNumPreviewPages** 멤버를 설정할 수 있습니다.  
  
##  <a name="_core_modifying_print_preview"></a> 인쇄 미리보기 수정  
 사용자는 여러 가지 방법으로 쉽게 인쇄 미리보기의 동작과 모양을 수정할 수 있습니다.  예를 들어, 다른 것들 중 가능합니다.  
  
-   문서의 모든 페이지에 쉽게 액세스할 수 있는 스크롤 막대를 표시하는 인쇄 미리보기 창이 발생합니다.  
  
-   인쇄 미리보기가 표시를 현재 페이지에서 시작함으로써 문서 내에서 사용자의 위치를 유지하도록 합니다.  
  
-   인쇄 미리보기 및 인쇄를 위해 수행된 다른 초기화가 발생합니다.  
  
-   사용자 고유의 형식으로 페이지 번호를 표시하는 인쇄 미리보기가 발생합니다.  
  
 문서가 얼마나 긴지 알고 있다면, 적절한 값을 사용하여 `SetMaxPage`를 호출합니다. framework는 인쇄 동안과 마찬가지로 미리보기 모드에서 이 정보를 사용할 수 있습니다.  프레임워크가 문서의 길이를 알면, 사용자가 미리보기 모드에서 문서를 앞뒤로 탐색할 수 있는 스크롤바를 포함한 미리보기 창을 제공할 수 있습니다.  사용자가 문서의 길이를 설정하지 않은 경우, framework는 현재 위치를 나타내는 스크롤 상자를 배치할 수 없으므로 framework는 스크롤 막대를 덧붙일 수 없습니다.  이 경우, 문서를 탐색하려면 사용자는 반드시 미리보기 창 내 컨트롤 바의 다음 페이지 및 이전 페이지 버튼을 사용해야 합니다.  
  
 인쇄 미리보기를 위해서는 일반적인 인쇄에서 결코 그렇게 하지 않는다고 하더라도 값을 `m_nCurPage` 멤버의 `CPrintInfo`에 지정하는 것이 유용합니다.  일반 인쇄 중에, 이 멤버는 framework로부터의 정보를 사용자의 뷰 클래스로 전달합니다.  이것이 프레임워크가 어떤 페이지가 출력되어야 하는지를 뷰에게 전달하는 방법입니다.  
  
 반대로, 인쇄 미리보기 모드가 시작될 때, `m_nCurPage` 멤버는 정보를 반대 방향인 뷰에서 framework로 전달합니다.  framework는 처음 보여져야 하는 페이지를 결정하기 위해 이 멤버의 값을 사용합니다.  이 멤버의 기본값이 1이므로 문서의 첫 페이지가 처음으로 표시됩니다.  사용자는 이 멤버를 인쇄 미리보기 명령이 호출되었을 때 보여지는 페이지의 수로 설정하기 위해서 `OnPreparePrinting`를 재정의할 수 있습니다.  이 방법으로, 일반 출력 모드에서 인쇄 미리보기 모드로 이동할 때 응용 프로그램이 사용자의 현재 위치를 유지합니다.  
  
 때때로 사용자는 출력 작업을 위해 출력되는지 또는 출력 미리보기를 위해 호출되는지의 여부에 따라 다른 초기화를 수행하는  `OnPreparePrinting`를 원할 수도 있습니다.  사용자는 이것을 `CPrintInfo` 구조체에서 **m\_bPreview** 멤버 변수를 검사하는 것에 의해 알아낼 수 있습니다.  인쇄 미리보기가 호출되었을 때, 이 멤버는 **TRUE**로 설정됩니다.  
  
 `CPrintInfo` 구조체는 또한 단일 페이지 및 다중 페이지 모드에서 화면의 끝에 표시된 문자열의 서식을 지정하는 데 사용되는 **m\_strPageDesc**로 명명된 멤버를 포함합니다.  이러한 문자열은 기본적으로 "페이지 *n*" 및 "페이지 *n*" 양식입니다.   \- *m*," 그러나 `OnPreparePrinting`로 **m\_strPageDesc**를 수정할 수 있으며 문자열을 더 정교한 것으로 설정할 수 있습니다.  자세한 내용은 *MFC Reference*의 [CPrintInfo Structure](../mfc/reference/cprintinfo-structure.md)를 참조하십시오.  
  
## 참고 항목  
 [인쇄 및 인쇄 미리 보기](../mfc/printing-and-print-preview.md)   
 [인쇄](../mfc/printing.md)   
 [CView Class](../mfc/reference/cview-class.md)   
 [CDC 클래스](../mfc/reference/cdc-class.md)