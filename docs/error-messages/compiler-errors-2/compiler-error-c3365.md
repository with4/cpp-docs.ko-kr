---
title: "컴파일러 오류 C3365 | Microsoft Docs"
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
  - "C3365"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3365"
ms.assetid: 875ec3a4-522c-4e3d-9b67-48808b857f6d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3365
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

연산자 'operator': 피연산자 형식 'type1'과 'type2'가 서로 다릅니다.  
  
 다른 형식의 대리자를 작성하려고 했습니다.  대리자에 대한 자세한 내용은 [방법: 대리자 구성](../../misc/how-to-compose-delegates.md)을 참조하세요.  
  
 다음 샘플에서는 C3365를 생성합니다.  
  
```  
// C3365.cpp // compile with: /clr delegate void D1(); delegate void D2(int); ref class R { public: void f(){} void g(int){} }; int main() { D1^ d1 = gcnew D1(gcnew R, &R::f); D2^ d2 = gcnew D2(gcnew R, &R::g); D1^ d3 = gcnew D1(gcnew R, &R::f); d1 += d2;   // C3365 d1 += d3;   // OK d1(); }  
```