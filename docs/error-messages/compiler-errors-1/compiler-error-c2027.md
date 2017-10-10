---
title: "컴파일러 오류 C2027 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2027
dev_langs:
- C++
helpviewer_keywords:
- C2027
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2a2fec9194858127ca08ecc0a891a81a91de48fa
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2027"></a>컴파일러 오류 C2027
정의 되지 않은 'type' 형식을 사용 하 여  
  
 형식 정의 될 때까지 사용할 수 없습니다. 이 오류를 해결 하려면 참조 하기 전에 형식을 완전히 정의 해야 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2027 오류가 발생 합니다.  
  
```  
// C2027.cpp  
class C;  
class D {  
public:  
   void func() {  
   }  
};  
  
int main() {  
   C *pC;  
   pC->func();   // C2027  
  
   D *pD;  
   pD->func();  
}  
```  
  
## <a name="example"></a>예제  
 선언 되지만 정의 되지 않은 형식에 대 한 포인터를 선언 하는 것이 불가능 합니다.  하지만 Visual c + + 정의 되지 않은 형식에 대 한 참조를 허용 하지 않습니다.  
  
 다음 샘플에서는 C2027 오류가 발생 합니다.  
  
```  
// C2027_b.cpp  
class A;  
A& CreateA();  
  
class B;  
B* CreateB();  
  
int main() {  
   CreateA();   // C2027  
   CreateB();   // OK  
}  
```
