---
title: 수학 오류 M6201 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6201
dev_langs:
- C++
helpviewer_keywords:
- M6201
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6a15e841cfc8daf1abdafc9997698807e7356af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332067"
---
# <a name="math-error-m6201"></a>수학 오류 M6201
'function': _DOMAIN 오류  
  
 지정된 된 함수에 인수로 해당 함수에 대 한 유효한 입력된 값의 도메인을 벗어났습니다.  
  
## <a name="example"></a>예제  
  
```  
result = sqrt(-1.0)   // C statement  
result = SQRT(-1.0)   !  FORTRAN statement  
```  
  
 호출 하는이 오류는 `_matherr` 함수 함수 이름, 인수 및 오류 유형을 포함 합니다. 다시 작성할 수 있습니다는 `_matherr` 특정 런타임 부동 소수점 수학 오류 처리 사용자 지정 하는 함수입니다.