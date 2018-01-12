---
title: "컴파일러 경고 (수준 3) C4243 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4243
dev_langs: C++
helpviewer_keywords: C4243
ms.assetid: ca72f9ad-ce0b-43a9-a68c-106e1f8b90ef
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b3449dc305495848517687b7404dbdab5528e9a2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4243"></a>컴파일러 경고(수준 3) C4243
'conversion type' 변환이 'type1'에서 'type2' (으) 있지만 액세스할 수 없으면  
  
 파생된 클래스에 대 한 포인터는 기본 클래스에 대 한 포인터로 변환 됩니다 하지만 파생된 클래스는 private 또는 protected 액세스를 사용 하 여 기본 클래스를 상속 합니다.  
  
 다음 샘플에서는 C4243 오류가 생성 됩니다.  
  
```  
// C4243.cpp  
// compile with: /W3  
// C4243 expected  
struct B {  
   int f() {  
      return 0;  
   };  
};  
  
struct D : private B {};  
struct E : public B {};  
  
int main() {  
   // Delete the following 2 lines to resolve.  
   int (D::* d)() = (int(D::*)()) &B::f;   
   d;  
  
   int (E::* e)() = (int(E::*)()) &B::f; // OK  
   e;  
}  
```