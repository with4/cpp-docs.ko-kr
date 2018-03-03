---
title: "컴파일러 오류 C2597 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2597
dev_langs:
- C++
helpviewer_keywords:
- C2597
ms.assetid: 2e48127d-e3ff-4a40-8156-2863e45b1a38
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7530805c7b5ad1e16ec95ea69324f6717791a6f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2597"></a>컴파일러 오류 C2597
비정적 멤버 'identifier'에 대한 참조가 잘못되었습니다.  
  
 가능한 원인:  
  
1.  비정적 멤버가 정적 멤버 함수에 지정되었습니다. 비정적 멤버에 액세스하려면 클래스의 로컬 인스턴스를 전달하거나 만들고 멤버 액세스 연산자(`.` 또는 `->`)를 사용해야 합니다.  
  
2.  지정한 식별자가 클래스, 구조체 또는 공용 구조체의 멤버가 아닙니다. 식별자 맞춤법을 검사합니다.  
  
3.  멤버 액세스 연산자가 비멤버 함수를 참조합니다.  
  
4.  다음 샘플에서는 C2597을 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C2597.cpp  
// compile with: /c  
struct s1 {  
   static void func();  
   static void func2(s1&);  
   int i;  
};  
  
void s1::func() {  
   i = 1;    // C2597 - static function can't access non-static data member  
}  
  
// OK - fix by passing an instance of s1  
void s1::func2(s1& a) {  
   a.i = 1;  
}  
```