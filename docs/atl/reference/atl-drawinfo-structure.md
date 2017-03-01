---
title: "ATL_DRAWINFO 구조 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::ATL_DRAWINFO
- ATL_DRAWINFO
- ATL.ATL_DRAWINFO
dev_langs:
- C++
helpviewer_keywords:
- ATL_DRAWINFO structure
ms.assetid: dd2e2aa8-e8c5-403b-b4df-35c0f6f57fb7
caps.latest.revision: 16
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: bc124de97acf85d6e706605afb55b0747a327ade
ms.lasthandoff: 02/24/2017

---
# <a name="atldrawinfo-structure"></a>ATL_DRAWINFO 구조
ActiveX 컨트롤, 메타 파일, 프린터 등의 다양 한 대상에 렌더링에 사용 되는 정보를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```
struct ATL_DRAWINFO {
    UINT cbSize;
    DWORD dwDrawAspect;
    LONG lindex;
    DVTARGETDEVICE* ptd;
    HDC hicTargetDev;
    HDC hdcDraw;
    LPCRECTL prcBounds;
    LPCRECTL prcWBounds;
    BOOL bOptimize;
    BOOL bZoomed;
    BOOL bRectInHimetric;
    SIZEL ZoomNum;
    SIZEL ZoomDen;
};
```  
  
## <a name="members"></a>멤버  
 `cbSize`  
 크기 (바이트)에서 구조입니다.  
  
 **dwDrawAspect**  
 대상을 표현할 방법을 지정 합니다. 표현은 콘텐츠, 아이콘, 미리 보기를 또는 인쇄 된 문서에 포함할 수 있습니다. 가능한 값 목록은 참조 하십시오. [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) 및 [DVASPECT2](http://msdn.microsoft.com/library/windows/desktop/ms688644)합니다.  
  
 **색인입니다.**  
 그리기 작업에 대 한 관심 있는 대상의 일부입니다. 값에 따라 해석이 달라는 **dwDrawAspect** 멤버입니다.  
  
 **데**  
 에 대 한 포인터는 [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) 지정 된 모양에 따른 그리기 최적화를 가능 하는 구조입니다. 참고 새 개체 및 최적화 된 드로잉 인터페이스를 지 원하는 컨테이너 에서도이 멤버를 지원 합니다. 이전 개체 및 컨테이너 항상 최적화 된 드로잉 인터페이스 지원 하지 않는 지정 **NULL** 이 멤버에 대 한 합니다.  
  
 **hicTargetDev**  
 가리키는 대상 장치에 대 한 정보 컨텍스트입니다 **데** 개체 수 장치 메트릭을 추출 하 고 있는 장치 기능을 테스트 합니다. 경우 **데** 는 **NULL**, 해당 개체의 값을 무시 해야는 **hicTargetDev** 멤버입니다.  
  
 **hdcDraw**  
 그릴 장치 컨텍스트입니다. 창 없는 개체는 **hdcDraw** 멤버에는 `MM_TEXT` 윈도우의 클라이언트 좌표와 일치 하는 논리적 좌표를 사용 하 여 매핑 모드입니다. 장치 컨텍스트 일반적으로 전달 하는 것과 동일한 상태 여야 합니다 또한는 `WM_PAINT` 메시지입니다.  
  
 **prcBounds**  
 에 대 한 포인터는 [RECTL](http://msdn.microsoft.com/library/windows/desktop/dd162907) 에 사각형을 지정 하는 구조 **hdcDraw** 및 개체를 그립니다. 이 멤버는 위치 및 개체의 늘이기를 제어 합니다. 이 멤버에 해야 **NULL** 창 없는 위치에서 현재 개체를 그리는 합니다. 다른 모든 상황에서 **NULL** 유효한 값 아니며을 유발는 `E_INVALIDARG` 오류 코드입니다. 컨테이너를 통과 이외의**NULL** 창 없는 개체를 개체에 값에 지정 된 장치 컨텍스트와 사각형 요청한 측면을 렌더링 해야 합니다. 컨테이너 개체의 두 번째, 비활성 뷰를 렌더링 하거나 개체를 인쇄 합니다. 창 없는 개체에서이 요청할 수 있습니다.  
  
 **prcWBounds**  
 경우 **hdcDraw** 메타 파일 장치 컨텍스트는 (참조 [GetDeviceCaps](http://msdn.microsoft.com/library/windows/desktop/dd144877) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]),이에 대 한 포인터는 **RECTL** 내부 메타 파일에는 경계 사각형을 지정 하는 구조입니다. 창 크기와 창 원점이 사각형 구조에 포함 되어 있습니다. 이러한 값은 메타 파일 그리기에 유용 합니다. 로 표시 된 사각형 **prcBounds** 이 안에 중첩 된 **prcWBounds** 사각형; 동일한 좌표 공간에서.  
  
 **bOptimize**  
 이 속성을 0이 아닌 경우 컨트롤의 그리기를 최적화, 그렇지 않으면 0입니다. 완료 했으면 장치 컨텍스트의 상태에 자동으로 복원 그리기를 최적화 하면 렌더링 합니다.  
  
 **bZoomed**  
 이 속성을 0이 아닌 대상에 확대/축소 비율, 그렇지 않으면 0입니다. 확대/축소 비율에 저장 된 **ZoomNum**합니다.  
  
 **bRectInHimetric**  
 0이 아닌 값의 크기 **prcBounds** 에 **HIMETRIC**, 그렇지 않으면 0입니다.  
  
 **ZoomNum**  
 개체는 렌더링 되는 사각형의 높이 너비입니다. x 축 (현재 범위에 개체의 원래 크기의 비율) 대상의 확대/축소 비율은 값 **ZoomNum.cx** 의 값으로 나눈 **ZoomDen.cx**합니다. Y 축의 확대/축소 비율 유사한 방식으로 이루어집니다.  
  
 **ZoomDen**  
 실제 너비와 높이의 대상입니다.  
  
## <a name="remarks"></a>주의  
 이 구조체의 일반적인 사용 대상 개체의 렌더링 하는 동안 정보를 검색할 수 있습니다. 예를 들어 값을 검색할 수 있습니다 `ATL_DRAWINFO` 에 오버 로드 내 [CComControlBase::OnDrawAdvanced](ccomcontrolbase-class.md#ondrawadvanced)합니다.  
  
 이 구조는 대상 장치에 대 한 개체의 모양을 렌더링 하는 데 사용 되는 관련 정보를 저장 합니다. 제공 된 정보를 화면, 프린터 또는 심지어 메타 파일 그리기에 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlctl.h  
  
## <a name="see-also"></a>참고 항목  
 [구조](../../atl/reference/atl-structures.md)   
 [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655)   
 [CComControlBase::OnDrawAdvanced](../../atl/reference/ccomcontrolbase-class.md#ondrawadvanced)






