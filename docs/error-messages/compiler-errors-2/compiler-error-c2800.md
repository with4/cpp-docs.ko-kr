---
title: 컴파일러 오류 C2800 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2800
dev_langs:
- C++
helpviewer_keywords:
- C2800
ms.assetid: a2f1a590-9fe6-44cb-ad09-b4505ef47c6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9dd9723513042ae7ef6d63914f5abecd63192e37
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33235599"
---
# <a name="compiler-error-c2800"></a>컴파일러 오류 C2800
'operator 연산자'를 오버 로드할 수 없습니다.  
  
 다음과 같은 연산자를 오버 로드할 수 없습니다: 클래스 멤버 액세스 (`.`), 멤버 포인터 (`.*`), 범위 결정 (`::`), 조건식 (`? :`), 및 `sizeof`합니다.  
  
 다음 샘플에서는 C2800 오류가 생성 됩니다.  
  
```  
// C2800.cpp  
// compile with: /c  
class C {  
   operator:: ();   // C2800  
};  
```