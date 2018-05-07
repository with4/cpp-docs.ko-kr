---
title: 컴파일러 오류 C2974 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2974
dev_langs:
- C++
helpviewer_keywords:
- C2974
ms.assetid: 1b444260-f2bf-48d7-ab1e-35573d8c4a0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 12af6bcd61642d8563eb08888229aab6217b6085
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2974"></a>컴파일러 오류 C2974
잘못 된 형식 인수 'number' 형식이 필요합니다.  
  
 제네릭 또는 템플릿 인수는 제네릭 또는 템플릿 선언이 일치 하지 않습니다. 형식을 꺾쇠 괄호 안에 표시 됩니다. 올바른 유형을 검색 하는 제네릭 또는 템플릿 정의 확인 합니다.  
  
 다음 샘플에서는 C2974 오류가 생성 됩니다.  
  
```  
// C2974.cpp  
// C2974 expected  
template <class T>  
struct TC {};  
  
template <typename T>  
void tf(T){}  
  
int main() {  
   // Delete the following 2 lines to resolve  
   TC<1>* tc;  
   tf<"abc">("abc");  
  
   TC<int>* tc;  
   tf<const char *>("abc");  
}  
```  
  
 C2974는 제네릭을 사용 하는 경우에 발생할 수 있습니다.  
  
```  
// C2974b.cpp  
// compile with: /clr  
// C2974 expected  
using namespace System;  
generic <class T>  
ref struct GCtype {};  
  
generic <typename T>  
void gf(T){}  
  
int main() {  
   // Delete the following 2 lines to resolve  
   GCtype<"a">^ gc;  
   gf<"a">("abc");  
  
   // OK  
   GCtype<int>^ gc;  
   gf<String ^>("abc");  
}  
```