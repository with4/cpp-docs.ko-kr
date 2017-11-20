---
title: "가감 연산자 사용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- operators [C++], addition
- additive operators
ms.assetid: 7d54841e-436d-4ae8-9865-1ac1829e6f22
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9f2bdbc6a22754587dce3cb2a4c9b2baf12a1a1f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="using-the-additive-operators"></a>가감 연산자 사용
더하기 및 빼기 연산자를 보여 주는 다음 예제는 이러한 선언을 사용합니다.  
  
```  
int i = 4, j;  
float x[10];  
float *px;  
```  
  
 이 문은 다음에 해당합니다.  
  
```  
px = &x[4 + i];  
px = &x[4] + i;    
```  
  
 값 `i`는 **float**의 길이로 곱해지고 `&x[4]`에 더해집니다. 결과 포인터 값은 `x[8]`의 주소입니다.  
  
```  
j = &x[i] - &x[i-2];  
```  
  
 이 예제에서는 `x`의 세 번째 요소의 주소(`x[i-2]`에서 지정)가 `x`의 다섯 번째 요소의 주소(`x[i]`에서 지정)에서 차감됩니다. 차이는 **float**의 길이로 나눠지며 결과는 정수 값 2입니다.  
  
## <a name="see-also"></a>참고 항목  
 [C 가감 연산자](../c-language/c-additive-operators.md)