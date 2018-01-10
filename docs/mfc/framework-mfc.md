---
title: "프레임 워크 (MFC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- encapsulation [MFC], Win32 API
- MFC, application framework
- wrapper classes [MFC], explained
- Win32 [MFC], API encapsulation by MFC
- application framework [MFC], about MFC application framework
- APIs [MFC], encapsulation by MFC Win32
- encapsulation [MFC]
- Windows API [MFC], encapsulation by MFC
- encapsulated Win32 API [MFC]
ms.assetid: 3be0fec8-9843-4119-ae42-ece993ef500b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c021b11809b3e6598e694fdaa46b7f829358e24f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="framework-mfc"></a>프레임워크(MFC)
Microsoft Foundation 클래스 (MFC) 라이브러리 프레임 워크를 사용 하 여 주로 몇 가지 주요 클래스와 여러 가지 Visual c + + 도구에 기반 합니다. 일부 클래스는 Win32 응용 프로그래밍 인터페이스 (API)의 많은 부분을 캡슐화합니다. 다른 클래스에는 문서, 뷰 및 응용 프로그램 자체와 같은 응용 프로그램 개념 캡슐화합니다. 여전히 다른 OLE 기능이 및 ODBC / DAO 데이터 액세스 기능을 캡슐화합니다.  
  
 창의 32의 개념은 MFC 클래스에 의해 캡슐화 하는 예를 들어 `CWnd`합니다. 즉, c + + 클래스 라고 `CWnd` "래핑" 또는 캡슐화는 `HWND` Windows 창을 나타내는 핸들입니다. 마찬가지로, 클래스 `CDialog` Win32 대화 상자를 캡슐화 합니다.  
  
 캡슐화 것을 의미 하는 c + + 클래스 `CWnd`, 예를 들어 형식의 멤버 변수를 포함 `HWND`, 클래스의 멤버 함수를 사용 하는 Win32 함수 호출을 캡슐화 하 고는 `HWND` 매개 변수로 합니다. 클래스 멤버 함수에는 일반적으로 캡슐화 하는 Win32 함수와 동일한 이름을 갖고 있습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [SDI 및 MDI](../mfc/sdi-and-mdi.md)  
  
 [문서, 뷰 및 프레임워크](../mfc/documents-views-and-the-framework.md)  
  
 [마법사 및 리소스 편집기](../mfc/wizards-and-the-resource-editors.md)  
  
## <a name="in-related-sections"></a>관련 단원  
 [프레임워크를 기반으로 구축](../mfc/building-on-the-framework.md)  
  
 [프레임워크가 코드를 호출하는 방법](../mfc/how-the-framework-calls-your-code.md)  
  
 [CWinApp: 응용 프로그램 클래스](../mfc/cwinapp-the-application-class.md)  
  
 [문서 템플릿 및 문서/뷰 만들기 프로세스](../mfc/document-templates-and-the-document-view-creation-process.md)  
  
 [메시지 처리 및 매핑](../mfc/message-handling-and-mapping.md)  
  
 [창 개체](../mfc/window-objects.md)  
  
## <a name="see-also"></a>참고 항목  
 [클래스를 사용하여 Windows 응용 프로그램 작성](../mfc/using-the-classes-to-write-applications-for-windows.md)
