---
title: "컴파일러 오류 C3392 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3392"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3392"
ms.assetid: e4757596-e2aa-4314-b01e-5c4bfd2110e9
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C3392
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type\_arg': 제네릭 'generic\_type'의 제네릭 매개 변수 'param'에 대한 형식 인수가 잘못되었습니다. 매개 변수가 없는 public 생성자가 있어야 합니다.  
  
 제네릭 형식이 잘못 인스턴스화되었습니다.  형식 정의를 확인하세요.  자세한 내용은 [Generics](../../windows/generics-cpp-component-extensions.md)을 참조하세요.  
  
## 예제  
 C\#을 사용하는 다음 샘플에서 [!INCLUDE[vcprvclong](../../error-messages/compiler-errors-2/includes/vcprvclong_md.md)]에 제네릭 형식을 제작하는 경우 지원되지 않는 특정 제약 조건과 함께 제네릭 형식을 포함하는 구성 요소를 만듭니다. 자세한 내용은 [형식 매개 변수에 대한 제약 조건](../Topic/Constraints%20on%20Type%20Parameters%20\(C%23%20Programming%20Guide\).md)을 참조하세요.  
  
```  
// C3392.cs // compile with: /target:library // a C# program public class GR<C, V, N> where C : class where V : struct where N : new() {}  
```  
  
## 예제  
 다음 샘플에서는 C3392를 생성합니다.  
  
```  
// C3392_b.cpp // compile with: /clr #using <C3392.dll> ref class R { R(int) {} }; ref class N { N() {} }; value class V {}; ref class N2 { public: N2() {} }; ref class R2 { public: R2() {} }; int main () { GR<R^, V, N^>^ gr1;   // C3392 GR<R^, V, N2^>^ gr1a;   // OK GR<R^, N^, N^>^ gr3;   // C3392 GR<R^, V, N2^>^ gr3a;   // OK GR<R^, V, R^>^ gr4;   // C3392 GR<R^, V, R2^>^ gr4a;   // OK }  
```