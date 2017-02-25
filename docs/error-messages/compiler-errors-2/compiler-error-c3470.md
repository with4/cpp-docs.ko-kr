---
title: "컴파일러 오류 C3470 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3470"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3470"
ms.assetid: 170c7a9d-214d-41b1-8f15-d4a4fc38aaa5
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# 컴파일러 오류 C3470
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 클래스에 인덱서\(인덱싱된 기본 속성\)와 operator\[\]가 동시에 포함될 수 없습니다.  
  
 하나의 형식으로 기본 인덱서와 연산자\[\]를 모두 정의할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 C3470을 생성합니다.  
  
```  
// C3470.cpp // compile with: /clr using namespace System; ref class R { public: property int default[int] { int get(int i) { return i+1; } } int operator[](String^ s) { return Convert::ToInt32(s); }   // C3470 }; int main() { R ^ r = gcnew R; // return r[9] + r["32"] - 42; }  
```