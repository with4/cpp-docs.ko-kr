---
title: "컴파일러 오류 C2199 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2199
dev_langs:
- C++
helpviewer_keywords:
- C2199
ms.assetid: 6a92a1b7-7906-49e6-a31f-e8bffbc7706a
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 28410dfc8ced15c7c3cddd55b5403f45d1b15e78
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2199"></a>컴파일러 오류 C2199
구문 오류: 찾을 ' 식별자 (' 전역 범위에서 (의도 한 선언 ि ल ्?)  
  
 지정된 된 컨텍스트 구문 오류가 발생 했습니다. 잘못 된 선언 구문이 있을 수 있습니다.  
  
 다음 샘플에서는 C2199 오류가 생성 됩니다.  
  
```  
// C2199.cpp  
// compile with: /c  
int j = int(1) int(1);   // C2199  
int j = 1;   // OK  
```
