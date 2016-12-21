---
title: "Moving a String from One Resource File to Another | Microsoft Docs"
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
  - "strings [C++], moving between files"
  - "resource script files, moving strings"
  - "string editing, moving strings between resources"
  - "String editor, moving strings between files"
ms.assetid: 94f8ee81-9b4c-4788-ba95-68c58db38029
caps.latest.revision: 12
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Moving a String from One Resource File to Another
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### 리소스 스크립트 파일 사이에 문자열을 이동하려면  
  
1.  두 개의 .rc 파일에서 문자열 테이블을 엽니다.  자세한 내용은 [프로젝트 외부에서 리소스 스크립트 파일 열기\(독립 실행형\)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)를 참조하십시오.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 없으면 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하십시오.  
  
2.  마우스 오른쪽 단추로 이동할 문자열을 클릭하고 바로 가기 메뉴에서 **잘라내기**를 선택합니다.  
  
3.  대상 **문자열 편집기** 창으로 커서를 이동합니다.  
  
4.  마우스 오른쪽 단추로 문자열을 이동할 대상 .rc 파일을 클릭하고 바로 가기 메뉴에서 **붙여넣기**를 선택합니다.  
  
    > [!NOTE]
    >  이동한 문자열의 **ID**나 **Value**가 대상 파일의 기존 **ID**나 **Value**와 충돌하면 이동한 문자열의 **ID**나 **Vlaue**가 변경됩니다.  **ID**가 동일한 문자열이 있으면 이동한 문자열의 **ID**가 변경됩니다.  **Vlaue**가 동일한 문자열이 있으면 이동한 문자열의 **Vlaue**가 변경됩니다.  
  
 관리되는 프로젝트\(공용 언어 런타임을 대상으로 하는 프로젝트\)에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
 **요구 사항**  
  
 Win32  
  
## 참고 항목  
 [String Editor](../mfc/string-editor.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [창 레이아웃 사용자 지정](../Topic/Customizing%20window%20layouts%20in%20Visual%20Studio.md)   
 [Strings](_win32_Strings)   
 [About Strings](_win32_About_Strings_cpp)