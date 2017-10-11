---
title: "컴파일러 오류 C2381 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2381
dev_langs:
- C++
helpviewer_keywords:
- C2381
ms.assetid: cc765f67-64ac-406f-93ef-ae7d548d58d7
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0442b94b1151dbee006a0d3ee71b1076d7afe7df
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

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
