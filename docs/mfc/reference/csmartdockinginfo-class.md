---
title: "CSmartDockingInfo Class | Microsoft Docs"
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
  - "CSmartDockingInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSmartDockingInfo class"
ms.assetid: cab04f38-4bc1-4378-9337-c56fc87fbd68
caps.latest.revision: 27
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSmartDockingInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스마트 도킹 마커 모양을 정의합니다.  
  
## 구문  
  
```  
class CSmartDockingInfo : public CObject  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|`CSmartDockingInfo::CSmartDockingInfo`|기본 생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSmartDockingInfo::CopyTo](../Topic/CSmartDockingInfo::CopyTo.md)|현재 스마트 도킹 정보 매개로 제공 된 복사  [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) 개체입니다.|  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CSmartDockingInfo::m\_bUseThemeColorInShading](../Topic/CSmartDockingInfo::m_bUseThemeColorInShading.md)|프레임 워크 스마트 도킹 마커를 표시 하는 경우 현재 테마 색을 사용할지 여부를 지정 합니다.|  
|[CSmartDockingInfo::m\_clrBaseBackground](../Topic/CSmartDockingInfo::m_clrBaseBackground.md)|스마트 도킹 마커 기본 배경색을 지정합니다.|  
|[CSmartDockingInfo::m\_clrToneDest](../Topic/CSmartDockingInfo::m_clrToneDest.md)|대체 색 지정 `m_clrToneSrc` 스마트 도킹 마커 비트맵에서.|  
|[CSmartDockingInfo::m\_clrToneSrc](../Topic/CSmartDockingInfo::m_clrToneSrc.md)|스마트 도킹 마커 비트맵의 색을 지정합니다.|  
|[CSmartDockingInfo::m\_clrTransparent](../Topic/CSmartDockingInfo::m_clrTransparent.md)|투명 한 경우 스마트 도킹 마커 비트맵의 색을 지정 합니다.|  
|[CSmartDockingInfo::m\_nCentralGroupOffset](../Topic/CSmartDockingInfo::m_nCentralGroupOffset.md)|중앙 그룹의 스마트 도킹 마커 중앙 그룹 사각형의 경계에서의 오프셋을 지정합니다.|  
|[CSmartDockingInfo::m\_sizeTotal](../Topic/CSmartDockingInfo::m_sizeTotal.md)|그룹의 모든 스마트 도킹 마커 총 크기를 지정합니다.|  
|[CSmartDockingInfo::m\_uiMarkerBmpResID](../Topic/CSmartDockingInfo::m_uiMarkerBmpResID.md)|Id 강조 표시 되지 않은 스마트 도킹 마커를 프레임 워크를 사용 하 여 비트맵 리소스를 정의 합니다.|  
|[CSmartDockingInfo::m\_uiMarkerLightBmpResID](../Topic/CSmartDockingInfo::m_uiMarkerLightBmpResID.md)|Id 강조 표시 된 스마트 도킹 마커를 프레임 워크를 사용 하 여 비트맵 리소스를 정의 합니다.|  
  
## 설명  
 프레임 워크 핸들 도킹 마커 내부적으로 스마트.  다음 그림에서는 표준 스마트 도킹 마커를 보여 줍니다.  
  
 ![스마트 도킹의 표준 마커](../../mfc/reference/media/nextsdmarkers.png "nextSDmarkers")  
  
 이 그림에서 사용할 수 있는 탭으로 도킹 되지 않은 중앙 그룹 스마트 도킹 마커 왼쪽 이미지를 보여 줍니다.  스마트 도킹 마커 오른쪽 가장자리 가운데에 이미지를 보여 줍니다.  이미지 오른쪽에 사용할 수 있는 탭으로 도킹 되어 있지는 중앙 그룹 스마트 도킹 마커를 표시 합니다.  중앙 그룹 스마트 도킹 마커 기본 비트맵이 5 도킹 마커 비트맵.  
  
 스마트 도킹 마커 다음 매개 변수를 사용자 지정할 수 있습니다.  
  
-   색  예를 들어, 모든 사용자 정의 색상에 파란색 마커 그림에서을 바꿀 수 있습니다.  
  
-   투명색입니다.  
  
-   스마트 도킹 표식 테두리에서 중앙 그룹 경계 사각형의 오프셋입니다.  
  
-   주 중앙 그룹을 나타내는 비트맵입니다.  
  
-   일반 및 강조 표시 된 스마트 도킹 마커를 나타내는 비트맵입니다.  
  
 다음 그림에서는 예제 사용자 지정 된 스마트 도킹 마커를 보여 줍니다.  
  
 ![스마트 도킹의 사용자 지정 마커](../../mfc/reference/media/nextsdmarkerscustom.png "nextSDmarkersCustom")  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)  
  
## 요구 사항  
 **헤더:** afxDockingManager.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)