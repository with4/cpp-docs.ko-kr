---
title: _FREEENTRY, _USEDENTRY | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- USEDENTRY
- _USEDENTRY
- _FREEENTRY
- FREEENTRY
dev_langs: C++
helpviewer_keywords:
- _USEDENTRY constant
- _FREEENTRY constant
- FREEENTRY constant
- USEDENTRY constant
ms.assetid: 26f658e6-6846-4a4e-9984-262cfe392770
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 82f33c60ae5be642e29e588cdab27508b207d62a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="freeentry-usedentry"></a>_FREEENTRY, _USEDENTRY
## <a name="syntax"></a>구문  
  
```  
#include <malloc.h>  
```  
  
## <a name="remarks"></a>설명  
 이러한 상수는 `_heapwalk` 루틴에 의해 **_HEAPINFO** 구조체의 **_useflag** 요소에 할당된 값을 나타냅니다. 힙 항목의 상태를 나타냅니다.  
  
## <a name="see-also"></a>참고 항목  
 [_heapwalk](../c-runtime-library/reference/heapwalk.md)   
 [전역 상수](../c-runtime-library/global-constants.md)