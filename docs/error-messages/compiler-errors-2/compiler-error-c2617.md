---
title: 컴파일러 오류 C2617 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2617
dev_langs:
- C++
helpviewer_keywords:
- C2617
ms.assetid: d6a435d2-7d95-4dbf-ad4a-abe4744f63e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cf84ec0de54b96800d56086c79dc5ff5f82b59e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33231792"
---
# <a name="compiler-error-c2617"></a>컴파일러 오류 C2617
'function': return 문이 일관성이 없습니다  
  
 지정된 된 함수는 선언 된 반환 형식이 돌아와 이전 문 값을 지정 하지 않은 없습니다.  
  
 다음 샘플에서는 C2617 오류가 생성 됩니다.  
  
```  
// C2617.cpp  
int i;  
func() {   // no return type prototype  
   if( i ) return;   // no return value  
   else return( 1 );   // C2617 detected on this line  
}  
```  
  
 해결 방법:  
  
```  
// C2617b.cpp  
// compile with: /c  
int i;  
int MyF() {  
   if (i)  
      return 0;  
   else   
      return (1);  
}  
```