---
title: "컴파일러 오류 C2647 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2647
dev_langs: C++
helpviewer_keywords: C2647
ms.assetid: 1034589e-bc3e-41a6-831f-2a1a4b8a2500
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8d9a068e70f39f05624cc1af843f1c8ae8db7caf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2647"></a>컴파일러 오류 C2647
'operator': 'type2'에서 'type1' 역 참조할 수 없습니다  
  
 멤버 포인터 연산자의 왼쪽된 피연산자 ( `->*` 또는 `.*` ) 오른쪽 연산자와 관련 된 형식으로 암시적으로 변환할 수 없습니다.  
  
 다음 샘플에서는 C2647 오류가 생성 됩니다.  
  
```  
// C2647.cpp  
class C {};  
class D {};  
  
int main() {  
   D d, *pd;  
   C c, *pc = 0;  
   int C::*pmc = 0;  
   pd->*pmc = 0;   // C2647  
   d.*pmc = 0;   // C2647  
  
   // OK  
   pc->*pmc = 0;  
   c.*pmc = 0;  
}  
```