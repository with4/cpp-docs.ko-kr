---
title: "픽셀 HIMETRIC 변환 전역 함수 | Microsoft 문서"
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
ms.assetid: ecb1b1b2-7e9d-4fbc-a855-16252d2d794c
caps.latest.revision: 19
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: efb7e7da896aea4e377225f4c1e2c9948e635705
ms.lasthandoff: 02/24/2017

---
# <a name="pixelhimetric-conversion-global-functions"></a>픽셀/HIMETRIC 변환 전역 함수
이러한 함수가 사이의 픽셀 및 HIMETRIC 단위 변환에 대 한 지원을 제공 합니다.  
  
> [!IMPORTANT]
>  다음 표에 나열 된 함수에서 실행 되는 응용 프로그램에서 사용할 수 없습니다는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]합니다.  
  
|||  
|-|-|  
|[AtlHiMetricToPixel](#atlhimetrictopixel)|(각 단위는 0.01 m m) HIMETRIC 단위 픽셀로 변환 합니다.|  
|[AtlPixelToHiMetric](#atlpixeltohimetric)|픽셀 HIMETRIC 단위 변환 (각 단위는 0.01 m m).|  
  
##  <a name="a-nameatlhimetrictopixela--atlhimetrictopixel"></a><a name="atlhimetrictopixel"></a>AtlHiMetricToPixel  
 개체의 HIMETRIC 단위 크기(각 단위는 0.01mm)를 화면 장치의 픽셀 크기로 변환합니다.  
  
 
```
extern void AtlHiMetricToPixel(
  const SIZEL* lpSizeInHiMetric, 
  LPSIZEL lpSizeInPix);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpSizeInHiMetric`  
 [in] 개체의 HIMETRIC 단위 크기에 대 한 포인터입니다.  
  
 `lpSizeInPix`  
 [out] 개체의 크기 (픽셀)이 반환 될 위치에 대 한 포인터입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[#49 NVC_ATL_COM](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_1.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  
  
##  <a name="a-nameatlpixeltohimetrica--atlpixeltohimetric"></a><a name="atlpixeltohimetric"></a>AtlPixelToHiMetric  
 화면 장치에서 개체의 픽셀 크기를 HIMETRIC 단위의 크기(각 단위는 0.01mm)로 변환합니다.  
  
```
extern void AtlPixelToHiMetric(
    const SIZEL* lpSizeInPix, 
    LPSIZEL lpSizeInHiMetric);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpSizeInPix`  
 [in] 개체의 크기 (픽셀 단위)에 대 한 포인터입니다.  
  
 `lpSizeInHiMetric`  
 [out] 개체의 HIMETRIC 단위 크기는 반환 될 위치에 대 한 포인터입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_COM&#51;](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_2.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  

## <a name="see-also"></a>참고 항목  
 [함수](../../atl/reference/atl-functions.md)

