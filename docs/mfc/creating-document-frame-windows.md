---
title: "문서 프레임 창 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- frame windows [MFC], creating
- document templates [MFC], and document frame windows
- windows [MFC], creating
- runtime, class information
- run-time class [MFC], and document frame window creation
- document frame windows [MFC], creating
- MFC, frame windows
ms.assetid: 8671e239-b76f-4dea-afa8-7024e6e58ff5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9098026c1a38f8e60093415ba1c5a2b3678b64d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-document-frame-windows"></a>문서 프레임 창 만들기
[문서/뷰 만들기](../mfc/document-view-creation.md) 표시 방법을 [CDocTemplate](../mfc/reference/cdoctemplate-class.md) 프레임 창, 문서 및 뷰를 만들고 모두 함께 연결 개체를 조정 합니다. 세 가지 [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) 에 대 한 인수는 `CDocTemplate` 생성자 프레임 창, 문서 및 문서 템플릿 파일에 새 명령 같은 사용자 명령에 대 한 응답에서 동적으로 작성 하는 뷰 클래스를 지정 합니다. 메뉴 또는 MDI 창 메뉴에서 새 창 명령을 합니다. 문서 서식 파일 보기 및 문서에 대 한 프레임 창을 만들 때 나중에 사용할이이 정보를 저장 합니다.  
  
 에 대 한는 [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) 파생에 속성이 제대로 작동 하는 메커니즘이 프레임 창 클래스를 사용 하 여 선언 해야 합니다는 [DECLARE_DYNCREATE](../mfc/reference/run-time-object-model-services.md#declare_dyncreate) 매크로입니다. 프레임 워크는 프레임 창 클래스의 생성 메커니즘을 사용 하 여 문서를 만드는 데 필요한 때문에 이것이 `CObject`합니다.  
  
 사용자가 문서를 만드는 명령을 선택, 문서 개체, 해당 뷰 및 보기를 표시 하는 프레임 창을 만드는 문서 서식 파일에 프레임 워크를 호출 합니다. 문서 서식 파일은 적절 한 클래스의 개체를 만듭니다 문서 프레임 창 만들면-클래스에서 파생 [CFrameWnd](../mfc/reference/cframewnd-class.md) SDI 응용 프로그램 또는 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) MDI에 대 한 응용 프로그램입니다. 프레임 워크는 프레임 창 개체의 다음 호출 [LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) 멤버 함수를 리소스에서 만든 정보를 가져오기 하 고 Windows 창을 만들 수 있습니다. 프레임 워크는 프레임 창 개체를 창 핸들을 연결합니다. 다음 문서 프레임 창의 자식 창으로 뷰를 만듭니다.  
  
 주의 결정 하는 데 사용 하 여 [초기화 시점](../mfc/when-to-initialize-cwnd-objects.md) 프로그램 `CWnd`-파생 된 개체입니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [CObject (동적 생성 메커니즘)에서 클래스 파생](../mfc/deriving-a-class-from-cobject.md)  
  
-   [문서/뷰 만들기 (템플릿 및 프레임 창 만들기)](../mfc/document-view-creation.md)  
  
-   [프레임 창 소멸 시키기](../mfc/destroying-frame-windows.md)  
  
## <a name="see-also"></a>참고 항목  
 [프레임 창 사용](../mfc/using-frame-windows.md)

