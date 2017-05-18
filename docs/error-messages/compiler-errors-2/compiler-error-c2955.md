---
title: "컴파일러 오류 C2955 | Microsoft Docs"
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2955
dev_langs:
- C++
helpviewer_keywords:
- C2955
ms.assetid: 77709fb6-d69b-46fd-a62f-e8564563d01b
caps.latest.revision: 15
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: b790beb88de009e1c7161f3c9af6b3e21c22fd8e
ms.openlocfilehash: 1d2d589ad29896cda2657888c616388e50cc397a
ms.contentlocale: ko-kr
ms.lasthandoff: 03/29/2017

---
# <a name="compiler-error-c2955"></a>컴파일러 오류 C2955
'identifier' : 클래스 템플릿 또는 별칭 제네릭을 사용하려면 템플릿 또는 제네릭 인수 목록이 필요합니다.  
  
 템플릿 또는 제네릭 인수 목록이 없으면 클래스 템플릿 또는 클래스 제네릭을 식별자로 사용할 수 없습니다.  
  
 자세한 내용은 참조 [클래스 템플릿](../../cpp/class-templates.md)합니다.  
  
 다음 샘플에서는 C2955 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C2955.cpp  
// compile with: /c  
template<class T>   
class X {};  
  
X x1;   // C2955  
X<int> x2;   // OK - this is how to fix it.  
```  
  
 클래스 템플릿에 선언된 함수에 대해 아웃오브 라인 정의를 만들 때도 C2955가 발생할 수 있습니다.  
  
```  
// C2955_b.cpp  
// compile with: /c  
template <class T>  
class CT {  
public:  
   void CTFunc();  
   void CTFunc2();  
};  
  
void CT::CTFunc() {}   // C2955  
  
// OK - this is how to fix it  
template <class T>  
void CT<T>::CTFunc2() {}  
  
```  
  
 제네릭을 사용할 때도 C2955가 발생할 수 있습니다.  
  
```  
// C2955_c.cpp  
// compile with: /clr  
generic <class T>   
ref struct GC {   
   T t;  
};  
  
int main() {  
   GC^ g;   // C2955  
   GC <int>^ g;  
}  
```

## <a name="example"></a>예제
**Visual Studio 2017 이상:** 서식 파일 (예를 들어 또는의 일부로 기본 템플릿 인수는 비형식 템플릿 매개 변수) 템플릿 매개 변수 목록에 표시 될 때 올바르게 컴파일러 누락 된 템플릿 인수 목록 진단 합니다. 다음 코드는 Visual Studio 2015에서는 컴파일되지만 Visual Studio 2017에서는 오류를 생성합니다.

```
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias 
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;
```

