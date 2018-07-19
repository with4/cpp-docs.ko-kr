---
title: 컴파일러 경고 (수준 1) C4393 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4393
dev_langs:
- C++
helpviewer_keywords:
- C4393
ms.assetid: 353a0539-d1ea-4c1b-8849-c9b321ec9842
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 59a1022f54d22e97a11c0970cad6bcd8918c7190
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277942"
---
# <a name="compiler-warning-level-1-c4393"></a>컴파일러 경고(수준 1) C4393
'var': const; 리터럴 데이터 멤버에 영향을 주지 무시  
  
 A [리터럴](../../windows/literal-cpp-component-extensions.md) 데이터 멤버를 const로 지정 합니다.  리터럴 데이터 멤버를 const 함축 이후 필요가 없습니다 추가할에 상수를 선언 합니다.  
  
 다음 샘플에서는 C4393 오류가 생성 됩니다.  
  
```  
// C4393.cpp  
// compile with: /clr /W1 /c  
ref struct Y1 {  
   literal const int staticConst = 10;   // C4393  
   literal int staticConst2 = 10;   // OK  
};  
```