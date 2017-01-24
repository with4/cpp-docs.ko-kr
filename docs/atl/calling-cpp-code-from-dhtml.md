---
title: "Calling C++ Code from DHTML | Microsoft Docs"
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
  - "DHTML, calling C++ code from"
ms.assetid: 37329acd-4c22-40ca-a85a-b7480748f75f
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Calling C++ Code from DHTML
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DHTML 컨트롤 테스트 컨테이너 또는 Internet Explorer 같은 컨테이너에서 호스팅될 수 있습니다.  참조  [속성 및 이벤트 테스트 컨테이너 테스트](../mfc/testing-properties-and-events-with-test-container.md) 테스트 컨테이너에 액세스 하는 방법에 대 한 정보.  
  
 컨트롤을 호스팅하는 컨테이너 컨트롤에 기본 컨트롤 인터페이스를 사용 하 여 통신 합니다.  C \+ \+ 코드 및 HTML 리소스와 통신 하 "UI"로 끝나는 디스패치 인터페이스에서는 DHTML을 사용 합니다.  [ATL DHTML 컨트롤 수정](../atl/modifying-the-atl-dhtml-control.md), 이러한 다른 인터페이스에서 호출할 수 있는 메서드 추가 연습할 수 있습니다.  
  
 DHTML에서 C\+\+ 코드를 호출 하는 예제를 보려면  [DHTML 컨트롤 만들기](../atl/creating-an-atl-dhtml-control.md) ATL 컨트롤 마법사를 사용 하 여 HTML 파일 및 헤더 파일에서 코드를 검사 합니다.  
  
## 헤더 파일에서 WebBrowser 메서드를 선언합니다.  
 DHTML UI에서 C\+\+ 메서드를 호출 하려면 해당 컨트롤의 UI 인터페이스에 메서드를 추가 해야 합니다.  예를 들어, ATL 컨트롤 마법사가 만든 헤더 파일을 C\+\+ 메서드 포함 `OnClick`를 마법사에서 생성 된 컨트롤의 UI 인터페이스의 멤버입니다.  
  
 검사 `OnClick` 컨트롤의.h 파일:  
  
 [!code-cpp[NVC_ATL_COM#4](../atl/codesnippet/CPP/calling-cpp-code-from-dhtml_1.h)]  
  
 첫 번째 매개 변수를 `pdispBody`, 본문 개체의 디스패치 인터페이스에 대 한 포인터입니다.  두 번째 매개 변수를 `varColor`, 컨트롤에 적용 하는 색상을 식별 합니다.  
  
## HTML 파일에서 C\+\+ 코드 호출  
 헤더 파일에서 WebBrowser 메서드를 선언 하면 HTML 파일에서 메서드를 호출할 수 있습니다.  HTML 파일에 ATL 컨트롤 마법사 세 가지 Windows 디스패치 메서드를 삽입 통지: 3 `OnClick` 컨트롤의 배경색을 변경 하는 메시지를 발송 하는 방법.  
  
 HTML 파일에서 메서드 중 하나를 검토 합니다.  
  
 `<BUTTON onclick='window.external.OnClick(theBody, "red");'>Red</BUTTON>`  
  
 창 외부 메서드 위에 HTML 코드에서 `OnClick`, 단추 태그의 일부로 호출 됩니다.  메서드는 두 개의 매개 변수가 있습니다: `theBody`, HTML 문서의 본문 참조 및 `"red"`를 나타내는 단추를 눌렀을 때 컨트롤의 배경 색을 빨강으로 변경 됩니다.  `Red` 태그 다음 버튼의 레이블이 됩니다.  
  
 참조  [ATL DHTML 컨트롤 수정](../atl/modifying-the-atl-dhtml-control.md) 직접 메서드를 제공 하는 방법에 대 한 자세한 내용은.  참조  [DHTML 컨트롤 프로젝트의 요소를 나타내는](../atl/identifying-the-elements-of-the-dhtml-control-project.md) HTML 파일에 대 한 자세한 내용은.  
  
## 참고 항목  
 [DHTML 컨트롤에 대한 지원](../atl/atl-support-for-dhtml-controls.md)