---
title: "Adding or Deleting a String | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.string"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strings [C++], adding to string tables"
  - "string tables, deleting strings"
  - "strings [C++], deleting in string tables"
  - "string tables, adding strings"
ms.assetid: 077077b4-0f4b-4633-92d6-60b321164cab
caps.latest.revision: 11
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Adding or Deleting a String
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

문자열 편집기를 사용하면 새 엔트리를 신속하게 문자열 테이블에 삽입할 수 있습니다.  새 문자열은 테이블 끝에 삽입되고 사용 가능한 다음 식별자가 이 문자열에 지정됩니다.  그런 다음 원하는 대로 [속성 창](../Topic/Properties%20Window.md)에서 ID, Value 또는 Caption 속성을 편집할 수 있습니다.  
  
 문자열 편집기에서는 이미 사용하고 있는 ID를 사용할 수 없습니다.  사용하고 있는 ID를 선택하면 문자열 편집기에서 메시지를 표시하고 IDS\_STRING58113과 같은 일반 고유 ID를 지정합니다.  
  
### 문자열 테이블 엔트리를 추가하려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md)에서 문자열 테이블 아이콘을 두 번 클릭하여 문자열 테이블을 엽니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 없으면 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하십시오.  
  
2.  마우스 오른쪽 단추로 문자열 테이블을 클릭하고 바로 가기 메뉴에서 **새 문자열**을 선택합니다.  
  
3.  **문자열** 편집기의 ID 드롭다운 목록에서 **ID**를 선택하거나 ID를 직접 입력합니다.  
  
4.  필요한 경우 **값**을 편집합니다.  
  
5.  **캡션**에 엔트리를 입력합니다.  
  
    > [!NOTE]
    >  Windows 문자열 테이블에는 Null 문자열을 사용할 수 없습니다.  문자열 테이블에 Null 문자열 엔트리를 만들면 "이 테이블 엔트리에 대해 문자열을 입력하십시오."라는 메시지가 표시됩니다.  
  
### 문자열 테이블 엔트리를 삭제하려면  
  
1.  삭제할 항목을 선택합니다.  
  
2.  **편집** 메뉴에서 **삭제**를 클릭합니다.  
  
 \-또는\-  
  
-   마우스 오른쪽 단추로 문자열을 클릭하고 바로 가기 메뉴에서 **삭제**를 선택합니다.  
  
 \-또는\-  
  
-   **Delete** 키를 누릅니다.  
  
 관리되는 프로젝트\(공용 언어 런타임을 대상으로 하는 프로젝트\)에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
 **요구 사항**  
  
 Win32  
  
## 참고 항목  
 [String Editor](../mfc/string-editor.md)   
 [Strings](_win32_Strings)   
 [About Strings](_win32_About_Strings_cpp)