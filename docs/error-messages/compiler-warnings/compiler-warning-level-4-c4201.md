---
title: "컴파일러 경고 (수준 4) C4201 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4201"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4201"
ms.assetid: 6156f508-9393-4d77-9e73-1ec3e1c32d0d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 4) C4201
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장을 사용했습니다 : 구조체\/공용 구조체의 이름이 없습니다.  
  
 Microsoft 확장\(\/Ze\)에서는 구조체를 선언자 없이 다른 구조체나 공용 구조체의 멤버로 지정할 수 있습니다.  이러한 구조체는 ANSI 규격\([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\)에서는 오류를 발생시킵니다.  
  
## 예제  
  
```  
// C4201.cpp  
// compile with: /W4  
struct S  
{  
   float y;  
   struct  
   {  
      int a, b, c;  // C4201  
   };  
} *p_s;  
  
int main()  
{  
}  
```