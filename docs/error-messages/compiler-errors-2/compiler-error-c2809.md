---
title: 컴파일러 오류 C2809 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2809
dev_langs:
- C++
helpviewer_keywords:
- C2809
ms.assetid: ce796b8e-1a8c-4074-995d-1ad09afd0e93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 283dfdbc3c6c0168cf9a6bd4887fa4b5599dabf1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33237546"
---
# <a name="compiler-error-c2809"></a>컴파일러 오류 C2809
'operator 연산자'에 정식 매개 변수가 없음  
  
 연산자에 필요한 매개 변수를 없습니다.  
  
 다음 샘플에서는 C2809 오류가 생성 됩니다.  
  
```  
// C2809.cpp  
// compile with: /c  
class A{};  
int operator+ ();   // C2809  
int operator+ (A);   // OK  
```