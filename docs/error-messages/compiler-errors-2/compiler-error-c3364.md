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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cdf9f9a6d4ae6584ff3b30e71a0c74b0ca777afe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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
