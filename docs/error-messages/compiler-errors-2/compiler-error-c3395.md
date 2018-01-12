---
title: "컴파일러 오류 C3395 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3395
dev_langs: C++
helpviewer_keywords: C3395
ms.assetid: 26a9ebc9-ed97-47ce-b436-19aa2bcf6e50
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4d937766291b32850c32b87c1405aa5ea0b71956
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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