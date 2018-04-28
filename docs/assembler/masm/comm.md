---
title: 통신 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- COMM
dev_langs:
- C++
helpviewer_keywords:
- COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 111dac47089fea13febe787e5b73557b287beea8
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="comm"></a>COMM
에 지정 된 특성을 가진 공용 변수를 만듭니다 `definition`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
COMM definition [[, definition]] ...  
```  
  
## <a name="remarks"></a>설명  
 각 `definition` 형식은 다음과 같습니다.  
  
 [[*langtype*]] [[**NEAR** &#124; **FAR**]] *label ***:**`type`[[**:*** count*]]  
  
 *레이블* 변수의 이름입니다. `type` 형식 지정자를 사용할 수 있습니다 ([바이트](../../assembler/masm/byte-masm.md), [단어](../../assembler/masm/word.md)등) 또는 바이트 수를 지정 하는 정수입니다. *count* (하나는 기본값) 데이터 개체의 수를 지정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)