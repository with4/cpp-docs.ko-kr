---
title: "액티브 문서 컨테이너 응용 프로그램 만들기 | Microsoft Docs"
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
  - "액티브 문서 컨테이너[C++], 만들기"
  - "활성 문서[C++], 컨테이너"
  - "응용 프로그램[MFC], 액티브 문서 컨테이너"
  - "컨테이너[C++], 활성 문서"
  - "MFC COM[C++], 활성 문서 포함"
ms.assetid: 14e2d022-a6c5-4249-8712-706b0f4433f7
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 액티브 문서 컨테이너 응용 프로그램 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

액티브 문서 컨테이너 응용 프로그램을 생성하는 가장 간단하고 권장되는 방법은 MFC 응용 프로그램 마법사를 사용하여 MFX EXE 컨테이너 응용 프로그램을 생성하는 것입니다. 그 다음 액티브 문서 컨테이너를 서포트하는 응용 프로그램을 수정합니다.  
  
#### 액티브 문서 컨테이너 응용 프로그램 만들기  
  
1.  **파일** 메뉴에서 **새로 만들기** 하위 메뉴에서 **프로젝트**를 클릭합니다.  
  
2.  왼쪽 창에서, **Visual C\+\+** 프로젝트 형식을 클릭합니다.  
  
3.  오른쪽 창에서 **MFC Application**을 선택합니다.  
  
4.  프로젝트 이름을 `MyProj`로 지정하고, **OK**를 클릭합니다.  
  
5.  **Compound Document Support** 페이지를 선택합니다.  
  
6.  **Container**를 선택하거나 **Container\/Full\-server** 옵션을 선택합니다.  
  
7.  **Active document container** 확인란을 선택합니다.  
  
8.  **마침**을 클릭합니다.  
  
9. MFC 응용 프로그램 마법사가 응용 프로그램을 생성하는 것을 완료했을 때, 솔루션 탐색기를 사용하여 다음 파일을 엽니다.  
  
    -   MyProjview.cpp  
  
10. MyProjview.cpp에서 다음과 같이 변경합니다.  
  
    -   `CMyProjView::OnPreparePrinting`에서, 함수 내용을 다음 코드를 사용하여 바꿉니다.  
  
         [!code-cpp[NVC_MFCDocView#56](../mfc/codesnippet/CPP/creating-an-active-document-container-application_1.cpp)]  
  
     `OnPreparePrinting`는 인쇄 지원을 제공합니다.  이 코드는 기본 인쇄 준비인 `DoPreparePrinting`를 대체합니다.  
  
     활성 문서 봉쇄는 향상된 인쇄 계획을 제공합니다.  
  
    -   액티브 문서를 그것의 `IPrint` 인터페이스를 통하여 처음으로 호출할 수 있습니다. 그리고 그것을 스스로 인쇄하도록 지시합니다.  이것은 이전의 OLE 봉쇄와는 다릅니다. 컨테이너는 프린터 `CDC`개체에서 봉쇄된 항복의 이미지를 렌더링해야 합니다.  
  
    -   실패하면, 봉쇄된 항목이 자신의 `IOleCommandTarget`인터페이스를 통해 스스로 인쇄하도록 전합니다.  
  
    -   실패하면, 항목을 직접 렌더링합니다.  
  
     정적 멤버 함수 `COleDocObjectItem::OnPrint` 및 `COleDocObjectItem::OnPreparePrinting`는 이전 코드에 구현된 대로 향상된 인쇄 계획을 제공합니다.  
  
11. 사용자 고유의 구현을 추가하고 응용 프로그램을 빌드합니다.  
  
## 참고 항목  
 [액티브 문서 포함](../mfc/active-document-containment.md)