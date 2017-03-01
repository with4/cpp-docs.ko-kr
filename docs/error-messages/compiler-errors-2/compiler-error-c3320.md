---
title: "컴파일러 오류 C3320 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3320
dev_langs:
- C++
helpviewer_keywords:
- C3320
ms.assetid: 2ef72d9a-1f1d-4b2e-b244-9fd3f3e70cb6
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: 4b4acfe97e38cf13e336b7c58ffc868c69cf7a09
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3320"></a>컴파일러 오류 C3320
'type': 형식은 모듈의 'name' 속성과 같은 이름을 사용할 수 없습니다.  
  
에 전달 된 매개 변수는 내보낸된 사용자 정의 형식 (UDT), 구조체, 클래스, 열거형 또는 공용 구조체 수 있는 이름이 같은 가질 수 없습니다는 [모듈](../../windows/module-cpp.md) 특성의 name 속성입니다.  
  
## <a name="example"></a>예제  
다음 샘플에서는 C3320을 생성합니다.  
  
```cpp  
// C3320.cpp  
#include "unknwn.h"  
[module(name="xx")];  
  
[export] struct xx {   // C3320  
// Try the following line instead  
// [export] struct yy {  
   int i;  
};  
```
