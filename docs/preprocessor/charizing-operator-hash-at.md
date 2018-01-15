---
title: "Charizing 연산자 (#@) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: '#@'
dev_langs: C++
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 933e97732462b61919d9e5a1e73f2a72d26ea01b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="charizing-operator-"></a>Charizing 연산자 (#@)
**Microsoft 전용**  
  
 charizing 연산자는 매크로의 인수에만 사용할 수 있습니다. 경우  **#@**  정식 매개 변수 앞에 오는 실제 인수 매크로 정의에서 단일 따옴표 안에 묶이고 문자로 취급 매크로 확장 합니다. 예:  
  
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