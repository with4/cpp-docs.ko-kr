---
title: "컴파일러 오류 C2312 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2312
dev_langs:
- C++
helpviewer_keywords:
- C2312
ms.assetid: c8bcfd06-12c1-4323-bb53-ba392d36daa4
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5d660a82b0bdf1b77848c993f6796ac3fa45e1ff
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2312"></a>컴파일러 오류 C2312
'exception1': 줄 번호에서 'exception2'에 의해 catch되었습니다.  
  
 두 개의 처리기가 동일한 예외 형식을 catch합니다.  
  
 다음 샘플에서는 C2312를 생성합니다.  
  
```  
// C2312.cpp  
// compile with: /EHsc  
#include <eh.h>  
int main() {  
    try {  
        throw "ooops!";  
    }  
    catch( signed int ) {}  
    catch( int ) {}   // C2312  
}  
```
