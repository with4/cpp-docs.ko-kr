---
title: 호출 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- Invoke
dev_langs:
- C++
helpviewer_keywords:
- INVOKE directive
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 27c18c83b623ce1a22ffcb5e1a9f1ce98ee6eb20
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="invoke"></a>INVOKE
프로시저를 호출 하 여 주어진 주소에서 *식*, 스택에 또는 언어 형식의 표준 호출 규칙에 따라 레지스터에 인수를 전달 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
INVOKE   
expression [[, arguments]]  
```  
  
## <a name="remarks"></a>설명  
 프로시저에 전달 하는 각 인수는 식, 레지스터 쌍 또는 주소 식 수 있습니다 (식 옵니다 `ADDR`).  
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)