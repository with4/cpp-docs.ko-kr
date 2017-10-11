---
title: "컴파일러 오류 C3364 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3364
dev_langs:
- C++
helpviewer_keywords:
- C3364
ms.assetid: 98654741-60fe-4472-a6af-e580f8c0a6e1
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6ca9b4d5ca4362e1d728a854bb776573d25969d7
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3364"></a>컴파일러 오류 C3364
'delegate': 대리 생성자: 인수에 관리 되는 클래스의 멤버 함수 또는 전역 함수에 대 한 포인터 여야 합니다.  
  
 대리 생성자의 두 번째 매개 변수는 멤버 함수의 주소 또는 클래스의 정적 멤버 함수의 주소를 사용 합니다. 둘 다 단순 주소로 처리 됩니다.  
  
 다음 샘플에서는 C3364 오류가 생성 됩니다.  
  
```  
// C3364_2.cpp  
// compile with: /clr  
  
delegate int D( int, int );  
  
ref class C {  
public:  
   int mf( int, int ) {  
      return 1;  
   }  
};  
  
int main() {  
   C^ pC = gcnew C;  
   System::Delegate^ pD = gcnew D( pC,pC->mf( 1, 2 ) ); // C3364  
  
   // try the following line instead  
   // System::Delegate^ pD = gcnew D(pC, &C::mf);  
}  
```  

