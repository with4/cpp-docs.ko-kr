---
title: "컴파일러 오류 C2653 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2653
dev_langs:
- C++
helpviewer_keywords:
- C2653
ms.assetid: 3f49e731-affd-43a0-a8d0-181db7650bc3
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: eb0c1bf407d1478451c246cf615d031ef6c45bf9
ms.openlocfilehash: 2203cf8a09dbb05f6145ed238ab9fc03e458aaa5
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2653"></a>컴파일러 오류 C2653
'identifier': 클래스 또는 네임 스페이스 이름이 아닙니다  
  
구문에는 클래스, 구조체, 공용 구조체 또는 네임 스페이스 이름이 필요합니다.  
  
다음 샘플에서는 c2653 오류가 발생 합니다.  
  
```cpp  
// C2653.cpp  
// compile with: /c  
class yy {  
   void func1(int i);  
};  
  
void xx::func1(int m) {}   // C2653  
void yy::func1(int m) {}   // OK  
```  
  
C2653 것도 가능 정의 하려는 경우는 *복합 네임 스페이스*, Visual Studio 2015 업데이트 3 이전의 Visual c + +의 버전을 사용 하면 하나 이상의 범위 중첩 된 네임 스페이스 이름을 포함 하는 네임 스페이스입니다. 복합 네임 스페이스 정의 C + +&17; 전에 c + +에서 사용할 수 없습니다. Visual c + + 2015 업데이트 3 부터는 컴파일러 지원 복합 네임 스페이스 정의 때는 [/std:c + + 최신](../../build/reference/std-specify-language-standard-version.md) 컴파일러 옵션을 지정 합니다.  
```cpp  
// C2653b.cpp  
namespace a::b {int i;}   // C2653 prior to Visual C++ 2015 Update 3,  
                          // C2429 thereafter. Use /std:c++latest to fix.
namespace a {  
   namespace b {  
      int i;  
   }  
}  
  
int main() {  
   a::b::i = 2;  
}  
```  
