---
title: "_pAtlModule | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATLBASE/_pAtlModule
- _pAtlModule
- ATL::_pAtlModule
- ATL._pAtlModule
dev_langs:
- C++
helpviewer_keywords:
- pAtlModule variable
- _pAtlModule variable
ms.assetid: 0ecde3a9-3f4d-4c7b-bb54-713ce05c4777
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
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
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: b20c5010616323eac9438223df64af9960192e2b
ms.lasthandoff: 02/24/2017

---
# <a name="patlmodule"></a>_pAtlModule
현재 모듈에 대 한 포인터를 저장 하는 전역 변수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
__declspec(selectany) CAtlModule* _pAtlModule  
```  
  
## <a name="remarks"></a>주의  
 기능을 제공 하려면이 전역 변수에 대 한 메서드를 사용할 수 있는 (이제 사용 되지 않음) 클래스 [CComModule](../../atl/reference/ccommodule-class.md) Visual c + + 6.0에서 제공 합니다.  
  
## <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing #&97;](../../atl/codesnippet/cpp/patlmodule_1.cpp)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
## <a name="see-also"></a>참고 항목  
 [전역 변수](../../atl/reference/atl-global-variables.md)




