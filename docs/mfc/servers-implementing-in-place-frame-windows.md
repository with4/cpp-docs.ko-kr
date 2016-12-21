---
title: "서버: 내부 프레임 창 구현 | Microsoft Docs"
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
  - "프레임 창, 구현"
  - "프레임 창, 내부"
  - "내부 프레임 창"
  - "OLE 서버 응용 프로그램, 프레임 창"
  - "서버, 내부 프레임 창"
ms.assetid: 09bde4d8-15e2-4fba-8d14-9b954d926b92
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 서버: 내부 프레임 창 구현
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 서버 응용 프로그램을 만드는 응용 프로그램 마법사를 사용 하지 않는 경우, 비주얼 편집 서버 응용 프로그램에서 내부 프레임 창을 구현 하려면 무엇을 해야 하는지 설명합니다.  이 문서에 설명 된 절차를 따르는 대신 응용 프로그램 마법사가 생성 한 응용 프로그램이나 Visual C\+\+과 함께 제공 된 샘플에서 기존 내부 프레임 창 클래스를 사용할 수 있습니다.  
  
#### 내부 프레임 창 클래스를 선언 하려면  
  
1.  `COleIPFrameWnd` 에서 내부 프레임 창 클래스를 파생합니다.  
  
    -   클래스 헤더 파일에서 `DECLARE_DYNCREATE` 매크로를 사용하십시오.  
  
    -   클래스 구현 파일\(.cpp\) 에서 `IMPLEMENT_DYNCREATE` 매크로를 사용하십시오.  이렇게 하면 이 클래스의 개체가 프레임에 의해 만들어 질 수 있도록 허용합니다.  
  
2.  내부 프레임 창 클래스에 `COleResizeBar` 멤버를 선언하십시오.  이 서버 응용 프로그램의 내부 크기를 지원 하려면 이것이 필요합니다.  
  
     `OnCreate` 메세지 처리기를\(**Properties** 창을 사용하여\) 선언하고 선언이 된 경우,  `COleResizeBar` 멤버에 대해 **Create** 를 호출하십시오.  
  
3.  도구 모음을 가지고 있는 경우, 내부 프레임 창 클래스에 `CToolBar` 멤버를 선언합니다.  
  
     서버에서 활성화 되어 있을 때, 도구 모음을 생성하기 위해 `OnCreateControlBars` 멤버 함수를 재정의 하십시오.  예를 들면 다음과 같습니다.  
  
     [!code-cpp[NVC_MFCOleServer#1](../mfc/codesnippet/CPP/servers-implementing-in-place-frame-windows_1.cpp)]  
  
     아래 5 단계의 이 코드의 설명을 참조하십시오.  
  
4.  메인 .cpp 파일에서 해당 내부 프레임 창 클래스에 대한 헤더 파일을 포함하십시오.  
  
5.  응용 프로그램의 클래스에 대한 `InitInstance` 에서 문서 템플릿 개체의 `SetServerInfo` 함수를 호출하여 리소스와 내부 프레임 창을 열기 및 내부 편집에서 사용되도록 지정하십시오.  
  
 **if** 문에서 함수의 호출 모음은 서버가 제공하는 리소스로 부터 도구 모음을 만듭니다.  도구 모음은 컨테이너의 창 계층의 일부입니다.  도구 모음이 `CToolBar` 로부터 파생되었기 때문에, 소유자를 변경하지 않는 한 메세지 소유자, 컨테이너 응용 프로그램의 프레임 창에 전달합니다.  `SetOwner` 에 대한 호출이 왜 필요한지를 나타냅니다.  이 호출 명령이 전송 되는 메시지를 서버에 전달할 서버의 내부 프레임 창으로 창을 변경 합니다.  이 것이 제공하는 도구 모음에서 작업에 반응하는 서버를 허용합니다.  
  
 도구 모음 비트맵의 ID는 서버 응용 프로그램에 정의 된 다른 위치에서 리소스와 동일 해야 합니다.  자세한 내용은 [Menus and Resources: Server Additions](../mfc/menus-and-resources-server-additions.md) 를 참조하십시오.  
  
 자세한 내용은 *Class Library Reference* 의 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md), [COleResizeBar](../mfc/reference/coleresizebar-class.md), 및 [CDocTemplate::SetServerInfo](../Topic/CDocTemplate::SetServerInfo.md) 를 참조하십시오.  
  
## 참고 항목  
 [서버](../mfc/servers.md)   
 [서버: 서버 구현](../mfc/servers-implementing-a-server.md)   
 [서버: 서버 문서 구현](../mfc/servers-implementing-server-documents.md)   
 [서버: 서버 항목](../mfc/servers-server-items.md)