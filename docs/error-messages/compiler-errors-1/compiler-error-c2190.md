---
title: "컴파일러 오류 C2190 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2190
dev_langs:
- C++
helpviewer_keywords:
- C2190
ms.assetid: 34e15f85-d979-4948-80fc-46c414508a70
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d004d5a80e6907695f742faf6573c348662a479b
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2190"></a>컴파일러 오류 C2190
첫 번째 매개 변수 목록이 둘째 보다 깁니다.  
  
 C 함수를 한 번 더 짧은 매개 변수 목록 사용 하 여 선언 되었습니다. C에서 오버 로드 된 함수를 지원 하지 않습니다.  
  
 다음 샘플에서는 C2190 오류가 생성 됩니다.  
  
```  
// C2190.c  
// compile with: /Za /c  
void func( int, float );  
void func( int  );   // C2190, different parameter list  
void func2( int  );   // OK  
```
