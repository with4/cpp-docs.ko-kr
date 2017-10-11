---
title: "컴파일러 오류 C3139 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3139
dev_langs:
- C++
helpviewer_keywords:
- C3139
ms.assetid: 95c92263-10ac-4ff3-b385-6312dd92adbc
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2982e615e2e99bfa64cb73a707af703f04d1ebf0
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3139"></a>컴파일러 오류 C3139
'struct': 멤버 없이 UDT를 내보낼 수 없습니다.  
  
 적용 하려고는 [내보내기](../../windows/export.md) 특성을 빈 UDT (사용자 정의 형식). 예:  
  
```  
// C3139.cpp  
#include "unknwn.h"  
[emitidl];  
[module(name=xx)];  
  
[export] struct MyStruct {   // C3139 empty type  
};  
int main(){}  
```
