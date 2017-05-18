---
title: "CD2DPointU 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DPointU
- AFXRENDERTARGET/CD2DPointU
- AFXRENDERTARGET/CD2DPointU::CD2DPointU
dev_langs:
- C++
helpviewer_keywords:
- CD2DPointU class
ms.assetid: 04733f96-b6de-4a89-82e3-caad1e8087a9
caps.latest.revision: 18
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 605415ad5a2739d8f8ac3a6a47c562796d55a813
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dpointu-class"></a>CD2DPointU 클래스
`D2D1_POINT_2U`의 래퍼입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CD2DPointU : public D2D1_POINT_2U;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DPointU::CD2DPointU](#cd2dpointu)|오버로드됨. 생성 된 `CD2DPointU` 개체에서 `D2D1_POINT_2U` 개체입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DPointU::operator CPoint](#operator_cpoint)|변환 `CD2DPointU` 를 `CPoint` 개체입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `D2D1_POINT_2U`  
  
 `CD2DPointU`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxrendertarget.h  
  
##  <a name="cd2dpointu"></a>CD2DPointU::CD2DPointU  
 CPoint 개체에서 CD2DPointU 개체를 만듭니다.  
  
```  
CD2DPointU(const CPoint& pt);  
CD2DPointU(const D2D1_POINT_2U& pt);  
  CD2DPointU(const D2D1_POINT_2U* pt);  
CD2DPointU(UINT32 uX = 0, UINT32 uY = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `pt`  
 원본 지점  
  
 `uX`  
 소스 X  
  
 `uY`  
 소스 Y  
  
##  <a name="operator_cpoint"></a>CD2DPointU::operator CPoint  
 CD2DPointU CPoint 개체로 변환합니다.  
  
```  
operator CPoint();
```   
  
### <a name="return-value"></a>반환 값  
 D2D 포인트의 현재 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)

