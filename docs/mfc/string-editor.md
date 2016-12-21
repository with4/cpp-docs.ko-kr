---
title: "String Editor | Microsoft Docs"
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
  - "vc.editors.string.F1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "String editor"
  - "string tables"
  - "string tables, String editor"
  - "string editing"
  - "string editing, string tables"
  - "resource editors, String editor"
  - "strings [C++], editing"
ms.assetid: f71ab8de-3068-4e29-8e28-5a33d18dd416
caps.latest.revision: 15
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# String Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

문자열 테이블은 응용 프로그램의 모든 문자열에 대한 ID, 값 및 캡션 목록이 포함된 Windows 리소스입니다. 예를 들어 상태 표시줄 프롬프트는 문자열 테이블에 있습니다.  
  
 응용 프로그램을 개발하는 동안 각 언어 또는 조건에 하나씩 여러 문자열 테이블을 만들 수 있습니다. 그러나 실행 가능 모듈에는 문자열 테이블이 하나만 포함됩니다. 테이블을 서로 다른 DLL에 삽입하면 실행 중인 응용 프로그램이 여러 문자열 테이블을 참조할 수 있습니다.  
  
 문자열 테이블을 사용하면 응용 프로그램을 여러 언어로 쉽게 지역화할 수 있습니다. 모든 문자열이 한 문자열 테이블에 있으면 소스 코드를 변경하지 않고 문자열과 기타 리소스를 번역하여 응용 프로그램을 지역화할 수 있습니다. 일반적으로 이 방법이 소스 파일에서 다양한 문자열을 수동으로 찾고 바꾸는 방법보다 더 바람직합니다.  
  
 문자열 편집기를 사용하여 다음을 수행할 수 있습니다.  
  
-   [문자열을 하나 이상 검색합니다](../mfc/finding-a-string.md).  
  
-   [새 항목을 문자열 테이블에 빠르게 삽입합니다](../mfc/adding-or-deleting-a-string.md).  
  
-   [리소스 파일 사이에 문자열을 이동합니다.](../mfc/moving-a-string-from-one-resource-file-to-another.md)  
  
-   [ID, 값 및 캡션 속성에 대한 바로 편집을 사용](../mfc/changing-the-properties-of-a-string.md)하고 변경 내용을 즉시 확인합니다.  
  
-   [여러 문자열의 Caption 속성을 변경합니다.](../mfc/changing-the-caption-property-of-multiple-strings.md)  
  
-   [문자열에 형식 지정 또는 특수 문자를 추가합니다.](../mfc/adding-formatting-or-special-characters-to-a-string.md)  
  
    > [!NOTE]
    >  Windows에서는 빈 문자열 테이블을 만들 수 없습니다. 항목 없이 문자열 테이블을 만들면 리소스 파일을 저장할 때 해당 테이블이 자동으로 삭제됩니다.  
  
 관리되는 프로젝트\(공용 언어 런타임을 대상으로 하는 프로젝트\)에 리소스를 추가하는 방법은 *.NET Framework 개발자 가이드*의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
## 요구 사항  
 Win32  
  
## 참고 항목  
 [Resource Editors](../mfc/resource-editors.md)   
 [문자열](http://msdn.microsoft.com/library/windows/desktop/ms646979.aspx)   
 [문자열 정보](http://msdn.microsoft.com/library/windows/desktop/ms647465.aspx)