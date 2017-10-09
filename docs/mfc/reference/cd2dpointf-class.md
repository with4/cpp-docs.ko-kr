---
title: "CD2DPointF 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DPointF
- AFXRENDERTARGET/CD2DPointF
- AFXRENDERTARGET/CD2DPointF::CD2DPointF
dev_langs:
- C++
helpviewer_keywords:
- CD2DPointF [MFC], CD2DPointF
ms.assetid: 30f72083-1c8a-4f50-adb2-72dbbe3522d4
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 98435819aeb0e173074a4794939bee10b00b3233
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="cd2dpointf-class"></a>CD2DPointF 클래스
`D2D1_POINT_2F`의 래퍼입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CD2DPointF : public D2D1_POINT_2F;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DPointF::CD2DPointF](#cd2dpointf)|오버로드됨. 생성 된 `CD2DPointF` 에서 개체 `D2D1_POINT_2F` 개체입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DPointF::operator CPoint](#operator_cpoint)|변환 `CD2DPointF` 를 `CPoint` 개체입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `D2D1_POINT_2F`  
  
 `CD2DPointF`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxrendertarget.h  
  
##  <a name="cd2dpointf"></a>CD2DPointF::CD2DPointF  
 CPoint 개체에서 CD2DPointF 개체를 만듭니다.  
  
```  
CD2DPointF(const CPoint& pt);    
CD2DPointF(const D2D1_POINT_2F& pt);    
CD2DPointF(const D2D1_POINT_2F* pt); 
CD2DPointF(FLOAT fX = 0., FLOAT fY = 0.);
```  
  
### <a name="parameters"></a>매개 변수  
 `pt`  
 원본 지점  
  
 `fX`  
 소스 X  
  
 `fY`  
 소스 Y  
  
##  <a name="operator_cpoint"></a>CD2DPointF::operator CPoint  
 CD2DPointF CPoint 개체로 변환합니다.  
  
```  
operator CPoint();
```   
  
### <a name="return-value"></a>반환 값  
 D2D 포인트의 현재 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)

