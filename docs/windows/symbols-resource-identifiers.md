---
title: "Symbols: Resource Identifiers | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.symbol.identifiers"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "symbols, resource identifiers"
  - "symbols, creating"
  - "resource symbols"
  - "symbols, editing"
  - "resource editors, resource symbols"
ms.assetid: 8fccc09a-0237-4a65-b9c4-57d60c59e324
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Symbols: Resource Identifiers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

기호는 두 부분 즉, 텍스트 문자열\(기호 이름\)과 이와 매핑되는 정수 값\(기호 값\)으로 구성된 리소스 식별자\(ID\)입니다. 예:  
  
```  
IDC_EDITNAME = 5100  
```  
  
 기호 이름은 가장 흔히 식별자라고 합니다.  
  
 소스 코드와 리소스 편집기에서 기호를 사용하여 작업하는 동안 기호는 리소스 및 사용자 인터페이스 개체를 참조하는 방법에 대한 설명을 제공합니다.[리소스 기호 대화 상자](../windows/viewing-resource-symbols.md)를 사용하여 한곳에서 편안하게 기호를 보고 조작할 수 있습니다.  
  
 새 리소스 또는 리소스 개체를 만들 때 [리소스 편집기](../mfc/resource-editors.md)에서는 리소스에 기본 이름\(예: `IDC_RADIO1`\)을 지정하고 값을 할당합니다. 이름과 값으로 구성된 정의는 Resource.h 파일에 저장됩니다.  
  
> [!NOTE]
>  .rc 파일 간에 리소스 또는 리소스 개체를 복사할 경우 Visual C\+\+에서는 기존 파일에 있는 기호 이름 또는 값과의 충돌을 방지하려고 복사된 리소스의 기호 값 또는 기호 이름과 값을 변경할 수 있습니다.  
  
 응용 프로그램의 크기가 커지고 복잡해질수록 리소스와 기호 수도 증가합니다. 여러 파일에 흩어져 있는 많은 기호를 추적하는 작업은 어려울 수 있습니다. 다음을 수행할 수 있는 중앙 집중식 도구를 제공하는 [리소스 기호 대화 상자](../windows/resource-symbols-dialog-box.md)를 사용하면 기호를 간단하게 관리할 수 있습니다.  
  
-   [리소스 기호 보기](../windows/viewing-resource-symbols.md)  
  
-   [새 기호 만들기](../windows/creating-new-symbols.md)  
  
-   [할당되지 않은 기호 변경](../windows/changing-unassigned-symbols.md)  
  
-   [할당되지 않은 기호 삭제](../windows/deleting-unassigned-symbols.md)  
  
-   [지정된 기호에 대한 리소스 편집기 열기](../windows/opening-the-resource-editor-for-a-given-symbol.md)  
  
-   [기호 또는 기호 이름\(ID\) 변경](../windows/changing-a-symbol-or-symbol-name-id.md)  
  
-   [기호 숫자 값 변경](../windows/changing-a-symbol-s-numeric-value.md)  
  
-   [기호 헤더 파일의 이름 변경](../windows/changing-the-names-of-symbol-header-files.md)  
  
-   [공유\(읽기 전용\) 또는 계산된 기호 포함](../windows/including-shared-read-only-or-calculated-symbols.md)  
  
-   [미리 정의된 기호 ID 보기](../windows/predefined-symbol-ids.md)  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 *.NET Framework 개발자 가이드*에서 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
## 요구 사항  
 Win32  
  
## 참고 항목  
 [How to: Search for Symbols in Resources](../windows/how-to-search-for-symbols-in-resources.md)   
 [Resource Editors](../mfc/resource-editors.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)