---
title: 컴파일러 오류 C2770 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2770
dev_langs:
- C++
helpviewer_keywords:
- C2770
ms.assetid: 100001b5-80b0-4971-8ff6-9023f443c926
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c54ae3c559d0a523bc25831fa71e37531295489
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2770"></a>컴파일러 오류 C2770
'template'에 대 한 잘못 된 명시적 template_or_generic 인수  
  
 함수 템플릿 후보 명시적 템플릿 또는 제네릭 인수를 허용 되지 않는 함수 형식 발생 했습니다.  
  
 다음 샘플에서는 C2770 오류가 생성 됩니다.  
  
```  
// C2770.cpp  
#include <stdio.h>  
template <class T>  
int f(typename T::B*);   // expects type with member B  
  
struct Err {};  
  
int main() {  
   f<int>(0);   // C2770 int has no B  
   // try the following line instead  
   f<OK>(0);  
}  
```