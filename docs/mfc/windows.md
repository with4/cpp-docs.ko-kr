---
title: Windows | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], window
- windows [MFC]
- MFC, windows
- window objects [MFC], MFC Framework
ms.assetid: dd92bf34-842e-40fe-8aea-3028b55314d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 88ba41b7bb921cc2834b4d45712be768b2d19f8e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384467"
---
# <a name="windows"></a>Windows
다음이의 문서에서는 MFC 프레임 워크의 창 개체를 설명합니다. 모든 MFC 창 클래스에서 파생 [CWnd](../mfc/reference/cwnd-class.md), 프레임 창, 보기, 대화 상자 및 컨트롤을 포함 합니다.  
  
 문서의 첫 번째 그룹 설명 [창 개체 소멸 시키기](../mfc/window-objects.md) 일반적입니다. 이 그룹에 대 한 c + + 창 개체 소멸 시키기, HWND 캡슐화 방법 및 자식 창과 같은 사용자 지정 창을 만들 때의 사용 방법에 대 한 일반 정보를 참조 하십시오.  
  
 문서의 두 번째 그룹 설명 [프레임 창](../mfc/frame-windows.md)-콘텐츠 주위에 프레임을 배치 하는 windows-특히 합니다. 이 그룹에는 MFC 프레임 워크 프레임 창 및 컨트롤 막대, 보기 등 프레임 내용을 관리 하는 방법에 대 한 정보를 참조 하십시오.  
  
## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아보려는 항목  
 *일반적인 창 개체에 대 한 항목*  
  
-   [창 개체 소멸 시키기](../mfc/window-objects.md)  
  
-   [관계는 c + + 창 개체와 HWND 처리](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md)  
  
-   [파생 된 창 클래스](../mfc/derived-window-classes.md)  
  
-   [창 개체 만들기](../mfc/creating-windows.md)  
  
-   [창 개체 제거](../mfc/destroying-window-objects.md)  
  
-   [창 "클래스" 등록](../mfc/registering-window-classes.md)  
  
-   [창 개체 작업](../mfc/working-with-window-objects.md)  
  
-   [장치 컨텍스트](../mfc/device-contexts.md): Windows 그리기 장치 독립적 하는 개체  
  
-   [그래픽 개체](../mfc/graphic-objects.md): 펜, 브러시, 글꼴, 비트맵, 색상표, 영역  
  
 *프레임 창 항목*  
  
-   [프레임 창](../mfc/frame-windows.md): 프레임을 제공 하는 창 개체  
  
-   [프레임 창 및 뷰](../mfc/frame-windows.md)  
  
-   [프레임 창 클래스](../mfc/frame-window-classes.md)  
  
-   [프레임 창 스타일](../mfc/frame-window-styles-cpp.md)  
  
-   [MFC에서 만든 창 스타일 변경](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
-   [프레임 창 수행할 작업](../mfc/what-frame-windows-do.md)  
  
-   [프레임 창 사용](../mfc/using-frame-windows.md)  
  
-   [MD/자식 창 (MDICLIENT 창) 관리](../mfc/managing-mdi-child-windows.md)  
  
-   [메뉴, 컨트롤 막대 및 액셀러레이터 관리](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
-   [CFrameWnd](../mfc/reference/cframewnd-class.md)  
  
-   [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
  
-   [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
  
-   [뷰 사용](../mfc/using-views.md)  
  
-   [여러 문서 형식, 뷰 및 프레임 창 (분할자 창)](../mfc/multiple-document-types-views-and-frame-windows.md)  
  
-   [메시지 (맵 및 처리기 함수)](../mfc/messages.md)  
  
 *만들고 Windows를 제거 합니다.*  
  
-   [일반 창 만들기 시퀀스](../mfc/general-window-creation-sequence.md)  
  
-   [창 개체 소멸](../mfc/destroying-window-objects.md)  
  
-   [문서 프레임 창 만들기](../mfc/creating-document-frame-windows.md)  
  
-   [프레임 창 소멸](../mfc/destroying-frame-windows.md)  
  
 *분할 창 만들기*  
  
-   [분할 창 만들기](../mfc/multiple-document-types-views-and-frame-windows.md)  
  
 *자식 창 및 현재 뷰 관리*  
  
-   [MDI 자식 창 관리](../mfc/managing-mdi-child-windows.md)  
  
-   [현재 뷰 관리](../mfc/managing-the-current-view.md)  
  
-   [메뉴, 컨트롤 막대 및 액셀러레이터 관리](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
 *창 스타일 및 장치 컨텍스트 사용*  
  
-   [펜과 다른 그래픽 개체를 사용 하 여 장치 컨텍스트에서](../mfc/graphic-objects.md)  
  
-   [MFC에서 만든 창 스타일 변경](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
## <a name="see-also"></a>참고 항목  
 [사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)   
 [대화 상자](../mfc/dialog-boxes.md)   
 [도구 모음](../mfc/toolbars.md)   
 [상태 표시줄](../mfc/status-bars.md)   
 [대화 상자 모음](../mfc/dialog-bars.md)

