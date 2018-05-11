---
title: 컴파일러 오류 C2942 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2942
dev_langs:
- C++
helpviewer_keywords:
- C2942
ms.assetid: 13abf744-8fa1-450d-886d-e5717c04956e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55dc1fc5c2762751762b3798d28245224281ce67
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2942"></a>컴파일러 오류 C2942
'class': type-class-id가 함수의 정식 인수로 재정의되었습니다.  
  
 제네릭 또는 템플릿 클래스를 정식 인수로 사용할 수 없습니다. 제네릭 또는 템플릿 클래스의 생성자에 직접 인수를 전달할 수 없습니다.  
  
 다음 샘플에서는 C2942를 생성합니다.  
  
```  
  
// C2942.cpp  
// compile with: /c  
template<class T>  
struct TC {};   
void f(int TC<int>) {}   // C2942  
  
// OK  
struct TC2 {};  
void f(TC2 i) {}  
```  
  
 C2942는 제네릭을 사용하는 경우에도 발생할 수 있습니다.  
  
```  
// C2942b.cpp  
// compile with: /clr /c  
generic<class T>  
ref struct GC {};  
void f(int GC<int>) {}   // C2942  
ref struct GC2 { };  
void f(int GC2) {}  
```