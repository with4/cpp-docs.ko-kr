---
title: 컴파일러 오류 C2198 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2198
dev_langs:
- C++
helpviewer_keywords:
- C2198
ms.assetid: 638a845c-9d7f-4115-a9aa-d72455605668
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6f69874b5c324250338baf480b6bd1cf1c36a1f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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