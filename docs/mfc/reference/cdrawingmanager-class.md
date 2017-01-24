---
title: "CDrawingManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDrawingManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDrawingManager class"
ms.assetid: 9e4775ca-101b-4aa9-a85a-4d047c701215
caps.latest.revision: 30
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDrawingManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CDrawingManager` 복잡 한 그리기 알고리즘 클래스를 구현 합니다.  
  
## 구문  
  
```  
class CDrawingManager : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDrawingManager::CDrawingManager](../Topic/CDrawingManager::CDrawingManager.md)|`CDrawingManager` 개체를 생성합니다.|  
|`CDrawingManager::~CDrawingManager`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDrawingManager::CreateBitmap\_32](../Topic/CDrawingManager::CreateBitmap_32.md)|응용 프로그램에 직접 쓸 수 있는 32 비트 장치 독립적 비트맵 \(DIB\) 만듭니다.|  
|[CDrawingManager::DrawAlpha](../Topic/CDrawingManager::DrawAlpha.md)|투명 또는 반투명 픽셀 비트맵을 표시 합니다.|  
|[CDrawingManager::DrawRotated](../Topic/CDrawingManager::DrawRotated.md)|원본 DC 콘텐츠에 의해 지정 된 사각형 안에 \+ \/\-90도 회전합니다.|  
|[CDrawingManager::DrawEllipse](../Topic/CDrawingManager::DrawEllipse.md)|제공 된 채우기 및 테두리 색으로 타원을 그립니다.|  
|[CDrawingManager::DrawGradientRing](../Topic/CDrawingManager::DrawGradientRing.md)|링 그리고이 색 그라데이션으로 채웁니다.|  
|[CDrawingManager::DrawLine, CDrawingManager::DrawLineA](../Topic/CDrawingManager::DrawLine,%20CDrawingManager::DrawLineA.md)|선을 그립니다.|  
|[CDrawingManager::DrawRect](../Topic/CDrawingManager::DrawRect.md)|제공 된 채우기 및 테두리 색으로 사각형을 그립니다.|  
|[CDrawingManager::DrawShadow](../Topic/CDrawingManager::DrawShadow.md)|그림자 사각형 영역을 그립니다.|  
|[CDrawingManager::Fill4ColorsGradient](../Topic/CDrawingManager::Fill4ColorsGradient.md)|두 색 그라데이션으로 사각형 영역을 채웁니다.|  
|[CDrawingManager::FillGradient](../Topic/CDrawingManager::FillGradient.md)|지정한 색 그라데이션이 있는 사각형 영역을 채웁니다.|  
|[CDrawingManager::FillGradient2](../Topic/CDrawingManager::FillGradient2.md)|지정한 색 그라데이션이 있는 사각형 영역을 채웁니다.  그라디언트 색상 변경의 방향을 지정 합니다.|  
|[CDrawingManager::GrayRect](../Topic/CDrawingManager::GrayRect.md)|지정 된 회색 사각형을 채웁니다.|  
|[CDrawingManager::HighlightRect](../Topic/CDrawingManager::HighlightRect.md)|사각형 영역을 강조 표시합니다.|  
|[CDrawingManager::HLStoRGB\_ONE](../Topic/CDrawingManager::HLStoRGB_ONE.md)|색상 HLS 표현에서 RGB 표현으로 변환합니다.|  
|[CDrawingManager::HLStoRGB\_TWO](../Topic/CDrawingManager::HLStoRGB_TWO.md)|색상 HLS 표현에서 RGB 표현으로 변환합니다.|  
|[CDrawingManager::HSVtoRGB](../Topic/CDrawingManager::HSVtoRGB.md)|색은 HSV 표현에서 RGB 표현으로 변환합니다.|  
|[CDrawingManager::HuetoRGB](../Topic/CDrawingManager::HuetoRGB.md)|색상 값은 빨강, 녹색 또는 파랑 구성 요소에 변환 하는 도우미 메서드.|  
|[CDrawingManager::MirrorRect](../Topic/CDrawingManager::MirrorRect.md)|사각형 영역을 대칭 이동합니다.|  
|[CDrawingManager::PixelAlpha](../Topic/CDrawingManager::PixelAlpha.md)|반투명 픽셀에 대 한 최종 색상을 결정 하는 도우미 메서드.|  
|[CDrawingManager::PrepareShadowMask](../Topic/CDrawingManager::PrepareShadowMask.md)|그림자로 사용할 수 있는 비트맵을 만듭니다.|  
|[CDrawingManager::RGBtoHSL](../Topic/CDrawingManager::RGBtoHSL.md)|색 RGB 표현에서 HSL 표현으로 변환합니다.|  
|[CDrawingManager::RGBtoHSV](../Topic/CDrawingManager::RGBtoHSV.md)|색 RGB 표현에서 HSV 표현으로 변환합니다.|  
|[CDrawingManager::SetAlphaPixel](../Topic/CDrawingManager::SetAlphaPixel.md)|부분적으로 투명 한 픽셀은 비트맵에 색을 하는 도우미 메서드.|  
|[CDrawingManager::SetPixel](../Topic/CDrawingManager::SetPixel.md)|단일 픽셀의 비트맵을 지정 된 색으로 변경 하는 도우미 메서드.|  
|[CDrawingManager::SmartMixColors](../Topic/CDrawingManager::SmartMixColors.md)|가 중된 비율을 기준으로 두 색상을 결합 합니다.|  
  
## 설명  
 `CDrawingManager` 클래스 그림자, 그라디언트 색상 및 강조 표시 된 사각형을 그리는 데 함수를 제공 합니다.  또한 알파 혼합 수행합니다.  이 클래스를 사용 하면 직접 응용 프로그램의 UI를 변경할 수 있습니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDrawingManager](../../mfc/reference/cdrawingmanager-class.md)  
  
## 요구 사항  
 **헤더:** afxdrawmanager.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)