---
title: "컴파일러 경고 (수준 1) C4533 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4533
dev_langs: C++
helpviewer_keywords: C4533
ms.assetid: 359fecda-d540-46e5-b214-dbabe9ef50d2
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 729e069612a72799a37135298f9ccce6c36e8a7e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4533"></a>컴파일러 경고(수준 1) C4533
'v 초기화 '명령'에 의해 생략 되었습니다.  
  
 프로그램에는 명령을 변경 제어 흐름이 변수를 초기화 하는 명령이 실행 되지 않았습니다. 다음 샘플에서는 C4533 오류가 생성 됩니다.  
  
```  
// C4533.cpp  
// compile with: /W1  
#include <stdio.h>  
  
struct A  
{  
   int m_data;  
};  
  
int main()  
{  
   if (1)  
   {  
      goto Label;  
   }  
  
   A a = { 100 };  
  
   Label:   // C4533  
      printf("\n%d", a.m_data);   // prints an uninitialized value  
}  
```