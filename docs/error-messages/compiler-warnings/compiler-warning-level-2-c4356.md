---
title: "컴파일러 경고 (수준 2) C4356 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4356
dev_langs: C++
helpviewer_keywords: C4356
ms.assetid: 3af3defe-de33-43b6-bd6c-2c2e09e34f3f
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cd32ad76e83a51ad361b7d0226fa73fd88b58214
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="compiler-warning-level-2-c4356"></a>컴파일러 경고(수준 2) C4356
'member': 파생된 클래스를 통해 정적 데이터 멤버를 초기화할 수 없습니다  
  
 정적 데이터 멤버의 초기화가 잘못 되었습니다. 컴파일러는 초기화를 허용합니다. 경고를 방지 하려면 기본 클래스를 통해 멤버를 초기화 합니다.  
  
 사용 하 여는 [경고](../../preprocessor/warning.md) pragma를이 경고를 표시 합니다.  
  
 다음 샘플에서는 C4356 오류가 생성 됩니다.  
  
```  
// C4356.cpp  
// compile with: /W2 /EHsc  
#include <iostream>  
  
template <class T>  
class C {  
   static int n;  
};  
  
class D : C<int> {};  
  
int D::n = 0; // C4356  
// try the following line instead  
// int C<int>::n = 0;  
  
class A {  
public:  
   static int n;  
};  
  
class B : public A {};  
  
int B::n = 10;   // C4356  
// try the following line instead  
// int A::n = 99;  
  
int main() {  
   using namespace std;  
   cout << B::n << endl;  
}  
```