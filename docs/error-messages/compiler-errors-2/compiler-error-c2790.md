---
title: "컴파일러 오류 C2790 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2790
dev_langs:
- C++
helpviewer_keywords:
- C2790
ms.assetid: 38d4fce1-ba00-413d-8bc1-e8aa43d7bc1f
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 11ea7285d20808f16f2588d50caebe99429c8da0
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2790"></a>컴파일러 오류 C2790
'super':이 키워드는 클래스 멤버 함수의 본문 내 에서만 사용할 수 있습니다  
  
 이 오류 메시지가 표시 된 키워드를 사용 하 여 사용자가 하려고 할 경우 [super](../../cpp/super.md) 컨텍스트 외부에서 멤버 함수입니다.  
  
 다음 샘플에서는 C2790 오류가 생성 됩니다.  
  
```  
// C2790.cpp  
void f() {  
   __super::g();   // C2790  
}  
```
