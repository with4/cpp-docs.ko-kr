---
title: "컴파일러 오류 C2139 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2139
dev_langs:
- C++
helpviewer_keywords:
- C2139
ms.assetid: 31e047c0-5bf9-46c2-b6de-b627ea6a5768
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 81c1b41a452068d572169d670f2a288f92f93142
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2139"></a>컴파일러 오류 C2139
'type': 정의 되지 않은 클래스는 컴파일러 내장 형식 특성 '특성'에 대 한 인수로 사용할 수 없습니다  
  
 형식 특성에 잘못 된 인수가 전달 되었습니다.  
  
 자세한 내용은 참조 [형식 특성에 대 한 컴파일러 지원](../../windows/compiler-support-for-type-traits-cpp-component-extensions.md)합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C2139 오류가 발생 합니다.  
  
```  
// C2139.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
template <class T>  
struct is_polymorphic {  
   static const bool value = __is_polymorphic(T);  
};  
  
class C;  
class D {};  
  
class E {  
public:  
   virtual void Test() {}  
};  
  
int main() {  
   cout << is_polymorphic<C>::value << endl;   // C2139  
   cout << is_polymorphic<D>::value << endl;   // OK  
   cout << is_polymorphic<E>::value << endl;   // OK  
}  
```