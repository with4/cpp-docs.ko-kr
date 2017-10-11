---
title: "컴파일러 오류 C3395 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3395
dev_langs:
- C++
helpviewer_keywords:
- C3395
ms.assetid: 26a9ebc9-ed97-47ce-b436-19aa2bcf6e50
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 93009d77c40535997ecc42ccb715f5fe81d79798
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3395"></a>컴파일러 오류 C3395
'function': __declspec (dllexport)를 사용 하는 함수에 적용할 수 없습니다는 \__clrcall 호출 규칙  
  
 `__declspec(dllexport)`및 [__clrcall](../../cpp/clrcall.md) 호환 되지 않습니다.  자세한 내용은 참조 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)합니다.  
  
 다음 샘플에서는 C3395 오류가 생성 됩니다.  
  
```  
// C3395.cpp  
// compile with: /clr /c  
  
__declspec(dllexport) void __clrcall Test(){}   // C3395  
void __clrcall Test2(){}   // OK  
__declspec(dllexport) void Test3(){}   // OK  
```
