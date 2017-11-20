---
title: "통신 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: COMM
dev_langs: C++
helpviewer_keywords: COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b8feb74f1da11fb6c4205ec1d8381f78789f684f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="comm"></a>COMM
에 지정 된 특성을 가진 공용 변수를 만듭니다 `definition`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
COMM definition [[, definition]] ...  
```  
  
## <a name="remarks"></a>설명  
 각 `definition` 형식은 다음과 같습니다.  
  
 [[*langtype*]] [[**NEAR** &#124; **원거리**]] *레이블***:**`type`[[**:***count*]]  
  
 *레이블* 변수의 이름입니다. `type` 형식 지정자를 사용할 수 있습니다 ([바이트](../../assembler/masm/byte-masm.md), [단어](../../assembler/masm/word.md)등) 또는 바이트 수를 지정 하는 정수입니다. *count* (하나는 기본값) 데이터 개체의 수를 지정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)