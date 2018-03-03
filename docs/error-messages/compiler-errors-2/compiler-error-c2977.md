---
title: "컴파일러 오류 C2977 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2977
dev_langs:
- C++
helpviewer_keywords:
- C2977
ms.assetid: 3c4218e0-5d03-4a2b-b757-c507c35f3542
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: df66aed1b9d3e605391ac5ae3562bc7089645141
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2977"></a>컴파일러 오류 C2977
'identifier': 형식 인수가 너무 많습니다.  
  
 제네릭 또는 템플릿에 실제 인수가 너무 많습니다. 제네릭 또는 템플릿 선언을 확인하여 올바른 매개 변수 개수를 찾습니다.  
  
 다음 샘플에서는 C2977을 생성합니다.  
  
```  
// C2977.cpp  
// compile with: /c  
template<class T, int i>   
class MyClass {};  
  
template MyClass< int , 1, 1 >;   // C2977  
template MyClass< int , 1 >;   // OK  
```  
  
 C2977은 제네릭을 사용하는 경우에도 발생할 수 있습니다.  
  
```  
// C2977b.cpp  
// compile with: /clr  
// C2977 expected  
generic <class T, class U>   
void f(){}  
  
generic <class T>   
ref struct GC1 {};  
  
int main() {  
   // Delete the following 2 lines to resolve.  
   GC1<int, char> ^ pgc1;  
   f<int,int,int>();  
  
   // OK  
   GC1<int> ^ pgc1;  
   f<int, int>();  
}  
```