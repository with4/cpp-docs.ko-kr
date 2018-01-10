---
title: "가정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ASSUME
dev_langs: C++
helpviewer_keywords: ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bf3e2bc4a29f1f6f2919e19085f73cde566aa5d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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