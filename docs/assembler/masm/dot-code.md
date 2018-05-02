---
title: . 코드 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .CODE
dev_langs:
- C++
helpviewer_keywords:
- .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 59e376fc9c10ab8891b02e4da334341ae0534b73
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="code"></a>.CODE
와 함께 사용할 경우 [합니다. 모델](../../assembler/masm/dot-model.md), 코드 세그먼트의 시작을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
.CODE [[name]]  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`name`|코드 세그먼트의 이름을 지정 하는 선택적 매개 변수입니다. 기본 이름은 아주 작은, 작은 압축 및 플랫에 대 한 _TEXT [모델](../../assembler/masm/dot-model.md)합니다. 기본 이름은 *modulename*_TEXT 다른 모델에 대 한 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)   
 [.DATA](../../assembler/masm/dot-data.md)