---
title: 매크로 대체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, macro substitution
- macros, NMAKE
- substitution macros in NMAKE
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4028ee710cf38b6a4ef929de9a7e4ffad95f3e41
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368072"
---
# <a name="macro-substitution"></a>매크로 대체
때 *매크로 이름* 가 호출의 각 항목 *string1* 으로 대체 하는 문자열의 정의에 *string2*합니다.  
  
## <a name="syntax"></a>구문  
  
```  
$(macroname:string1=string2)  
```  
  
## <a name="remarks"></a>설명  
 매크로 대체 대/소문자 구분 되며 리터럴; *string1* 및 *string2* 매크로 호출할 수 없습니다. 대체는 원래 정의 수정 하지 않습니다. 제외한 모든 미리 정의 된 매크로의 텍스트를 대체할 수 [ $$@ ](../build/filename-macros.md)합니다.  
  
 O n; 앞에 공백 또는 탭 콜론 after 리터럴로 해석 됩니다. 경우 *string2* 가 null 이면의 항목을 모두 *string1* 매크로 정의 문자열에서 삭제 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [NMAKE 매크로 사용](../build/using-an-nmake-macro.md)