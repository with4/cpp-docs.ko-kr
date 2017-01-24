---
title: "컴파일러 경고 C4957 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4957"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4957"
ms.assetid: a18c52d4-23e2-44f1-b4b5-f7fa5a7f3987
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 C4957
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'cast': 'cast\_from'에서 'cast\_to'로의 명시적 캐스트는 확인할 수 없습니다.  
  
 캐스트로 인해 확인할 수 없는 이미지가 발생합니다.  
  
 일부 캐스트는 안전합니다\(예: 사용자 정의 변환을 트리거하는 `static_cast` 및 `const_cast`\).[safe\_cast](../../windows/safe-cast-cpp-component-extensions.md)는 확인할 수 있는 코드를 생성합니다.  
  
 자세한 내용은 [순수형 및 안정형 코드](../../dotnet/pure-and-verifiable-code-cpp-cli.md)을 참조하세요.  
  
 이 경고는 오류로 발생하며 [warning](../../preprocessor/warning.md) pragma 또는 [\/wd](../../build/reference/compiler-option-warning-level.md) 컴파일러 옵션과 함께 사용하지 않도록 설정할 수 있습니다.  
  
 다음 샘플에서는 C4957을 생성합니다.  
  
```  
// C4957.cpp // compile with: /clr:safe // #pragma warning( disable : 4957 ) using namespace System; int main() { Object ^ o = "Hello, World!"; String ^ s = static_cast<String^>(o);   // C4957 String ^ s2 = safe_cast<String^>(o);   // OK }  
```