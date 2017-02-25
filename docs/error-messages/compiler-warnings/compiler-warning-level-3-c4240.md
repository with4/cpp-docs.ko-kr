---
title: "컴파일러 경고 (수준 3) C4240 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4240"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4240"
ms.assetid: a2657cdb-18e1-493f-882b-4e10c0bca71d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 3) C4240
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장이 사용됨 : 'classname'에 대한 액세스가 이제 'access specifier'\(으\)로 정의됩니다. 이전에는 'access specifier'\(으\)로 정의되었습니다.  
  
 ANSI 규격\([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\)에서는 중첩 클래스에 대한 액세스를 변경할 수 없습니다.  기본 Microsoft 확장\(\/Ze\)에서는 변경할 수 있지만 이 경고가 발생합니다.  
  
## 예제  
  
```  
// C4240.cpp  
// compile with: /W3  
class X  
{  
private:  
   class N;  
public:  
   class N  
   {   // C4240  
   };  
};  
  
int main()  
{  
}  
```