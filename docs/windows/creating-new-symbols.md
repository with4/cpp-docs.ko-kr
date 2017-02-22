---
title: "Creating New Symbols | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.symbol.creating"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "New Symbol dialog box"
  - "symbols, creating"
ms.assetid: 35168d31-3af6-4ecd-9362-3707d47b53f3
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Creating New Symbols
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

새 프로젝트를 시작하는 경우 기호 이름이 할당될 리소스를 만들기 전에 필요한 기호 이름을 매핑하는 것이 편리하다는 것을 알 수 있습니다.  
  
### 리소스 기호 대화 상자를 사용하여 새 기호를 만들려면  
  
1.  [리소스 기호 대화 상자](../windows/resource-symbols-dialog-box.md)에서 **새로 만들기**를 선택합니다.  
  
2.  **이름** 상자에 기호 이름을 입력합니다.  
  
3.  할당된 기호 값을 적용합니다.  
  
     또는  
  
     **값** 상자에 새 값을 입력합니다.  
  
4.  **확인**을 클릭하여 기호 목록에 새 기호를 추가합니다.  
  
 이미 있는 기호 이름을 입력하면 해당 이름을 사용하는 기호가 이미 정의되어 있다는 메시지 상자가 나타납니다.  이름이 같은 기호를 두 개 이상 정의할 수는 없지만 동일한 숫자 값을 사용하는 서로 다른 기호는 정의할 수 있습니다.  자세한 내용은 [기호 이름 제한](../windows/symbol-name-restrictions.md) 및 [기호 값 제한](../windows/symbol-value-restrictions.md)을 참조하세요.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
 요구 사항  
  
 Win32  
  
## 참고 항목  
 [Viewing Resource Symbols](../windows/viewing-resource-symbols.md)   
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)