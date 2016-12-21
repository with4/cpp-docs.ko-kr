---
title: "CDateTimeCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDateTimeCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDateTimeCtrl class"
  - "date-picking functionality"
  - "DateTimePicker control [MFC]"
  - "DateTimePicker control [MFC], CDateTimeCtrl class"
ms.assetid: 7113993b-5d37-4148-939f-500a190c5bdc
caps.latest.revision: 23
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDateTimeCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

날짜 및 시간 선택 컨트롤의 기능을 캡슐화합니다.  
  
## 구문  
  
```  
class CDateTimeCtrl : public CWnd  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDateTimeCtrl::CDateTimeCtrl](../Topic/CDateTimeCtrl::CDateTimeCtrl.md)|`CDateTimeCtrl` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDateTimeCtrl::CloseMonthCal](../Topic/CDateTimeCtrl::CloseMonthCal.md)|현재 날짜 및 시간 선택 컨트롤을 닫습니다.|  
|[CDateTimeCtrl::Create](../Topic/CDateTimeCtrl::Create.md)|날짜 및 시간 선택 컨트롤을 만들고이에 연결 된 `CDateTimeCtrl` 개체입니다.|  
|[CDateTimeCtrl::GetDateTimePickerInfo](../Topic/CDateTimeCtrl::GetDateTimePickerInfo.md)|현재 날짜 및 시간 선택 컨트롤에 대 한 정보를 검색합니다.|  
|[CDateTimeCtrl::GetIdealSize](../Topic/CDateTimeCtrl::GetIdealSize.md)|현재 날짜나 시간을 표시 하는 데 필요한 시간 및 날짜 선택 컨트롤의 이상적인 크기를 반환 합니다.|  
|[CDateTimeCtrl::GetMonthCalColor](../Topic/CDateTimeCtrl::GetMonthCalColor.md)|월 달력에서 날짜 및 시간 선택 컨트롤의 특정된 부분에 대 한 색을 검색합니다.|  
|[CDateTimeCtrl::GetMonthCalCtrl](../Topic/CDateTimeCtrl::GetMonthCalCtrl.md)|검색은 `CMonthCalCtrl` 개체의 날짜 및 시간 선택 컨트롤에 연결 합니다.|  
|[CDateTimeCtrl::GetMonthCalFont](../Topic/CDateTimeCtrl::GetMonthCalFont.md)|현재 날짜 및 시간 선택 컨트롤의 자식 컨트롤에서 사용 되는 글꼴을 검색 합니다.|  
|[CDateTimeCtrl::GetMonthCalStyle](../Topic/CDateTimeCtrl::GetMonthCalStyle.md)|현재 날짜 및 시간 선택 컨트롤의 스타일을 가져옵니다.|  
|[CDateTimeCtrl::GetRange](../Topic/CDateTimeCtrl::GetRange.md)|현재 최소 및 최대 허용 시스템 시간 날짜 및 시간 선택 컨트롤을 검색 합니다.|  
|[CDateTimeCtrl::GetTime](../Topic/CDateTimeCtrl::GetTime.md)|날짜 및 시간 선택 컨트롤에서 현재 선택한 시간을 검색 하 고 지정 된 배치 `SYSTEMTIME` 구조.|  
|[CDateTimeCtrl::SetFormat](../Topic/CDateTimeCtrl::SetFormat.md)|지정 된 형식 문자열에 따라 날짜 및 시간 선택 컨트롤의 표시를 설정합니다.|  
|[CDateTimeCtrl::SetMonthCalColor](../Topic/CDateTimeCtrl::SetMonthCalColor.md)|월 달력에서 날짜 및 시간 선택 컨트롤의 특정된 부분에 대 한 색을 설정합니다.|  
|[CDateTimeCtrl::SetMonthCalFont](../Topic/CDateTimeCtrl::SetMonthCalFont.md)|날짜 및 시간 선택 컨트롤의 자식 컨트롤을 사용 하는 글꼴을 설정 합니다.|  
|[CDateTimeCtrl::SetMonthCalStyle](../Topic/CDateTimeCtrl::SetMonthCalStyle.md)|현재 날짜 및 시간 선택 컨트롤의 스타일을 설정합니다.|  
|[CDateTimeCtrl::SetRange](../Topic/CDateTimeCtrl::SetRange.md)|날짜 및 시간 선택 컨트롤에 대 한 최소 및 최대 허용 된 시스템 시간을 설정합니다.|  
|[CDateTimeCtrl::SetTime](../Topic/CDateTimeCtrl::SetTime.md)|날짜 및 시간 선택 컨트롤에는 시간을 설정합니다.|  
  
## 설명  
 날짜 및 시간 선택 컨트롤 \(DTP\) 사용자가 날짜 및 시간 정보를 교환 하는 간단한 인터페이스를 제공 합니다.  이 인터페이스는 각각은 해당 컨트롤에 저장 된 날짜 및 시간 정보를 표시 하는 필드를 포함 합니다.  문자열에서 지정된 된 필드의 내용을 변경 하 여 컨트롤에 저장 된 정보를 변경할 수 있습니다.  마우스나 키보드를 사용 하 여 필드에서 사용자를 이동할 수 있습니다.  
  
 만들 때 개체에 다양 한 스타일을 적용 하 여 날짜 및 시간 선택 컨트롤을 사용자 지정할 수 있습니다.  참조  [날짜 및 시간 선택 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb761728) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 날짜 및 시간 선택 컨트롤에 특정 스타일에 대 한 자세한 내용은.  서식 스타일을 사용 하 여 DTP 컨트롤의 표시 형식을 설정할 수 있습니다.  이러한 서식 스타일 "서식 스타일" 아래에 나와 있는 [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)] 항목  [날짜 및 시간 선택 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb761728).  
  
 날짜 및 시간 선택 컨트롤 또한 알림 및에서 설명 하는 콜백을 사용  [CDateTimeCtrl을 사용 하 여](../../mfc/using-cdatetimectrl.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDateTimeCtrl`  
  
## 요구 사항  
 **헤더:**  afxdtctl.h  
  
## 참고 항목  
 [MFC 샘플 CMNCTRL1](../../top/visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CMonthCalCtrl Class](../../mfc/reference/cmonthcalctrl-class.md)