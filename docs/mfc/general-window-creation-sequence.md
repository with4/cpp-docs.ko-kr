---
title: 일반 창 만들기 시퀀스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- sequence [MFC], window creation
- frame windows [MFC], creating
- windows [MFC], creating
- sequence [MFC]
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3a4b67ccbba97405678985e6412cc56911bd184
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929694"
---
# <a name="general-window-creation-sequence"></a>일반 창 만들기 시퀀스
프레임 워크 훨씬 동일한 프로세스를 사용 하 여에서 설명 하는 자식 같은 고유한 창의 창을 만들 때 [문서/뷰 만들기](../mfc/document-view-creation.md)합니다.  
  
 사용 하는 MFC에서 제공 하는 모든 창 클래스 [2 단계 생성](../mfc/one-stage-and-two-stage-construction-of-objects.md)합니다. 즉, c + + 호출 하는 동안 **새** 연산자를 생성자 할당 하 고 c + + 개체를 초기화 하지만 해당 Windows 창을 만들지 않습니다. 호출 하 여 나중에 수행 되는 [만들기](../mfc/reference/cwnd-class.md#create) window 개체의 멤버 함수입니다.  
  
 `Create` 멤버 함수는 Windows 창을 저장 하 고 해당 `HWND` c + + 개체의 공용 데이터 멤버에 [m_hWnd](../mfc/reference/cwnd-class.md#m_hwnd)합니다. `Create` 제공 생성 매개 변수를 통해 유연성을 완료합니다. 호출 하기 전에 `Create`, 전역 함수는 창 클래스를 등록 하는 것이 좋습니다 [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) 프레임에 대 한 아이콘 및 클래스 스타일을 설정 하는 데 있습니다.  
  
 프레임 창에 사용할 수 있습니다는 [LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) 멤버 함수 대신 `Create`합니다. `LoadFrame` 더 적은 수의 매개 변수를 사용 하 여 Windows 창을으로 열립니다. 프레임의 캡션, 아이콘, 액셀러레이터 키 테이블 및 메뉴를 포함 하 여 리소스에서 많은 기본값을 가져옵니다.  
  
> [!NOTE]
>  아이콘, 액셀러레이터 키 테이블 및 메뉴 리소스 있어야 공용 리소스 ID와 같은 **IDR_MAINFRAME**, 하 여 LoadFrame에 로드할 수 있습니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아보려는 항목  
  
-   [창 개체 소멸 시키기](../mfc/window-objects.md)  
  
-   [창 "클래스" 등록](../mfc/registering-window-classes.md)  
  
-   [창 개체 소멸 시키기](../mfc/destroying-window-objects.md)  
  
-   [문서 프레임 창 만들기](../mfc/creating-document-frame-windows.md)  
  
## <a name="see-also"></a>참고 항목  
 [창 만들기](../mfc/creating-windows.md)

