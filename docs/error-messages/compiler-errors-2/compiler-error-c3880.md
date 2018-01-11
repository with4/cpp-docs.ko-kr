---
title: "컴파일러 오류 C3880 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3880
dev_langs: C++
helpviewer_keywords: C3880
ms.assetid: b0e05d1e-32d0-4034-9246-f37d23573ea9
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1a1aba2a8cc76e1f47650b4a4fd4c47e95e98d2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3880"></a>컴파일러 오류 C3880
'var': 리터럴 데이터 멤버가 될 수 없습니다  
  
 유형의 [리터럴](../../windows/literal-cpp-component-extensions.md) 특성 이어야 합니다 또는 컴파일 타임 다음 유형 중 하나로 변환할:  
  
-   정수 계열 형식  
  
-   string  
  
-   정수 계열 또는 기본 유형의 열거형  
  
 다음 샘플에서는 C3880 오류가 생성 됩니다.  
  
```  
// C3880.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   literal System::Decimal staticConst1 = 10;   // C3880  
   literal int staticConst2 = 10;   // OK  
};  
```