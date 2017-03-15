---
title: "컴파일러 경고 (수준 4) C4714 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4714"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4714"
ms.assetid: 22c7fd0c-899d-4e9b-95f3-725b2c49fb46
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 4) C4714
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' 함수가 인라인이 아니라 \_\_forceinline으로 표시되었습니다.  
  
 주어진 함수를 인라인 확장용으로 선택했지만 컴파일러에서 인라이닝을 수행하지 못했습니다.  
  
 컴파일러에서는 `__forceinline`이 `__inline`보다 강력하지만 컴파일러의 판단에 따라 인라이닝이 수행됩니다. 그러나 이 함수를 인라이닝함으로써 얻는 이익을 결정하기 위한 휴리스틱은 사용되지 않습니다.  
  
 일부 경우에서는 컴파일러가 기계적인 이유로 인해 특정 함수를 인라인하지 않습니다.  예를 들어, 컴파일러에서는 다음과 같은 경우 인라인하지 않습니다.  
  
-   SEH 및 C\+\+ EH 모두가 혼합된 결과가 나타나는 함수  
  
-   \-GX\/EHs\/EHa가 설정되어 있을 때 값에서 전달한 복사 생성된 개체를 사용하는 일부 함수  
  
-   \-GX\/EHs\/EHa가 설정되어 있을 때 값에 의해 풀릴 수 있는 개체를 반환하는 함수  
  
-   \-Og\/Ox\/O1\/O2 없이 컴파일할 때 인라인 어셈블리를 사용하는 함수  
  
-   가변 인수 목록을 사용하는 함수  
  
-   C\+\+ 예외 처리의 **try** 문을 사용하는 함수  
  
 다음 샘플에서는 C4714 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4714.cpp  
// compile with: /Ob1 /GX /W4  
__forceinline void func1()  
{  
   try  
   {  
   }  
   catch (...)  
   {  
   }  
}  
  
void func2()  
{  
   func1();   // C4714  
}  
  
int main()  
{  
}  
```