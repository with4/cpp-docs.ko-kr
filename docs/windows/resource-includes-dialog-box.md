---
title: "리소스 내용 대화 상자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.resourceincludes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "리소스 내용 대화 상자"
  - "rc 파일, 저장소 변경"
  - "기호 헤더 파일, 변경"
  - "소스 코드 컴파일, 리소스 포함"
  - ".rc 파일, 저장소 변경"
  - "기호 헤더 파일, 읽기 전용"
  - "기호, 기호 헤더 파일"
ms.assetid: 659a54e6-e416-4045-8411-798730ff4ce3
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 리소스 내용 대화 상자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**리소스 내용** 대화 상자를 사용하여, 환경에서 프로젝트 .rc 파일에 모든 리소스를 저장하고 Resource.h에 [기호](../mfc/symbols-resource-identifiers.md)를 저장하는 것을 정상 작업이 되도록 수정할 수 있습니다.  
  
 **리소스 내용** 대화 상자를 열려면 [리소스 뷰](../windows/resource-view-window.md)에서 .rc 파일을 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **리소스 내용**을 선택합니다.  
  
 **기호 헤더 파일**  
 리소스 파일에 대한 기호 정의가 저장되는 헤더 파일의 이름을 변경할 수 있습니다.  자세한 내용은 [기호 헤더 파일의 이름 변경](../windows/changing-the-names-of-symbol-header-files.md)을 참조하세요.  
  
 **읽기 전용 기호 지시문**  
 편집 세션 동안 수정해서는 안 되는 기호가 들어 있는 헤더 파일을 포함할 수 있습니다.  예를 들어 여러 프로젝트 간에 공유되는 기호 파일을 포함할 수 있습니다.  MFC .h 파일을 포함할 수도 있습니다.  자세한 내용은 [공유\(읽기 전용\) 또는 계산된 기호 포함](../windows/including-shared-read-only-or-calculated-symbols.md)을 참조하세요.  
  
 **컴파일 타임 지시문**  
 기본 리소스 파일에 있는 리소스와 별도로 생성 및 편집되는 리소스 파일을 포함하거나, 컴파일 타임 지시문\(예: 특정 조건에 따라 리소스를 포함하는 지시문\)을 포함하거나, 사용자 지정 형식에 리소스를 포함할 수 있습니다.  컴파일 타임 지시문 상자를 사용하여 표준 MFC 리소스 파일을 포함할 수도 있습니다.  자세한 내용은 [컴파일 타임에 리소스 포함](../windows/how-to-include-resources-at-compile-time.md)을 참조하세요.  
  
> [!NOTE]
>  이 텍스트 상자의 항목은 .rc 파일에서 각각  `TEXTINCLUDE 1`, `TEXTINCLUDE 2` 및 `TEXTINCLUDE 3`으로 표시됩니다.  자세한 내용은 [TN035: Visual C\+\+에서 여러 개의 리소스 파일 및 헤더 파일 사용](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)을 참조하세요.  
  
 **리소스 내용** 대화 상자를 사용하여 리소스 파일을 변경한 후에는 하고 나면  .rc 파일을 닫았다가 다시 열어야 변경 내용이 적용됩니다.  자세한 내용은 [컴파일 타임에 리소스 포함](../windows/how-to-include-resources-at-compile-time.md)을 참조하세요.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
## 요구 사항  
 Win32  
  
## 참고 항목  
 [How to: Specify Include Directories for Resources](../windows/how-to-specify-include-directories-for-resources.md)   
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)