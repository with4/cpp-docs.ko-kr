---
title: EXTERN (MASM) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- extern
dev_langs:
- C++
helpviewer_keywords:
- EXTERN directive
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7528ea78270e4976ed3b926e83fe4f9977148498
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="extern-masm"></a>EXTERN (MASM)
하나 이상의 외부 변수, 레이블 또는 이라는 기호 정의 *이름* 형식이 변수인 `type`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
   EXTERN [[langtype]] name [[(altid)]] :  
type [[, [[langtype]] name [[(altid)]] :type]]...  
```  
  
## <a name="remarks"></a>설명  
 `type` 수 [ABS](../../assembler/masm/operator-abs.md)를 가져오는 *이름* 상수입니다. 와 동일 [EXTRN](../../assembler/masm/extrn.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)