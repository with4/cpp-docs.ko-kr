---
title: EXTERNDEF | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: EXTERNDEF
dev_langs: C++
helpviewer_keywords: EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a06378b7cf1217c01f57d7994220bfe5dd585a66
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="externdef"></a>EXTERNDEF
하나 이상의 외부 변수, 레이블 또는 이라는 기호 정의 *이름* 형식이 변수인 `type`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
EXTERNDEF [[langtype]] name:type [[, [[langtype]] name:type]]...  
```  
  
## <a name="remarks"></a>설명  
 경우 *이름* 정의로 처리 되는 모듈 [공용](../../assembler/masm/public-masm.md)합니다. 경우 *이름* 참조로 처리 되는 모듈 [EXTERN](../../assembler/masm/extern-masm.md)합니다. 경우 *이름* 가 참조 되지 않으면는 무시 됩니다. `type` 수 [ABS](../../assembler/masm/operator-abs.md)를 가져오는 *이름* 상수입니다. 일반적으로 사용 되는에서 파일을 포함 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)