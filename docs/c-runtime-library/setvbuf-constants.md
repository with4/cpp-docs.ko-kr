---
title: "setvbuf 상수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _IOFBF
- _IONBF
- _IOLBF
dev_langs:
- C++
helpviewer_keywords:
- _IOFBF constant
- IOFBF constant
- IONBF constant
- _IOLBF constant
- IOLBF constant
- _IONBF constant
ms.assetid: a6ec4dd5-1f24-498c-871a-e874cd28d33c
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 72597020534100f86de855db0095995e50d10f9b
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---
# <a name="setvbuf-constants"></a>setvbuf 상수
## <a name="syntax"></a>구문  
  
```  
  
#include <stdio.h>  
  
```  
  
## <a name="remarks"></a>설명  
 이러한 상수는 `setvbuf`에 대한 버퍼의 형식을 나타냅니다.  
  
 가능한 값은 다음 매니페스트 상수에 의해 제공됩니다.  
  
|상수|의미|  
|--------------|-------------|  
|`_IOFBF`|전체 버퍼링: `setvbuf` 호출에서 지정된 버퍼가 사용되고 크기는 `setvbuf` 호출에서 지정됩니다. 버퍼 포인터가 **NULL**이면 지정된 크기의 할당된 버퍼가 자동으로 사용됩니다.|  
|`_IOLBF`|`_IOFBF`와 동일합니다.|  
|`_IONBF`|`setvbuf` 호출 인수에 관계없이 버퍼는 사용되지 않습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [setbuf](../c-runtime-library/reference/setbuf.md)   
 [전역 상수](../c-runtime-library/global-constants.md)
