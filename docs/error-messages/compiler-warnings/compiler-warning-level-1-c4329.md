---
title: 컴파일러 경고 (수준 1) C4329 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4329
dev_langs:
- C++
helpviewer_keywords:
- C4329
ms.assetid: 4316f51a-2c56-4b3f-831e-65d24b83b65c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f7eca757f361acaa0aeaf90332d33400f5a0ba6d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33278007"
---
# <a name="compiler-warning-level-1-c4329"></a>컴파일러 경고(수준 1) C4329
__declspec(align())는 enum에서 무시 됩니다.  
  
 사용은 [맞춤](../../cpp/align-cpp.md) 의 키워드는 [__declspec](../../cpp/declspec.md) 에 한정자를 사용할 수는 `enum`합니다. 다음 샘플에서는 C4329 오류가 생성 됩니다.  
  
```  
// C4329.cpp  
// compile with: /W1 /LD  
enum __declspec(align(256)) TestEnum {   // C4329  
   TESTVAL1,  
   TESTVAL2,  
   TESTVAL3  
};  
__declspec(align(256)) enum TestEnum1;  
```