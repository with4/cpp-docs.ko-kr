---
title: . IF | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .IF
dev_langs:
- C++
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ab0e2fc510b4be8c5a9a8c0c3d0fb1c4347f0b9
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
ms.locfileid: "32053118"
---
# <a name="if"></a>.IF
테스트 하는 코드를 생성 `condition1` (예를 들어 > 7 AX,)를 실행 하 고는 *문을* 해당 조건이 true 인 경우.  
  
## <a name="syntax"></a>구문  
  
```  
  
   .IF condition1   
statements  
[[.ELSEIF condition2   
   statements]]  
[[.ELSE  
   statements]]  
.ENDIF  
```  
  
## <a name="remarks"></a>설명  
 경우는 [합니다. 다른](../../assembler/masm/dot-else.md) 원래 상태로 되었으면 false 다음과, 해당 문이 실행 됩니다. 참고 조건이 런타임에 평가 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)