---
title: "How to: Open a Resource Script File in Text Format | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.resource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resource script files, opening in text format"
  - ".rc files, opening in text format"
  - "rc files, opening in text format"
ms.assetid: 0bc57527-f53b-40c9-99a9-4dcbc5c9af57
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# How to: Open a Resource Script File in Text Format
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

특정 리소스 편집기 내에서 대화 상자와 같은 리소스를 열지 않고 프로젝트의 리소스 스크립트\(.rc\) 파일의 내용을 보려는 경우가 있을 수 있습니다.  예를 들어 리소스 파일에서 각 대화 상자를 별도로 열지 않고 모든 대화 상자에서 문자열을 검색하려고 할 수 있습니다.  
  
> [!NOTE]
>  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
 리소스 파일을 텍스트 형식으로 간단하게 열어 포함된 모든 리소스를 확인하고 [텍스트 편집기](http://msdn.microsoft.com/ko-kr/508e1f18-99d5-48ad-b5ad-d011b21c6ab1)에서 지원하는 전역 작업을 수행할 수 있습니다.  
  
> [!NOTE]
>  리소스 편집기에서 .rc 또는 resource.h 파일을 직접 읽지 않습니다.  리소스 컴파일러는 리소스 편집기에서 사용되는 이러한 파일을 .aps 파일로 컴파일합니다.  이 파일은 컴파일 단계이며 기호화된 데이터만 저장합니다.  일반적인 컴파일 프로세스에서처럼 기호화되지 않은 정보\(예: 주석\)는 컴파일 프로세스 중에 삭제됩니다.  .aps 파일이 .rc 파일과 동기화되지 않을 때마다 .rc 파일이 다시 생성됩니다. 예를 들어 저장하면 리소스 편집기에서 .rc 파일 및 resource.h 파일을 덮어씁니다.  리소스 자체의 모든 변경 내용은 .rc 파일에 통합된 상태로 유지되지만 주석은 .rc 파일을 덮어쓰면 항상 손실됩니다.  주석을 유지하는 방법에 대한 자세한 내용은 [컴파일 타임에 리소스 포함](../windows/how-to-include-resources-at-compile-time.md)을 참조하세요.  
  
### 리소스 스크립트 파일을 텍스트로 열려면  
  
1.  **파일** 메뉴에서 **열기**를 선택하고 **파일**을 클릭합니다.  
  
2.  **파일 열기** 대화 상자에서 텍스트 형식으로 는 리소스 스크립트 파일로 이동합니다.  
  
3.  파일을 강조 표시한 다음 **열기** 단추의 드롭다운 화살표\(단추의 오른쪽에 있음\)를 클릭합니다.  
  
4.  드롭다운 메뉴에서 **연결 프로그램**을 선택합니다.  
  
5.  **연결 프로그램** 대화 상자에서 **소스 코드\(텍스트\) 편집기**를 클릭합니다.  
  
6.  **다음 형식으로 열기** 드롭다운 목록에서 **텍스트**를 선택합니다.  
  
     리소스가 소스 코드 편집기에서 열립니다.  
  
 또는  
  
1.  **솔루션 탐색기**에서 .rc 파일을 마우스 오른쪽 단추로 클릭합니다.  
  
2.  바로 가기 메뉴에서 **연결 프로그램...**을 선택한 다음 **소스 코드\(텍스트\) 편집기**를 선택합니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
 요구 사항  
  
 Win32  
  
## 참고 항목  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)