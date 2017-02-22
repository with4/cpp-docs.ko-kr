---
title: "Including Shared (Read-Only) or Calculated Symbols | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.symbol.shared.calculated"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "symbols, read-only"
  - "symbols, shared"
  - "symbols, calculated"
  - "read-only symbols"
  - "symbol directives"
  - "calculated symbols"
  - "shared symbols"
ms.assetid: 32b77faf-a066-4371-a072-9a5b84c0766d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Including Shared (Read-Only) or Calculated Symbols
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다른 응용 프로그램에서 만든 리소스 파일을 처음으로 개발 환경에서 읽는 경우 포함된 헤더 파일을 모두 읽기 전용으로 표시합니다.  그런 다음 [리소스 내용 대화 상자](../windows/resource-includes-dialog-box.md)를 사용하여 읽기 전용 기호 헤더 파일을 더 추가할 수 있습니다.  
  
 읽기 전용 기호 정의를 사용하려는 한 가지 이유는 여러 프로젝트에서 공유하려고 하는 기호 파일 때문입니다.  
  
 또한 단순 정수 대신 식을 사용하여 기호 값을 정의하는 기호 정의를 사용하는 기존 리소스가 있는 경우에 포함된 기호 파일을 사용할 수 있습니다.  예:  
  
```  
#define   IDC_CONTROL1 2100  
#define   IDC_CONTROL2 (IDC_CONTROL1+1)  
```  
  
 다음과 같은 경우 환경에서 이러한 계산된 기호를 올바르게 해석합니다.  
  
-   계산된 기호가 읽기 전용 기호 파일에 배치됩니다.  
  
-   리소스 파일에 이러한 계산된 기호가 이미 할당된 리소스가 포함되어 있습니다.  
  
-   숫자 식이 필요합니다.  
  
> [!NOTE]
>  문자열이나 숫자 식이 필요한 경우에는 식이 계산되지 않습니다.  
  
### 리소스 파일에 공유\(읽기 전용\) 기호를 포함하려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md)에서 .rc 파일을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 [리소스 내용](../windows/resource-includes-dialog-box.md)을 선택합니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  **읽기 전용 기호 지시문** 상자에서 **\#include** 컴파일러 지시문을 사용하여 읽기 전용 기호를 유지할 파일을 지정합니다.  
  
     Resource.h는 주 기호 헤더 파일에 일반적으로 사용되는 파일 이름이므로 이 파일은 호출하지 마세요.  
  
    > [!NOTE]
    >  **중요** 읽기 전용 기호 지시문 상자에 입력한 내용은 입력한 대로 정확하게 리소스 파일에 포함됩니다.  입력한 내용에 맞춤법이나 구문 오류가 없는지 확인하세요.  
  
     **읽기 전용 기호 지시문** 상자를 사용하여 기호 정의가 있는 파일만 포함합니다.  리소스 정의는 포함하지 마세요. 그렇지 않으면 파일을 저장할 때 중복된 리소스 정의가 생성됩니다.  
  
3.  지정한 파일에 기호를 배치합니다.  
  
     이런 식으로 포함된 파일의 기호는 리소스 파일을 열 때마다 계산되지만 파일을 저장할 때 디스크에서 교체되지는 않습니다.  
  
4.  **확인**을 클릭합니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
 요구 사항  
  
 Win32  
  
## 참고 항목  
 [Symbol Name Restrictions](../windows/symbol-name-restrictions.md)   
 [Symbol Value Restrictions](../windows/symbol-value-restrictions.md)   
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)   
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)