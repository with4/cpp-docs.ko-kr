---
title: 컴파일러 오류 C3168 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3168
dev_langs:
- C++
helpviewer_keywords:
- C3168
ms.assetid: 4c36fcfb-c351-48ff-b4eb-78d2aa1b4d55
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 83f0d6c6b35d863ee200798bd4c6a8bcd08d88ab
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33245240"
---
# <a name="compiler-error-c3168"></a>컴파일러 오류 C3168
'type': 열거형의 내부 형식이 잘못 되었습니다.  
  
에 대해 지정 된 내부 형식이 고 `enum` 형식이 잘못 되었습니다. 기본 형식이 c + + 정수 형식이 나 해당 CLR 형식 이어야 합니다.  
  
다음 샘플에서는 C3168 오류가 생성 됩니다.  
  
```  
// C3168.cpp  
// compile with: /clr /c  
ref class G{};  
  
enum class E : G { e };   // C3168  
enum class F { f };   // OK  
```  
