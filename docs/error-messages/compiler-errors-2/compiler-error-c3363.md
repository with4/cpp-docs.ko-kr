---
title: 컴파일러 오류 C3363 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3363
dev_langs:
- C++
helpviewer_keywords:
- C3363
ms.assetid: 41aa922f-608e-4f7a-ba66-451fc1161935
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aec09769f4db4f501f62ebaa2a996dfdefb5fcd6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3363"></a>컴파일러 오류 C3363
'type': 'typeid'는 형식에만 적용될 수 있습니다.  
  
 [typeid](../../windows/typeid-cpp-component-extensions.md) 연산자를 잘못 사용했습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3363을 생성합니다.  
  
```  
// C3363.cpp  
// compile with: /clr  
int main() {  
   System::typeid;   // C3363  
}  
```