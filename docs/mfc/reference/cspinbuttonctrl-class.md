---
title: "CSpinButtonCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSpinButtonCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSpinButtonCtrl class"
  - "CSpinButtonCtrl class, 공용 컨트롤"
  - "spin button 컨트롤"
  - "up-down 컨트롤, spin button 컨트롤"
  - "Windows common controls [C++], CSpinButtonCtrl"
ms.assetid: 509bfd76-1c5a-4af6-973f-e133c0b87734
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CSpinButtonCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 공용 스핀 단추 컨트롤의 기능을 제공합니다.  
  
## 구문  
  
```  
class CSpinButtonCtrl : public CWnd  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CSpinButtonCtrl::CSpinButtonCtrl](../Topic/CSpinButtonCtrl::CSpinButtonCtrl.md)|`CSpinButtonCtrl` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSpinButtonCtrl::Create](../Topic/CSpinButtonCtrl::Create.md)|스핀 단추 컨트롤을 만들고이에 연결 된 `CSpinButtonCtrl` 개체입니다.|  
|[CSpinButtonCtrl::CreateEx](../Topic/CSpinButtonCtrl::CreateEx.md)|지정한 Windows 확장된 스타일 스핀 단추 컨트롤을 만들고이에 연결 된 `CSpinButtonCtrl` 개체입니다.|  
|[CSpinButtonCtrl::GetAccel](../Topic/CSpinButtonCtrl::GetAccel.md)|스핀 단추 컨트롤에 대 한 가속도 정보를 검색합니다.|  
|[CSpinButtonCtrl::GetBase](../Topic/CSpinButtonCtrl::GetBase.md)|스핀 단추 컨트롤에 대 한 현재 기준을 검색합니다.|  
|[CSpinButtonCtrl::GetBuddy](../Topic/CSpinButtonCtrl::GetBuddy.md)|현재 버디 창에 대 한 포인터를 검색합니다.|  
|[CSpinButtonCtrl::GetPos](../Topic/CSpinButtonCtrl::GetPos.md)|스핀 단추 컨트롤의 현재 위치를 검색합니다.|  
|[CSpinButtonCtrl::GetRange](../Topic/CSpinButtonCtrl::GetRange.md)|상한 및 하 한 제한 \(범위\) 스핀 단추 컨트롤을 검색합니다.|  
|[CSpinButtonCtrl::SetAccel](../Topic/CSpinButtonCtrl::SetAccel.md)|스핀 단추 컨트롤에 대 한 가속을 설정합니다.|  
|[CSpinButtonCtrl::SetBase](../Topic/CSpinButtonCtrl::SetBase.md)|스핀 단추 컨트롤에 대 한 기본을 설정입니다.|  
|[CSpinButtonCtrl::SetBuddy](../Topic/CSpinButtonCtrl::SetBuddy.md)|스핀 단추 컨트롤의 버디 창으로 설정합니다.|  
|[CSpinButtonCtrl::SetPos](../Topic/CSpinButtonCtrl::SetPos.md)|컨트롤의 현재 위치를 설정합니다.|  
|[CSpinButtonCtrl::SetRange](../Topic/CSpinButtonCtrl::SetRange.md)|상한 및 하 한 제한 \(범위\) 스핀 단추 컨트롤을 설정합니다.|  
  
## 설명  
 "\(로 up\-down 컨트롤이 라고도 함\)는 스핀 단추 컨트롤"을 증가 시키거나 감소 스크롤 위치 또는 도우미 컨트롤에 표시 되는 숫자 값을 사용자가 클릭할 수 화살표 단추 쌍입니다.  스핀 단추 컨트롤과 연결 된 값은 현재 위치를 라고 합니다.  스핀 단추 컨트롤 "버디 창" 이라는 컨트롤과 함께, 가장 많이 사용 됩니다.  
  
 이 컨트롤 \(즉의 `CSpinButtonCtrl` 클래스\) Windows NT 및 Windows 95\/98 버전 3.51에서 실행 되는 프로그램에만 사용할 수 있습니다.  
  
 사용자에 게 스핀 단추 컨트롤 및 버디 창 종종 단일 컨트롤 같은 찾습니다.  스핀 단추 컨트롤 자체를 버디 창 옆에 있는 위치를 자동으로 하 고 자동으로 버디 창의 캡션을 현재 위치에 설정 되었는지 지정할 수 있습니다.  스핀 단추 컨트롤 숫자 입력에 대해 묻는 메시지를 편집 컨트롤을 사용할 수 있습니다.  
  
 위쪽 화살표를 클릭 하면 현재 위치에서 최대 쪽으로 이동 및 아래쪽 화살표를 클릭 하면 최소값 방향으로 현재 위치를 이동.  기본 최소값은 100입니다 및 최대값은 0입니다.  최소 설정은 설정 \(예를 들어, 기본 설정을 사용할 경우\), 클릭 위쪽 화살표 감소 최대값 보다 큽니다 언제 든 위치 값 및 아래쪽 화살표를 클릭 하 증가 그.  
  
 스핀 단추 컨트롤 없이 버디 창 단순화 된 스크롤 막대의 일종으로 작동합니다.  예를 들어, 탭 컨트롤을 스핀 단추 컨트롤을 추가 탭 보기로 스크롤할 수 있게 하는 경우가 표시 됩니다.  
  
 사용에 대 한 자세한 내용은 `CSpinButtonCtrl`를 참조 하십시오  [컨트롤](../../mfc/controls-mfc.md) 및  [CSpinButtonCtrl 사용](../../mfc/using-cspinbuttonctrl.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSpinButtonCtrl`  
  
## 요구 사항  
 **헤더:**  afxcmn.h  
  
## 참고 항목  
 [MFC 샘플 CMNCTRL2](../../top/visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CSliderCtrl Class](../../mfc/reference/csliderctrl-class.md)