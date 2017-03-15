---
title: "리소스 기호 대화 상자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.resourcesymbols"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "새 기호 대화 상자"
  - "리소스 기호 대화 상자"
  - "기호 변경 대화 상자"
ms.assetid: 9706cde3-1f48-4fcd-bedb-2b03b455e3c1
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 리소스 기호 대화 상자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**리소스 기호** 대화 상자에서는 새 리소스 기호를 추가하거나, 표시되는 기호를 변경하거나, 소스 코드에서 기호를 사용 중인 위치로 건너뛸 수 있습니다.  
  
 **이름**  
 기호의 이름을 표시합니다.  자세한 내용은 [기호 이름 제한](../windows/symbol-name-restrictions.md)을 참조하세요.  
  
 **값**  
 기호의 숫자 값을 표시합니다.  자세한 내용은 [기호 값 제한](../windows/symbol-value-restrictions.md)을 참조하세요.  
  
 **사용 중**  
 선택하면 하나 이상의 리소스에서 기호를 사용하고 있음을 지정합니다.  해당 리소스가 다음에서 사용 상자에 나열됩니다.  
  
 **읽기 전용 기호 표시**  
 선택하면 읽기 전용 리소스를 표시합니다.  기본적으로 리소스 기호 대화 상자에는 리소스 스크립트 파일에서 수정 가능한 리소스만 표시되지만 이 옵션을 선택하면 수정 가능한 리소스는 굵은 텍스트로 표시되고 읽기 전용 리소스는 일반 텍스트로 표시됩니다.  
  
 **다음에서 사용**  
 기호 목록에서 선택한 기호를 사용하여 리소스를 표시합니다.  지정된 리소스에 대한 편집기로 이동하려면 **다음에서 사용** 상자에서 리소스를 선택하고 **사용 리소스 보기**를 클릭합니다.  자세한 내용은 [특정 기호에 대한 리소스 편집기 열기](../windows/opening-the-resource-editor-for-a-given-symbol.md)를 참조하세요.  
  
 **새로 만들기**  
 새 기호화된 리소스 식별자의 이름 및 필요한 경우 값을 정의할 수 있는 새 기호 대화 상자를 엽니다.  자세한 내용은 [새 기호 만들기](../windows/creating-new-symbols.md)를 참조하세요.  
  
 **변경**  
 기호의 이름 또는 값을 변경할 수 있는 기호 변경 대화 상자를 엽니다.  사용 중인 컨트롤 또는 리소스에 대한 기호인 경우 해당 리소스 편집기에서만 기호를 변경할 수 있습니다.  자세한 내용은 [할당되지 않은 기호 변경](../windows/changing-unassigned-symbols.md)을 참조하세요.  
  
 **사용 리소스 보기**  
 해당 리소스 편집기에서 기호를 포함하는 리소스를 엽니다.  자세한 내용은 [특정 기호에 대한 리소스 편집기 열기](../windows/opening-the-resource-editor-for-a-given-symbol.md)를 참조하세요.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
## 요구 사항  
 Win32  
  
## 참고 항목  
 [Viewing Resource Symbols](../windows/viewing-resource-symbols.md)