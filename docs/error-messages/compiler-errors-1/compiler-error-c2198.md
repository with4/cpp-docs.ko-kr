---
title: "컴파일러 오류 C2198 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2198
dev_langs:
- C++
helpviewer_keywords:
- C2198
ms.assetid: 638a845c-9d7f-4115-a9aa-d72455605668
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0da955515b5ad51836a82563fcfdf8d70de14470
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2198"></a>컴파일러 오류 C2198
'function': 호출에 매개 변수가 너무 적습니다.  
  
 컴파일러가 함수 호출 매개 변수를 너무 적게 발견했거나 잘못된 함수 선언을 발견했습니다.  
  
 다음 샘플에서는 C2198 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2198.c  
// compile with: /c  
void func( int, int );  
int main() {  
   func( 1 );   // C2198 only one actual parameter  
   func( 1, 1 );   // OK  
}  
```
