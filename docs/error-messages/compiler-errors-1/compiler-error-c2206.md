---
title: 컴파일러 오류 C2206 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2206
dev_langs:
- C++
helpviewer_keywords:
- C2206
ms.assetid: d7fba68b-aa28-4885-a9a0-27107358f066
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 93058e5a7a4bd4fadfbfc1830ea6e2840618463c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2206"></a>컴파일러 오류 C2206
'function': 형식 정의는 함수 정의에 사용할 수 없습니다.  
  
 `typedef` 가 함수 형식을 정의하는 데 사용됩니다.  
  
 다음 샘플에서는 C2206을 생성합니다.  
  
```  
// C2206.cpp  
typedef int functyp();  
typedef int MyInt;  
functyp func1 {};   // C2206  
int main() {  
   MyInt i = 0;   // OK  
}  
```