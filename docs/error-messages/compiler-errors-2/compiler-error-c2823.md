---
title: 컴파일러 오류 C2823 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2823
dev_langs:
- C++
helpviewer_keywords:
- C2823
ms.assetid: 982b1b35-1a7c-456e-b711-f80cfe2d571e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ad7336834d38f7236b88debc28035d8f7d68e88
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2823"></a>컴파일러 오류 C2823  
  
> typedef 템플릿이 잘못 되었습니다.  
  
서식 파일에서 허용 되지 않는 `typedef` 정의 합니다.  
  
## <a name="example"></a>예제  
  
다음 샘플에서는 C2823, 경고가 발생 하 고를 해결 하는 방법을 보여 줍니다.  
  
```cpp  
// C2823.cpp  
template<class T>  
typedef struct x {  
   T i;   // C2823 can't use T, specify data type and delete template  
   int i;   // OK  
} x1;  
```