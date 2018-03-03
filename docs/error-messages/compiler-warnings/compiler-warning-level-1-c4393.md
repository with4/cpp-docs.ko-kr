---
title: "컴파일러 경고 (수준 1) C4393 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4393
dev_langs:
- C++
helpviewer_keywords:
- C4393
ms.assetid: 353a0539-d1ea-4c1b-8849-c9b321ec9842
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bfd5357ca15cc73f23040f66f89b0a5a41bb963a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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