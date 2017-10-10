---
title: "컴파일러 오류 C2159 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2159
dev_langs:
- C++
helpviewer_keywords:
- C2159
ms.assetid: 925a2cbd-43c9-45ee-a373-84004350b380
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 06ca0380bbd55d40763fb0fd038de75a0b603842
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2159"></a>컴파일러 오류 C2159
저장소 클래스를 두 개 이상 지정했습니다.  
  
 선언에 저장소 클래스가 둘 이상 포함되어 있습니다.  
  
 다음 샘플에서는 C2159를 생성합니다.  
  
```  
// C2159.cpp  
// compile with: /c  
static int i;   // OK  
extern static int i;   // C2159  
```
