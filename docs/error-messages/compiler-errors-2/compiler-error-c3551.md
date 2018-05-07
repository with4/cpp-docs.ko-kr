---
title: 컴파일러 오류 C3551 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3551
dev_langs:
- C++
helpviewer_keywords:
- C3551
ms.assetid: c8ee23da-6568-40db-93a6-3ddb7ac47712
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f9f69adcf071415d3c1760294bdaaaec7b71f8e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3551"></a>컴파일러 오류 C3551
"런타임에 지정된 반환 형식이 필요합니다."  
  
 `auto` 키워드를 함수 반환 형식에 대한 자리 표시자로 사용하는 경우 컴파일하면 지정되는 반환 형식을 제공해야 합니다. 다음 예제에서는 런타임에 지정된 `myFunction` 함수의 반환 형식이 `int`형식의 네 요소 배열에 대한 포인터입니다.  
  
```  
auto myFunction()->int(*)[4];   
```  
  
## <a name="see-also"></a>참고 항목  
 [auto](../../cpp/auto-cpp.md)