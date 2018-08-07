---
title: 컴파일러 오류 C2381 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2381
dev_langs:
- C++
helpviewer_keywords:
- C2381
ms.assetid: cc765f67-64ac-406f-93ef-ae7d548d58d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7bd5f5edcf95144333524c41b803c24b728a621f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33225279"
---
# <a name="compiler-error-c2381"></a>컴파일러 오류 C2381
'function': 재정의. __declspec (noreturn)와 다른  
  
 함수를 선언 하 고 사용 되는 정의 제외한 다음 정의 [noreturn](../../cpp/noreturn.md) `__declspec` 한정자입니다. 사용 `noreturn` 함수의 재정의 선언 및 정의의 사용에 동의 해야 합니다. `noreturn`합니다.  
  
 다음 샘플에서는 C2381 오류가 생성 됩니다.  
  
```  
// C2381.cpp  
// compile with: /c  
void f1();  
void __declspec(noreturn) f1() {}   // C2381  
void __declspec(noreturn) f2() {}   // OK  
```