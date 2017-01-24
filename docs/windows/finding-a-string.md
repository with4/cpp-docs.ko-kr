---
title: "Finding a String | Microsoft Docs"
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
  - "strings [C++], searching"
  - "strings [C++]"
ms.assetid: c2497173-f356-4f77-97d6-f0ac41782510
caps.latest.revision: 12
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Finding a String
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

문자열 테이블에서 하나 이상의 문자열을 검색하고, **편집** 메뉴의 **파일에서 찾기** 명령에 [정규식](../Topic/Using%20Regular%20Expressions%20in%20Visual%20Studio.md)을 사용하여 패턴과 일치하는 모든 문자열 인스턴스를 찾을 수 있습니다.  
  
### 문자열 테이블에서 문자열을 찾으려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md)에서 문자열 테이블 아이콘을 두 번 클릭하여 문자열 테이블을 엽니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 없으면 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하십시오.  
  
2.  **편집** 메뉴에서 **찾기 및 바꾸기**를 클릭한 다음 **찾기**를 선택합니다.  
  
3.  **찾을 내용** 상자의 드롭다운 목록에서 이전 검색 문자열을 선택하거나 찾을 문자열의 리소스 식별자 또는 캡션 텍스트를 입력합니다.  
  
4.  **찾기** 옵션을 선택합니다.  
  
5.  **다음 찾기**를 클릭합니다.  
  
    > [!TIP]
    >  정규식을 사용하여 파일을 검색하려면 **파일에서 찾기** 명령을 사용합니다.  패턴과 일치하는 정규식을 입력하거나 **찾을 내용** 상자 오른쪽에 있는 단추를 클릭하여 정규 검색식 목록을 표시합니다.  이 목록에서 식을 선택하면 선택한 식이 **찾을 내용** 상자에 검색 텍스트로 입력됩니다.  정규식을 사용할 경우에는 **정규식 사용** 확인란을 선택해야 합니다.  
  
 관리되는 프로젝트\(공용 언어 런타임을 대상으로 하는 프로젝트\)에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
 **요구 사항**  
  
 Win32  
  
## 참고 항목  
 [String Editor](../mfc/string-editor.md)   
 [Strings](_win32_Strings)   
 [About Strings](_win32_About_Strings_cpp)