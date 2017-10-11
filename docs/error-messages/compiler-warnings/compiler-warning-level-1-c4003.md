---
title: "컴파일러 경고 (수준 1) C4003 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4003
dev_langs:
- C++
helpviewer_keywords:
- C4003
ms.assetid: 0ed1c285-4428-4c90-8131-86897e31f115
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0e0ac3c216168ada4f2367adbac509b422aba310
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-level-1-c4003"></a>컴파일러 경고 (수준 1) C4003
'identifier' 매크로의 실제 매개 변수가 부족합니다.  
  
 매크로 정의의 형식 매개 변수 개수가 매크로의 실제 매개 변수 개수를 초과 합니다. 누락 된 매개 변수가 빈 텍스트를 대체 하는 매크로 확장 합니다.  
  
 다음 샘플에서는 C4003 오류가 생성 됩니다.  
  
```  
// C4003.cpp  
// compile with: /WX  
#define test(a,b) (a+b)  
  
int main()  
{  
   int a = 1;  
   int b = 2;  
   a = test(b);   // C4003  
   // try..  
   a = test(a,b);  
}  
```
