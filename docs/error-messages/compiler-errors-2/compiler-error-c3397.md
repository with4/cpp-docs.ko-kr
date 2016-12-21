---
title: "컴파일러 오류 C3397 | Microsoft Docs"
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
  - "C3397"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3397"
ms.assetid: a8536e87-79c4-4ed7-bd96-42704d06391f
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3397
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본 인수에서는 집합체 초기화가 허용되지 않습니다.  
  
 배열이 잘못 선언되었습니다.  자세한 내용은 [Arrays](../../windows/arrays-cpp-component-extensions.md)를 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3397을 생성합니다.  
  
```  
// C3397.cpp // compile with: /clr // /clr /c void Func(array<int> ^p = gcnew array<int> { 1, 2, 3 });   // C3397 void Func2(array<int> ^p = gcnew array<int> (3));   // OK int main() { array<int> ^p = gcnew array<int> { 1, 2, 3};   // OK }  
```