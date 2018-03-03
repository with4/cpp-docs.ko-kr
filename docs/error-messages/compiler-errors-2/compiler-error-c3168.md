---
title: "컴파일러 오류 C3168 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3168
dev_langs:
- C++
helpviewer_keywords:
- C3168
ms.assetid: 4c36fcfb-c351-48ff-b4eb-78d2aa1b4d55
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c96c94c15e586b98f236fb7731529cbca7087396
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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
