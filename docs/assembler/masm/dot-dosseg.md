---
title: . DOSSEG | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .DOSSEG
dev_langs:
- C++
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3817cfe98758faf86ea87d74e02657598c3e806b
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="dosseg"></a>.DOSSEG
MS-DOS 세그먼트 규칙에 따라 세그먼트를 정렬: 먼저 DGROUP에 없는 다음 세그먼트를 다음 DGROUP 세그먼트가 코드입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
.DOSSEG  
  
```  
  
## <a name="remarks"></a>설명  
 세그먼트 DGROUP에이 순서를 따릅니다: BSS, 스택, 세그먼트 BSS 세그먼트 및 스택 세그먼트입니다. CodeView 지원 MASM 독립 실행형 프로그램에서을 위한 주로 사용 됩니다. 와 동일 [DOSSEG](../../assembler/masm/dosseg.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)