---
title: 컴파일러 오류 C2462 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2462
dev_langs:
- C++
helpviewer_keywords:
- C2462
ms.assetid: a8601bf8-f5ce-41de-9117-e2632bd4996b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e4ce82ed15bdb8844f69abc260446c1af2fd4a0f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198562"
---
# <a name="compiler-error-c2462"></a>컴파일러 오류 C2462
'identifier': ' new-expression '에서 형식을 정의할 수 없습니다  
  
 피연산자 필드에는 형식을 정의할 수 없습니다는 `new` 연산자입니다. 형식 정을 별도의 문으로 넣습니다.  
  
 다음 샘플에서는 C2462 오류가 생성 됩니다.  
  
```  
// C2462.cpp  
int main() {  
   new struct S { int i; };   // C2462  
}  
```