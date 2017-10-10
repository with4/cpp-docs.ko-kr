---
title: "컴파일러 오류 C2213 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2213
dev_langs:
- C++
helpviewer_keywords:
- C2213
ms.assetid: ff012278-7f3b-4d49-aaed-2349756f6225
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: adfe94d1285ba0f237077820909ac955a5a65953
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2213"></a>컴파일러 오류 C2213
'modifier': __based에 대 한 인수가 잘못 되었습니다  
  
 인수 수정 `__based` 올바르지 않습니다.  
  
 다음 샘플에서는 C2213 오류가 생성 됩니다.  
  
```  
// C2213.cpp  
// compile with: /c  
int i;  
int *j;  
char __based(i) *p;   // C2213  
char __based(j) *p2;   // OK  
```
