---
title: "Adding Formatting or Special Characters to a String | Microsoft Docs"
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
  - "special characters, adding to strings"
  - "ASCII characters, adding to strings"
  - "strings [C++], formatting"
  - "strings [C++], special characters"
ms.assetid: c40f394a-8b2c-4896-ab30-6922863ddbb5
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Adding Formatting or Special Characters to a String
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### 문자열에 형식 지정이나 특수 문자를 추가하려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md)에서 문자열 테이블 아이콘을 두 번 클릭하여 문자열 테이블을 엽니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 없으면 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하십시오.  
  
2.  수정할 문자열을 선택합니다.  
  
3.  [속성 창](../Topic/Properties%20Window.md)에서 아래 표에 있는 표준 이스케이프 시퀀스를 **Caption** 상자의 텍스트에 추가하고 **Enter** 키를 누릅니다.  
  
    |수행할 작업|입력할 이스케이프 시퀀스|  
    |------------|-------------------|  
    |줄 바꿈|\\n|  
    |캐리지 리턴|\\r|  
    |Tab|\\t|  
    |백슬래시\(\\\)|\\\\|  
    |ASCII 문자|\\ddd\(8진수 표기법\)|  
    |경고\(경고음\)|\\a|  
  
> [!NOTE]
>  문자열 편집기에서 이스케이프된 ASCII 문자를 모두 지원하지는 않습니다.  위에서 설명한 문자만 사용할 수 있습니다.  
  
 관리되는 프로젝트\(공용 언어 런타임을 대상으로 하는 프로젝트\)에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
 **요구 사항**  
  
 Win32  
  
## 참고 항목  
 [String Editor](../mfc/string-editor.md)   
 [Strings](_win32_Strings)   
 [About Strings](_win32_About_Strings_cpp)