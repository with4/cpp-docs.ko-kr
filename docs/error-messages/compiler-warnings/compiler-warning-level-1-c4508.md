---
title: 컴파일러 경고 (수준 1) C4508 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4508
dev_langs:
- C++
helpviewer_keywords:
- C4508
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 53f152c2f3573e5f3bd7b8e9be0603ed6d3f11bb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283198"
---
# <a name="compiler-warning-level-1-c4508"></a>컴파일러 경고(수준 1) C4508
'function':; 값을 반환 해야 하는 함수 'void' 반환 형식으로 간주 됩니다.  
  
 함수는 지정 된 반환 형식이 없습니다. 이 경우 C4430도 발생 하 고 컴파일러 구현 C4430 (기본값은 int)에서 보고 된 문제를 해결 합니다.  
  
 이 경고를 해결 하려면 함수의 반환 형식을 명시적으로 선언 합니다.  
  
 다음 샘플에서는 C4508 오류가 생성 됩니다.  
  
```  
// C4508.cpp  
// compile with: /W1 /c  
#pragma warning (disable : 4430)  
func() {}   // C4508  
void func2() {}   // OK  
```