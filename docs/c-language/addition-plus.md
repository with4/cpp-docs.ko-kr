---
title: "더하기(+) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- pointers, adding integers
ms.assetid: b9014fee-825d-46ef-91db-5d46807081fc
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: a3e1560730f95fb3ca222f460a9da0490a609190
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="addition-"></a>더하기(+)
더하기 연산자(**+**)는 두 피연산자를 더합니다. 두 피연산자 모두 정수 계열 또는 부동 형식이 되거나 하나는 포인터가 되고 다른 하나는 정수가 될 수 있습니다.  
  
 정수를 포인터에 더하는 경우 정수 값(*i*)은 포인터가 가리키는 값의 크기를 곱하여 변환됩니다. 변환 후 정수 값은 *i* 메모리 위치를 나타내며 각 위치의 길이는 포인터 형식으로 지정됩니다. 변환된 정수 값을 포인터 값에 더하면 그 결과는 원래 주소에서 *i* 위치만큼 떨어진 주소를 나타내는 새로운 포인터 값입니다. 새로운 포인터 값은 원래 포인터 값과 같은 형식의 값을 가리키므로 배열 인덱싱과 동일합니다([1차원 배열](../c-language/one-dimensional-arrays.md) 및 [다차원 배열](../c-language/multidimensional-arrays-c.md) 참조). 합계 포인터가 배열 외부(위쪽 끝을 벗어난 첫 번째 위치 제외)를 가리키는 경우 결과가 정의되지 않습니다. 자세한 내용은 [포인터 산술](../c-language/pointer-arithmetic.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [C 가감 연산자](../c-language/c-additive-operators.md)
