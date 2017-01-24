---
title: "컴파일러 경고 (수준 3) C4243 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4243"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4243"
ms.assetid: ca72f9ad-ce0b-43a9-a68c-106e1f8b90ef
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 3) C4243
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'conversion type' 변환\('type1'에서 'type2'\(으\)로\)이 있지만 액세스할 수 없습니다.  
  
 파생 클래스에 대한 포인터를 기본 클래스에 대한 포인터로 변환했지만 파생 클래스가 전용 또는 보호된 액세스를 통해 기본 클래스에서 상속됩니다.  
  
 다음 샘플에서는 C4243 오류가 발생하는 경우를 보여 줍니다.  
  
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