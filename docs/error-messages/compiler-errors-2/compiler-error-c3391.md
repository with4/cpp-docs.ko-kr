---
title: "컴파일러 오류 C3391 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3391"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3391"
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3391
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type\_arg': 제네릭 'generic\_type'의 제네릭 매개 변수 'param'에 대한 형식 인수가 잘못되었습니다. null을 허용하지 않는 값 형식이어야 합니다.  
  
 제네릭 형식이 잘못 인스턴스화되었습니다.  형식 정의를 확인하세요.  자세한 내용은 <xref:System.Nullable> 및 [Generics](../../windows/generics-cpp-component-extensions.md)를 참조하세요.  
  
## 예제  
 C\#을 사용하는 다음 샘플에서 [!INCLUDE[vcprvclong](../../error-messages/compiler-errors-2/includes/vcprvclong_md.md)]에 제네릭 형식을 제작하는 경우 지원되지 않는 특정 제약 조건과 함께 제네릭 형식을 포함하는 구성 요소를 만듭니다. 자세한 내용은 [형식 매개 변수에 대한 제약 조건](../Topic/Constraints%20on%20Type%20Parameters%20\(C%23%20Programming%20Guide\).md)을 참조하세요.  
  
```  
// C3391.cs // compile with: /target:library // a C# program public class GR<N> where N : struct {}  
```  
  
## 예제  
 다음 샘플에서는 C3391을 생성합니다.  
  
```  
// C3391_b.cpp // compile with: /clr #using <C3391.dll> using namespace System; value class VClass {}; int main() { GR< Nullable<VClass> >^ a = gcnew GR< Nullable<VClass> >();   // C3391 can't be Nullable GR<VClass>^ aa = gcnew GR<VClass>();   // OK }  
```