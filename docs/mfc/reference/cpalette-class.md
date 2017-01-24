---
title: "CPalette Class | Microsoft Docs"
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
  - "CPalette"
  - "HPALETTE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "색상표, MFC"
  - "CPalette class"
  - "HPALETTE"
ms.assetid: 8cd95498-53ed-4852-85e1-70e522541114
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPalette Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 색상표를 캡슐화합니다.  
  
## 구문  
  
```  
class CPalette : public CGdiObject  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CPalette::CPalette](../Topic/CPalette::CPalette.md)|생성 된 `CPalette` 개체와 연결 된 Windows 색상표가 있습니다.  초기화 해야는 `CPalette` 개체를 사용 하기 전에 초기화 멤버 함수 중 하나를 사용 합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CPalette::AnimatePalette](../Topic/CPalette::AnimatePalette.md)|대체 항목을 식별 하는 논리 색상표를 `CPalette` 개체입니다.  Windows는 시스템 색상표에 새 항목을 즉시 매핑되기 때문에 응용 프로그램의 클라이언트 영역을 업데이트할 수 없습니다.|  
|[CPalette::CreateHalftonePalette](../Topic/CPalette::CreateHalftonePalette.md)|장치 컨텍스트에 대 한 하프톤 색상표를 만들고를 연결 된 `CPalette` 개체입니다.|  
|[CPalette::CreatePalette](../Topic/CPalette::CreatePalette.md)|Windows 색상표를 만들고 연결 하는 `CPalette` 개체입니다.|  
|[CPalette::FromHandle](../Topic/CPalette::FromHandle.md)|반환에 대 한 포인터는 `CPalette` Windows 색상표 개체에 핸들을 지정 하면 개체입니다.|  
|[CPalette::GetEntryCount](../Topic/CPalette::GetEntryCount.md)|논리 색상표의 색상표 항목을 검색합니다.|  
|[CPalette::GetNearestPaletteIndex](../Topic/CPalette::GetNearestPaletteIndex.md)|가장 가깝게 일치 하는 색상 값의 논리 색상표에서 항목의 인덱스를 반환 합니다.|  
|[CPalette::GetPaletteEntries](../Topic/CPalette::GetPaletteEntries.md)|논리 색상표에서 색상표 항목의 범위를 검색합니다.|  
|[CPalette::ResizePalette](../Topic/CPalette::ResizePalette.md)|지정 된 논리 색상표의 크기를 변경의 `CPalette` 개체에 지정 된 항목 수입니다.|  
|[CPalette::SetPaletteEntries](../Topic/CPalette::SetPaletteEntries.md)|논리 색상표에서 항목의 범위에서 RGB 색상 값과 플래그를 설정합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CPalette::operator HPALETTE](../Topic/CPalette::operator%20HPALETTE.md)|반환 된 `HPALETTE` 연결을 `CPalette`.|  
  
## 설명  
 색상표 색 출력 장치 \(예: 디스플레이 장치\) 응용 프로그램 사이의 인터페이스를 제공합니다.  인터페이스는 응용 프로그램을 출력 장치의 색 기능을 다른 응용 프로그램에서 표시 되는 색상을 심각 하 게 방해 하지 않고 활용할 수 있습니다.  Windows 응용 프로그램의 논리적 팔레트 \(필요한 색 목록\) 및 \(사용 가능한 색 정의\)의 시스템 팔레트 사용 되는 색상이 결정 됩니다.  
  
 A `CPalette` 개체 개체에서 참조 하는 색상표를 조작 하기 위한 멤버 함수를 제공 합니다.  생성 된 `CPalette` 개체와 해당 멤버 함수를 사용 하 여 실제 색상표 그래픽 장치 인터페이스 \(GDI\) 개체를 만들 수 및 해당 항목과 다른 속성을 조작 하.  
  
 사용에 대 한 자세한 내용은 `CPalette`를 참조 하십시오  [그래픽 개체](../../mfc/graphic-objects.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPalette`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [Diblook에서는 MFC 샘플](../../top/visual-cpp-samples.md)   
 [CGdiObject Class](../../mfc/reference/cgdiobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CPalette::GetPaletteEntries](../Topic/CPalette::GetPaletteEntries.md)   
 [CPalette::SetPaletteEntries](../Topic/CPalette::SetPaletteEntries.md)