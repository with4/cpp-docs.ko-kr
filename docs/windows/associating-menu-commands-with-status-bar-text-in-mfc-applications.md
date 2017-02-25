---
title: "Associating Menu Commands with Status Bar Text in MFC Applications | Microsoft Docs"
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
  - "status bars, associating menu items"
  - "menus, status bar text"
ms.assetid: 757c0e02-bc97-493f-bccd-6cc6887ebc64
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Associating Menu Commands with Status Bar Text in MFC Applications
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

응용 프로그램은 사용자가 선택할 수 있는 각 메뉴 명령에 대한 설명 텍스트를 표시할 수 있습니다. 속성 창에서 **프롬프트** 속성을 사용하여 각 메뉴 명령에 텍스트 문자열을 할당하면 됩니다. 명령과 동일한 ID를 가진 문자열이 [문자열 테이블](../mfc/string-editor.md)에 있는 경우 MFC 응용 프로그램은 사용자가 메뉴 항목 위로 마우스를 가져갈 때 실행 중인 응용 프로그램의 상태 표시줄에 이 문자열 리소스를 자동으로 표시합니다.  
  
### 메뉴 명령을 상태 표시줄 텍스트 문자열에 연결하려면  
  
1.  **메뉴** 편집기에서 메뉴 명령을 선택합니다.  
  
2.  [속성 창](../Topic/Properties%20Window.md)의 **프롬프트** 상자에 연결된 상태 표시줄 텍스트를 입력합니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 *.NET Framework 개발자 가이드*에서 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md) 항목을 참조하세요.  
  
 **요구 사항**  
  
 MFC  
  
## 참고 항목  
 [문자열](../atl-mfc-shared/strings-atl-mfc.md)   
 [Adding Commands to a Menu](../windows/adding-commands-to-a-menu.md)   
 [Menu Editor](../mfc/menu-editor.md)