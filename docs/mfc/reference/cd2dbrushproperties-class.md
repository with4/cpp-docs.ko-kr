---
title: CD2DBrushProperties 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CommonInit
dev_langs:
- C++
helpviewer_keywords:
- CD2DBrushProperties [MFC], CD2DBrushProperties
- CD2DBrushProperties [MFC], CommonInit
ms.assetid: c77d717f-0a16-4d74-b2ce-0ae1766ed6f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 897be7063385566f2fd0e717eba0f89b335c2c48
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950415"
---
# <a name="cd2dbrushproperties-class"></a>CD2DBrushProperties 클래스
`D2D1_BRUSH_PROPERTIES`의 래퍼입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CD2DBrushProperties : public D2D1_BRUSH_PROPERTIES;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DBrushProperties::CD2DBrushProperties](#cd2dbrushproperties)|오버로드됨. 만듭니다는 `CD2D_BRUSH_PROPERTIES` 구조|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DBrushProperties::CommonInit](#commoninit)|개체를 초기화합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `D2D1_BRUSH_PROPERTIES`  
  
 `CD2DBrushProperties`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxrendertarget.h  
  
##  <a name="cd2dbrushproperties"></a>  CD2DBrushProperties::CD2DBrushProperties  
 CD2D_BRUSH_PROPERTIES 구조를 만듭니다.  
  
```  
CD2DBrushProperties();  
CD2DBrushProperties(FLOAT _opacity);

 
CD2DBrushProperties(
    D2D1_MATRIX_3X2_F _transform,  
    FLOAT _opacity = 1.);
```  
  
### <a name="parameters"></a>매개 변수  
 *_opacity*  
 기본 불투명도 브러시입니다. 기본값은 1.0입니다.  
  
 *_transform*  
 브러시에 적용할 변환  
  
##  <a name="commoninit"></a>  CD2DBrushProperties::CommonInit  
 개체를 초기화합니다.  
  
```  
void CommonInit();
```  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)
