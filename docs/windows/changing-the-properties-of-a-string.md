---
title: "Changing the Properties of a String | Microsoft Docs"
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
  - "resource identifiers, string properties"
  - "string tables, changing strings"
  - "strings [C++], properties"
ms.assetid: 0a220434-f444-4405-9a64-d28d6b965687
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Changing the Properties of a String
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### 문자열이나 문자열 식별자를 변경하려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md)에서 문자열 테이블 아이콘을 두 번 클릭하여 문자열 테이블을 엽니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 없으면 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하십시오.  
  
2.  편집할 문자열을 선택하고 **ID**, **값** 또는 **캡션** 열을 두 번 클릭합니다.  이제 다음과 같은 작업을 수행할 수 있습니다.  
  
    -   **ID 드롭다운** 목록에서 **ID**를 선택하거나 직접 ID를 입력할 수 있습니다.  
  
    -   **값** 열에 다른 값을 입력할 수 있습니다.  
  
    -   **캡션** 열에 입력하여 편집할 수 있습니다.  
  
        > [!NOTE]
        >  [속성 창](../Topic/Properties%20Window.md)에서 문자열 속성을 편집할 수도 있습니다.  
  
 관리되는 프로젝트\(공용 언어 런타임을 대상으로 하는 프로젝트\)에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
 **요구 사항**  
  
 Win32  
  
## 참고 항목  
 [String Editor](../mfc/string-editor.md)   
 [Strings](_win32_Strings)   
 [About Strings](_win32_About_Strings_cpp)