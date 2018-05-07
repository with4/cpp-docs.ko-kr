---
title: 컴파일러 오류 C2940 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2940
dev_langs:
- C++
helpviewer_keywords:
- C2940
ms.assetid: af6bf2bf-8de6-4cfd-bbf0-4c6b32a30edf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 17f9a89f4adb2da1ef10ae17301e0b36452e43fe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2940"></a>컴파일러 오류 C2940
'class': type-class-id가 지역 typedef로 재정의됩니다.  
  
 제네릭 또는 템플릿 클래스를 지역 `typedef`로 사용할 수 없습니다.  
  
 다음 샘플에서는 C2940을 생성합니다.  
  
```  
// C2940.cpp  
template<class T>  
struct TC {};   
int main() {  
   typedef int TC<int>;   // C2940  
   typedef int TC;   // OK  
}  
```  
  
 C2940은 제네릭을 사용하는 경우에도 발생할 수 있습니다.  
  
```  
// C2940b.cpp  
// compile with: /clr  
generic<class T>  
ref struct GC { };  
  
int main() {  
   typedef int GC<int>;   // C2940  
   typedef int GC;  
}  
```