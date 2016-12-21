---
title: "Win32 Predefined Symbols | Microsoft Docs"
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
  - "Win32 [C++], predefined symbols"
  - "symbols, Win32 predefined"
  - "Windows API [C++], predefined symbols"
ms.assetid: 45c8e193-ee2a-4024-bfc2-34d1ec9c9239
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Win32 Predefined Symbols
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 기호들은 Win32 헤더 파일에 정의되어 있으며 표준 Windows 응용 프로그램 함수 및 동작을 지원합니다.  이 기호들은 주로 일반 UI 요소에서 사용됩니다.  리소스 편집기에서 대화 상자와 컨트롤에 대해 작업할 경우, [속성 창](../Topic/Properties%20Window.md)에 이 기호들이 일반 컨트롤과 연결되어 나타납니다.  예를 들어, 도구 모음에 응용 프로그램 아이콘이 표시되는 경우 해당 아이콘은 속성 창에서 기호 IDI\_SMALL과 연결됩니다.  
  
|||  
|-|-|  
|IDABORT|컨트롤: 대화 상자 중단 단추|  
|IDC\_STATIC|컨트롤: 대화 상자의 정적 텍스트|  
|IDCANCEL|컨트롤: 대화 상자 취소 단추|  
|IDD\_ABOUTBOX|대화 상자: 제품 정보 대화 상자|  
|IDI\_PROJECTNAME|아이콘: 현재 프로젝트 아이콘|  
|IDI\_SMALL|아이콘: 현재 프로젝트의 작은 아이콘|  
|IDIGNORE|컨트롤: 대화 상자 무시 단추|  
|IDM\_ABOUT|메뉴 항목: 도움말 메뉴의 정보|  
|IDM\_EXIT|메뉴 항목: 파일 메뉴의 종료|  
|IDNO|컨트롤: 대화 상자 아니요 단추|  
|IDOK|컨트롤: 대화 상자 확인 단추|  
|IDRETRY|컨트롤: 대화 상자 재시도 단추|  
|IDS\_APP\_TITLE|문자열: 현재 응용 프로그램 이름|  
|IDYES|컨트롤: 대화 상자 예 단추|  
  
## 요구 사항  
 Win32  
  
## 참고 항목  
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)   
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)