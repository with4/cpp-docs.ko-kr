---
title: 가정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- ASSUME
dev_langs:
- C++
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f8898895d2e107e522fe88dc954146d64e6f62b9
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
ms.locfileid: "32050638"
---
# <a name="assume"></a>ASSUME
오류 레지스터 값에 대 한 검사를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
ASSUME segregister:name [[, segregister:name]]...  
ASSUME dataregister:type [[, dataregister:type]]...  
ASSUME register:ERROR [[, register:ERROR]]...  
ASSUME [[register:]] NOTHING [[, register:NOTHING]]...  
```  
  
## <a name="remarks"></a>설명  
 이후에 `ASSUME` 어셈블러에는 지정 된 레지스터의 값에 변경 내용을 감시 효과에 배치 됩니다. **오류** 는 레지스터를 사용 하는 경우 오류를 생성 합니다. **아무것도** 제거 오류 검사를 등록 합니다. 다양 한 가정 하나의 문에서 결합할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)