---
title: "CProgressCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CProgressCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CProgressCtrl class"
  - "Internet Explorer 4.0 common controls"
  - "progress controls [C++], CProgressCtrl class"
ms.assetid: 222630f4-1598-4026-8198-51649b1192ab
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CProgressCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

일반적인 진행률 표시줄 Windows 컨트롤의 기능을 제공합니다.  
  
## 구문  
  
```  
class CProgressCtrl : public CWnd  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CProgressCtrl::CProgressCtrl](../Topic/CProgressCtrl::CProgressCtrl.md)|`CProgressCtrl` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CProgressCtrl::Create](../Topic/CProgressCtrl::Create.md)|진행률 표시줄 컨트롤을 만들고이에 연결 된 `CProgressCtrl` 개체입니다.|  
|[CProgressCtrl::CreateEx](../Topic/CProgressCtrl::CreateEx.md)|지정한 Windows 확장된 스타일 진행률 컨트롤을 만들고 연결 하는 `CProgressCtrl` 개체입니다.|  
|[CProgressCtrl::GetBarColor](../Topic/CProgressCtrl::GetBarColor.md)|현재 진행률 표시줄 컨트롤의 진행률 표시줄의 색을 가져옵니다.|  
|[CProgressCtrl::GetBkColor](../Topic/CProgressCtrl::GetBkColor.md)|현재 진행률 막대의 배경색을 가져옵니다.|  
|[CProgressCtrl::GetPos](../Topic/CProgressCtrl::GetPos.md)|진행률 표시줄의 현재 위치를 가져옵니다.|  
|[CProgressCtrl::GetRange](../Topic/CProgressCtrl::GetRange.md)|최저 한계와 최고 한계를 진행률 표시줄 컨트롤의 범위를 가져옵니다.|  
|[CProgressCtrl::GetState](../Topic/CProgressCtrl::GetState.md)|현재 진행률 표시줄 컨트롤의 상태를 가져옵니다.|  
|[CProgressCtrl::GetStep](../Topic/CProgressCtrl::GetStep.md)|현재 진행률 표시줄 컨트롤의 진행률 표시줄에 대 한 단계적 증가 값을 검색합니다.|  
|[CProgressCtrl::OffsetPos](../Topic/CProgressCtrl::OffsetPos.md)|진행률 표시줄 컨트롤의 현재 위치를 지정한 양만큼 이동 하 고 새 위치를 반영 하는 모음을 다시 그립니다.|  
|[CProgressCtrl::SetBarColor](../Topic/CProgressCtrl::SetBarColor.md)|현재 진행률 표시줄 컨트롤에는 진행률 표시줄의 색을 설정합니다.|  
|[CProgressCtrl::SetBkColor](../Topic/CProgressCtrl::SetBkColor.md)|진행률 표시줄에 대 한 배경 색을 설정 합니다.|  
|[CProgressCtrl::SetMarquee](../Topic/CProgressCtrl::SetMarquee.md)|현재 진행률 표시줄 컨트롤을 움직이는 텍스트 모드로를 설정 또는 해제 합니다.|  
|[CProgressCtrl::SetPos](../Topic/CProgressCtrl::SetPos.md)|진행률 표시줄 컨트롤에 대 한 현재 위치를 설정 하 고 새 위치를 반영 하는 모음을 다시 그립니다.|  
|[CProgressCtrl::SetRange](../Topic/CProgressCtrl::SetRange.md)|진행률 표시줄 컨트롤에 대 한 최소 및 최대 범위를 설정 하 고 새 범위를 반영 하는 모음을 다시 그립니다.|  
|[CProgressCtrl::SetState](../Topic/CProgressCtrl::SetState.md)|현재 진행률 표시줄 컨트롤의 상태를 설정합니다.|  
|[CProgressCtrl::SetStep](../Topic/CProgressCtrl::SetStep.md)|진행률 표시줄 컨트롤에 대 한 단계적 증가 값을 지정합니다.|  
|[CProgressCtrl::StepIt](../Topic/CProgressCtrl::StepIt.md)|단계적 증가 값으로 진행률 표시줄 컨트롤에 대 한 현재 위치를 앞으로 이동 \(참조  [SetStep](../Topic/CProgressCtrl::SetStep.md)\) 하 고 새 위치를 반영 하는 모음을 다시 그립니다.|  
  
## 설명  
 진행률 표시줄 컨트롤은 응용 프로그램이 긴 작업의 진행률을 나타내기 위해 사용할 수 있는 창입니다.  점차적으로, 왼쪽에서 오른쪽 시스템으로 작업 진행에 따른 강조색으로 채워지는 사각형으로 구성 됩니다.  
  
 진행률 표시줄 컨트롤에는 범위 및 현재 위치가 있습니다.  작업의 총 기간 범위를 나타내는 및 현재 위치는 응용 프로그램으로 작업을 완료 했습니다 진행률을 나타냅니다.  범위 및 현재 위치가 창 프로시저를 사용 하 여 강조 색으로 채우는 진행률 표시줄의 백분율을 결정 합니다.  범위 및 현재 위치 값을 부호 있는 정수로 표현 되는 현재 위치 값의 가능한 범위에서 – 2, 때문에, 147, 483, 648 2147483647 까지입니다.  
  
 사용에 대 한 자세한 내용은 `CProgressCtrl`를 참조 하십시오  [컨트롤](../../mfc/controls-mfc.md) 및  [CProgressCtrl 사용](../../mfc/using-cprogressctrl.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CProgressCtrl`  
  
## 요구 사항  
 **헤더:**  afxcmn.h  
  
## 참고 항목  
 [MFC 샘플 CMNCTRL2](../../top/visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)