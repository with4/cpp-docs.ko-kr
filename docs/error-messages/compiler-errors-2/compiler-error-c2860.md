---
title: "컴파일러 오류 C2860 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2860
dev_langs:
- C++
helpviewer_keywords:
- C2860
ms.assetid: ccc83553-90ed-4e94-b5e9-38b58ae38e31
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 53a5d08e6a6b9fbbd0aba9156bc85c4f2ef8dae0
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2860"></a>컴파일러 오류 C2860
'void', '(void)'를 제외한 인수 형식일 수 없습니다  
  
 형식 `void` 다른 인수를 포함 하는 인수 형식으로 사용할 수 없습니다.  
  
 다음 샘플에서는 C2860 오류가 생성 됩니다.  
  
```  
// C2860.cpp  
// compile with: /c  
void profunc1(void, int i);   // C2860  
void func10(void);   // OK  
```
