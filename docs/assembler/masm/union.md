---
title: UNION | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- union
dev_langs:
- C++
helpviewer_keywords:
- UNION directive
ms.assetid: 52504abf-7dc1-47c5-944c-b886803a0c6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 71a2d7644e14903d2c4a9c4191ce54c8fea14849
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057671"
---
# <a name="union"></a>UNION
하나 이상의 데이터 형식의 공용 구조체가 선언합니다. *fielddeclarations* 유효한 데이터 정의 해야 합니다. 생략 된 [종료](../../assembler/masm/ends-masm.md) *이름* 레이블에 중첩 **UNION** 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      name   
      UNION [[alignment]] [[, NONUNIQUE]]  
   fielddeclarations  
[[name]] ENDS  
```  
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)