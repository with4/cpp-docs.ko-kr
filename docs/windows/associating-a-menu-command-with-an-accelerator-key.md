---
title: "Associating a Menu Command with an Accelerator Key | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "keyboard shortcuts, menu association"
  - "commands, associating menu commands with accelerator keys"
  - "menu commands, associating with keyboard shortcuts"
ms.assetid: ad2de43f-b20a-4c9f-bda8-0420179da48c
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Associating a Menu Command with an Accelerator Key
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

메뉴 명령과 키보드 조합에서 동일한 프로그램 명령을 종종 실행하도록 하려고 합니다. 이렇게 하려면 메뉴 편집기를 사용하여 메뉴 명령과 응용 프로그램의 액셀러레이터 테이블에 있는 항목에 동일한 리소스 식별자를 할당합니다. 그러고 나서 메뉴 명령의 [캡션](../windows/menu-command-properties.md)을 편집하여 액셀러레이터 키의 이름을 표시합니다.  
  
### 메뉴 명령을 액셀러레이터 키와 연결하려면  
  
1.  **메뉴** 편집기에서 원하는 메뉴 명령을 선택합니다.  
  
2.  [속성 창](../Topic/Properties%20Window.md)에서 액셀러레이터 키 이름을 **캡션** 속성에 추가합니다.  
  
    -   모든 메뉴의 액셀러레이터 키가 왼쪽으로 맞춰 표시되도록 메뉴 캡션 뒤에 탭의 이스케이프 시퀀스\(\\t\)를 입력합니다.  
  
    -   보조 키의 이름\(**CTRL**, **ALT** 또는 **SHIFT**\) 다음에 더하기 기호\(**\+**\)를 입력하고 추가 키의 이름, 문자 또는 기호를 입력합니다.  
  
         예를 들어 **CTRL\+O**를 **파일** 메뉴의 **열기** 명령에 할당하려면 메뉴 명령의 **캡션**을 다음과 같이 표시되도록 수정합니다.  
  
        ```  
        &Open...\tCtrl+O   
        ```  
  
         메뉴 편집기의 메뉴 명령이 업데이트되고 입력한 대로 새 캡션이 반영됩니다.  
  
3.  **액셀러레이터** 편집기에서 [액셀러레이터 테이블 항목을 만들고](../windows/adding-an-entry-to-an-accelerator-table.md) 메뉴 명령과 같은 식별자를 할당합니다. 기억하기 쉬운 키 조합을 사용합니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 *.NET Framework 개발자 가이드*에서 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
 **요구 사항**  
  
 Win32  
  
## 참고 항목  
 [Adding Commands to a Menu](../windows/adding-commands-to-a-menu.md)   
 [Menu Editor](../mfc/menu-editor.md)