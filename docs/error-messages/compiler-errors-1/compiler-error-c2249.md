---
title: "컴파일러 오류 C2249 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2249
dev_langs:
- C++
helpviewer_keywords:
- C2249
ms.assetid: bdd6697c-e04b-49b9-8e40-d9eb6d74f2b6
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5878c28ed0b4fc2663c17021aa9e277ccaa8ad4e
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2249"></a>컴파일러 오류 C2249
'member': 가상 기본 'class'에 선언 된 액세스 멤버에 액세스할 수 있는 경로가 없는  
  
 `member` 비공용에서 상속 된 `virtual` 기본 클래스 또는 구조체입니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2249 오류가 발생 합니다.  
  
```  
// C2249.cpp  
class A {  
private:  
   void privFunc( void ) {};  
public:  
   void pubFunc( void ) {};  
};  
  
class B : virtual public A {} b;  
  
int main() {  
   b.privFunc();    // C2249, private member of A  
   b.pubFunc();    // OK  
}  
```  
  
## <a name="example"></a>예제  
 C2249 다른 스트림에 스트림을 c + + 표준 라이브러리에서 할당 하려는 경우에 발생할 수 있습니다.  다음 샘플에서는 C2249 오류가 발생 합니다.  
  
```  
// C2249_2.cpp  
#include <iostream>  
using namespace std;  
int main() {  
   cout = cerr;   // C2249  
   #define cout cerr;   // OK  
}  
```
