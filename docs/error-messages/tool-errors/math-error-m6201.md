---
title: "수학 오류 M6201 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- M6201
dev_langs:
- C++
helpviewer_keywords:
- M6201
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 17de7fab7b41a5a8acc2fed2f3c8185f66aadd9c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="math-error-m6201"></a>수학 오류 M6201
'function': _DOMAIN 오류  
  
 지정된 된 함수에 인수로 해당 함수에 대 한 유효한 입력된 값의 도메인을 벗어났습니다.  
  
## <a name="example"></a>예  
  
```  
result = sqrt(-1.0)   // C statement  
result = SQRT(-1.0)   !  FORTRAN statement  
```  
  
 호출 하는이 오류는 `_matherr` 함수 함수 이름, 인수 및 오류 유형을 포함 합니다. 다시 작성할 수 있습니다는 `_matherr` 특정 런타임 부동 소수점 수학 오류 처리 사용자 지정 하는 함수입니다.