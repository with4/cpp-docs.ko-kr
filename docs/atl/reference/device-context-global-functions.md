---
title: "장치 컨텍스트 전역 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
caps.latest.revision: 17
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 8c71781519b965717acbcefab6fe6a183686caef
ms.lasthandoff: 02/24/2017

---
# <a name="device-context-global-functions"></a>장치 컨텍스트 전역 함수
이 함수는 지정된 된 장치에 대 한 장치 컨텍스트를 만듭니다.  
  
|||  
|-|-|  
|[AtlCreateTargetDC](#atlcreatetargetdc)|장치 컨텍스트를 만듭니다.|  
  
##  <a name="a-nameatlcreatetargetdca--atlcreatetargetdc"></a><a name="atlcreatetargetdc"></a>AtlCreateTargetDC  
 에 지정 된 장치에 대 한 장치 컨텍스트를 만듭니다는 [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) 구조입니다.  
  
```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```  
  
### <a name="parameters"></a>매개 변수  
 *hdc*  
 [in] 장치 컨텍스트에의 기존 핸들 또는 **NULL**합니다.  
  
 `ptd`  
 [in] 에 대 한 포인터는 **DVTARGETDEVICE** 대상 장치에 대 한 정보가 포함 된 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 에 지정 된 장치에 대 한 장치 컨텍스트를 핸들을 반환 합니다.는 **DVTARGETDEVICE**합니다. 장치는 지정 하는 경우 기본 디스플레이 장치에 핸들을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 구조가 **NULL** 및 *hdc* 는 **NULL**, 기본 디스플레이 장치에 대 한 장치 컨텍스트를 만듭니다.  
  
 경우 *hdc* 없는 **NULL** 및 `ptd` 는 **NULL**를 반환 하 고 기존 *hdc*합니다.  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  
   
## <a name="see-also"></a>참고 항목  
 [함수](../../atl/reference/atl-functions.md)

