---
title: "ATL_DRAWINFO Structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::ATL_DRAWINFO"
  - "ATL_DRAWINFO"
  - "ATL.ATL_DRAWINFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL_DRAWINFO structure"
ms.assetid: dd2e2aa8-e8c5-403b-b4df-35c0f6f57fb7
caps.latest.revision: 16
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL_DRAWINFO Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ActiveX 컨트롤, 메타 파일 또는 프린터 등의 다양 한 대상의 렌더링에 사용 되는 정보가 들어 있습니다.  
  
## 구문  
  
```  
  
      struct ATL_DRAWINFO{  
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
  
## Members  
 `cbSize`  
 구조의 바이트 크기입니다.  
  
 **dwDrawAspect**  
 대상 표시 될 방식을 지정 합니다.  표현 내용, 아이콘, 미리 보기를 또는 문서를 인쇄할된 수 있습니다.  가능한 값 목록을 보려면을 참조 하십시오.  [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) 및  [DVASPECT2](http://msdn.microsoft.com/library/windows/desktop/ms688644).  
  
 **색인입니다.**  
 관심 그리기 작업의 대상의 일부입니다.  해석의 값에 따라 달라 집니다를  **dwDrawAspect** 멤버입니다.  
  
 **ptd**  
 포인터는  [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) 지정 된 모양에 따라 드로잉을 최적화 하는 구조입니다.  참고 새 개체와 그리기 최적화 된 인터페이스를 지 원하는 컨테이너도이 멤버를 지원 합니다.  이전 개체 및 최적화 된 그리기 인터페이스 항상 지원 하지 않는 컨테이너를 지정 합니다.  **NULL** 이 됩니다.  
  
 **hicTargetDev**  
 대상 장치에 대 한 정보 컨텍스트 여를 가리키는  **ptd** 개체에서 장치 메트릭을 추출 하 고 장치 기능을 테스트 합니다.  경우  **ptd** 는  **NULL**, 개체의 값을 무시 해야는  **hicTargetDev** 멤버.  
  
 **hdcDraw**  
 그릴 장치 컨텍스트입니다.  창 없는 개체를  **hdcDraw** 멤버인에 `MM_TEXT` 클라이언트 좌표를 포함 하는 창에 일치 하는 해당 논리 좌표 매핑 모드.  또한 장치 컨텍스트 정상적으로 전달 된 것 같은 상태에서 여야 합니다의 `WM_PAINT` 메시지.  
  
 **prcBounds**  
 포인터는  [RECTL](http://msdn.microsoft.com/library/windows/desktop/dd162907) 구조에 사각형을 지정 합니다.  **hdcDraw** 에 그려야 개체는.  이 구성원 위치와 개체의 확장을 제어 합니다.  이 멤버  **NULL** 창 없는 내부 활성 개체를 그립니다.  모든 상황에서  **NULL** 값 이며의 `E_INVALIDARG` 오류 코드입니다.  비 컨테이너를 통과 하면\-**NULL** 창 없는 개체를, 개체 값에 지정 된 장치 컨텍스트 및 사각형 요청한 측면 렌더링 해야 합니다.  컨테이너는이 두 번째, 비활성 개체의 보기를 렌더링 하거나 개체를 인쇄 하려면 창 없는 개체에서 요청할 수 있습니다.  
  
 **prcWBounds**  
 경우  **hdcDraw** 메타 파일 디바이스 컨텍스트는 \(참조  [GetDeviceCaps](http://msdn.microsoft.com/library/windows/desktop/dd144877) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]\),이에 대 한 포인터입니다.는  **RECTL** 내부 메타 파일에 경계 사각형을 지정 하는 구조.  창 크기 및 창 원점 사각형 구조를 포함합니다.  이러한 값은 메타 파일 그리기에 대 한 유용 합니다.  사각형을 표시 하 여  **prcBounds** 이 안에 중첩 된  **prcWBounds** 직사각형을 그립니다. 이러한 동일한 좌표 공간에 있습니다.  
  
 **bOptimize**  
 컨트롤의 그리기 최적화 된, 그렇지 않으면 0 이면 0이 아닌.  드로잉 최적화 되 면 완료 되 면 장치 컨텍스트의 상태를 자동으로 복원 됩니다 렌더링 합니다.  
  
 **bZoomed**  
 대상 확대\/축소 비율, 그렇지 않으면 0 이면 0이 아닌.  확대\/축소 비율에 저장 된  **ZoomNum**.  
  
 **bRectInHimetric**  
 0이 아닌 경우 치수의  **prcBounds** 에 있는  **HIMETRIC**, 그렇지 않으면 0입니다.  
  
 **ZoomNum**  
 개체를 렌더링 하는 데 사용 되는 사각형의 높이 및 너비.  대상 \(개체의 원래 크기를 현재 범위에 비율\) x 축 따라 있는 확대\/축소 비율의 값이  **ZoomNum.cx** 의 값으로 나눈  **ZoomDen.cx**.  눌러 확대 계수는 y 축 따라 비슷한 방식으로 이루어집니다.  
  
 **ZoomDen**  
 실제 너비와 높이의 대상입니다.  
  
## 설명  
 이 구조체의 일반적인 사용 동안 렌더링 대상 객체의 정보가 검색 됩니다.  예를 들어, 값을 검색할 수 `ATL_DRAWINFO` 내에 오버 로드의  [CComControlBase::OnDrawAdvanced](../Topic/CComControlBase::OnDrawAdvanced.md).  
  
 이 구조는 대상 장치에 대 한 개체의 모양을 렌더링 하는 데 관련 정보가 있습니다.  화면, 프린터, 심지어 메타 파일 그리기에서 제공 하는 정보를 사용할 수 있습니다.  
  
## 요구 사항  
 **헤더:** atlctl.h  
  
## 참고 항목  
 [구조체](../../atl/reference/atl-structures.md)   
 [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655)   
 [CComControlBase::OnDrawAdvanced](../Topic/CComControlBase::OnDrawAdvanced.md)