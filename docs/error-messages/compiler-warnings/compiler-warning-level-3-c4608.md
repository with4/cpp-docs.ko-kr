---
title: "컴파일러 경고 (수준 3) C4608 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4608
dev_langs: C++
helpviewer_keywords: C4608
ms.assetid: 8b8f5f28-8ce9-457e-9d3d-a8c0efce9b6a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7634d5520fa4407496ba161ca6a4de55cf730b24
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4608"></a>컴파일러 경고(수준 3) C4608
'union_member'가 이미 이니셜라이저 목록의 다른 공용 구조체 멤버 'union_member'에 의해 초기화되었습니다.  
  
 동일한 공용 구조체의 두 멤버가 초기화 목록에서 초기화되었습니다. 공용 구조체 멤버 중 하나에만 액세스할 수 있습니다.  
  
 다음 샘플에서는 C4608 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4608.cpp  
// compile with: /W3 /c  
class X {  
public:  
   X(char c) : m_i( c + 1), m_c(c) {}   // C4608  
   // try the following line instead  
   // X(char c) : m_c(c) {}  
  
private:  
   union {  
      int m_i;  
      char m_c;  
   };  
};  
  
union Y {  
public:  
   Y(char * name) : m_number(0.3), m_string( name ) {} // C4608  
  
private:  
   double m_number;  
   char * m_string;  
};  
```