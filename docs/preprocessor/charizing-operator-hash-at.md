---
title: Charizing 연산자 (#@) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#@'
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9e0c0d140d937b7359ff3abf9c0eae145a89210
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="charizing-operator-"></a>Charizing 연산자 (#@)
**Microsoft 전용**  
  
 charizing 연산자는 매크로의 인수에만 사용할 수 있습니다. 경우 **#@** 정식 매개 변수 앞에 오는 실제 인수 매크로 정의에서 단일 따옴표 안에 묶이고 문자로 취급 매크로 확장 합니다. 예를 들어:  
  
```  
#define makechar(x)  #@x  
```  
  
 위의 정의는 다음 문이  
  
```  
a = makechar(b);  
```  
  
 다음과 같이 확장되게 합니다.  
  
```  
a = 'b';  
```  
  
 작은따옴표는 charizing 연산자와 함께 사용할 수 없습니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [전처리기 연산자](../preprocessor/preprocessor-operators.md)