---
title: IF (MASM) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: if
dev_langs: C++
helpviewer_keywords: IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b6ddb2c9d9ec6e39a0147d513fb452685d8e7213
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="if-masm"></a>IF (MASM)
어셈블리의 부여 *ifstatements* 경우 *expression1* 가 true (0이 아님) 또는 *elseifstatements* 경우 *expression1* 가 false (0) 및 *expression2* 그렇습니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
   IF expression1  
ifstatements  
[[ELSEIF expression2  
   elseifstatements]]  
[[ELSE  
   elsestatements]]  
ENDIF  
```  
  
## <a name="remarks"></a>설명  
 다음과 같은 지시문 대신 사용할 수 있습니다 [ELSEIF](../../assembler/masm/elseif-masm.md): **ELSEIFB**, **ELSEIFDEF**, **ELSEIFDIF**, **ELSEIFDIFI** , **ELSEIFE**, **ELSEIFIDN**, **ELSEIFIDNI**, **ELSEIFNB**, 및 **ELSEIFNDEF** . 필요에 따라 어셈블하고 *elsestatements* 이전 식이 false 이면 합니다. 참고 식은 어셈블리 시간에 평가 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)