---
title: "컴파일러 경고 C4959 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4959"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4959"
ms.assetid: 3a128f3e-4d8a-4565-ba1a-5d32fdeb5982
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 경고 C4959
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

해당 멤버에 액세스하면 비안정형 코드가 생성되므로 \/clr:safe를 지정하는 경우 관리되지 않는 구조체 'type'을 정의할 수 없습니다.  
  
 관리되지 않는 형식의 멤버에 액세스하면 확인할 수 없는 \(peverify.exe\) 이미지가 생성됩니다.  
  
 자세한 내용은 [순수형 및 안정형 코드](../../dotnet/pure-and-verifiable-code-cpp-cli.md)을 참조하세요.  
  
 이 경고는 오류로 발생하며 [warning](../../preprocessor/warning.md) pragma 또는 [\/wd](../../build/reference/compiler-option-warning-level.md) 컴파일러 옵션과 함께 사용하지 않도록 설정할 수 있습니다.  
  
 다음 샘플에서는 C4959를 생성합니다.  
  
```  
// C4959.cpp // compile with: /clr:safe // Uncomment the following line to resolve. // #pragma warning( disable : 4959 ) struct X { int data; }; int main() { X x; x.data = 10;   // C4959 }  
```