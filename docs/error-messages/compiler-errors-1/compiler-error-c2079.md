---
title: "컴파일러 오류 C2079 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2079
dev_langs:
- C++
helpviewer_keywords:
- C2079
ms.assetid: ca58d6d5-eccd-40b7-ba14-c003223c5bc7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9eb8dda8af6a71cda1d3a4f9114af238110afc01
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2079"></a>컴파일러 오류 C2079
'identifier' 정의 되지 않은 클래스/구조체/공용 'name'를 사용합니다.  
  
 지정 된 식별자는 정의 되지 않은 클래스, 구조체 또는 공용 구조체는.  
  
 이 오류는 익명 공용 구조체를 초기화 하 여 발생할 수 있습니다.  
  
 다음 샘플에서는 C2079 오류가 생성 됩니다.  
  
```  
// C2079.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   std::ifstream g;   // C2079  
}  
```  
  
 해결 방법:  
  
```  
// C2079b.cpp  
// compile with: /EHsc  
#include <fstream>  
int main( ) {  
   std::ifstream g;  
}  
```  
  
 C2079 인 정방향 선언에만 범위에에서가 type 스택에서 개체를 선언 하려고 하는 경우에 발생할 수 있습니다.  
  
```  
// C2079c.cpp  
class A;  
  
class B {  
   A a;   // C2079  
};  
  
class A {};  
```  
  
 해결 방법:  
  
```  
// C2079d.cpp  
// compile with: /c  
class A;  
class C {};  
  
class B {  
   A * a;  
   C c;  
};  
  
class A {};  
```