---
title: "매크로 대체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, macro substitution
- macros, NMAKE
- substitution macros in NMAKE
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7c2ea7a2509e58cfd4da163cc76c018d06c244fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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