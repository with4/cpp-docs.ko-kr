---
title: "컴파일러 오류 C3287 | Microsoft Docs"
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
  - "C3287"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3287"
ms.assetid: c1fa73d2-2c82-4136-a7da-0e75e3b420ad
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3287
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' 형식\(GetEnumerator의 반환 형식\)에는 적절한 공용 MoveNext 멤버 함수 및 공용 Current 속성이 있어야 합니다.  
  
 사용자 정의 컬렉션 클래스에는 `MoveNext` 및 `Current`에 대한 정의가 포함되어야 합니다.  
  
 자세한 내용은 [방법: for each로 사용자 정의 컬렉션 반복](../../dotnet/how-to-iterate-over-a-user-defined-collection-with-for-each.md)를 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3287을 생성합니다.  
  
```  
// C3287.cpp // compile with: /clr using namespace System; ref struct R { bool MoveNext() { return true; } property Object^ Current { Object^ get() { Object ^ o = gcnew Object; return o; } } }; ref struct R2 { R ^GetEnumerator() { R^ r = gcnew R; return r; } }; ref struct T {}; ref struct T2 { T ^GetEnumerator() { T^ t = gcnew T; return t; } }; int main() { for each (int i in gcnew T2) {}   // C3287 for each (int i in gcnew R2) {}   // OK }  
```