---
title: "CHotKeyCtrl Class | Microsoft Docs"
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
  - "CHotKeyCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHotKeyCtrl class"
  - "hot key controls"
  - "Windows common controls [C++], CHotKeyCtrl"
ms.assetid: 896f9766-0718-4f58-aab2-20325e118ca6
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHotKeyCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 공용 hot key 컨트롤의 기능을 제공합니다.  
  
## 구문  
  
```  
class CHotKeyCtrl : public CWnd  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CHotKeyCtrl::CHotKeyCtrl](../Topic/CHotKeyCtrl::CHotKeyCtrl.md)|`CHotKeyCtrl` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CHotKeyCtrl::Create](../Topic/CHotKeyCtrl::Create.md)|Hot key 컨트롤을 만들고이에 연결 된 `CHotKeyCtrl` 개체입니다.|  
|[CHotKeyCtrl::CreateEx](../Topic/CHotKeyCtrl::CreateEx.md)|지정한 Windows 확장된 스타일 hot key 컨트롤을 만들고이에 연결 된 `CHotKeyCtrl` 개체입니다.|  
|[CHotKeyCtrl::GetHotKey](../Topic/CHotKeyCtrl::GetHotKey.md)|Hot key 컨트롤에서 가상 키 코드 및 한정자 플래그에 바로 가기 키를 검색합니다.|  
|[CHotKeyCtrl::GetHotKeyName](../Topic/CHotKeyCtrl::GetHotKeyName.md)|바로 가기 키에 할당 하는 로컬 문자 집합에서 키 이름을 검색 합니다.|  
|[CHotKeyCtrl::GetKeyName](../Topic/CHotKeyCtrl::GetKeyName.md)|지정 된 가상 키 코드를 할당 하는 로컬 문자 집합에서 키 이름을 검색 합니다.|  
|[CHotKeyCtrl::SetHotKey](../Topic/CHotKeyCtrl::SetHotKey.md)|Hot key 컨트롤에 대 한 바로 가기 키 조합을 설정합니다.|  
|[CHotKeyCtrl::SetRules](../Topic/CHotKeyCtrl::SetRules.md)|Hot key 컨트롤의 기본 한정자 조합 및 잘못 된 조합을 정의합니다.|  
  
## 설명  
 "Hot key 컨트롤" 바로 가기 키를 만들 수 있는 창입니다.  "핫 키"는 사용자 키를 눌러 작업을 빠르게 수행할 수 있습니다 키 조합입니다.  \(예를 들어, 사용자가 바로 가기 키에 지정 된 창을 활성화 하 고 위쪽에 Z 순서를 가져옵니다 만들 수 있습니다.\) Hot key 컨트롤 사용자의 선택 항목을 표시 하 고 사용자가 올바른 키조합을 선택할 수 있도록 합니다.  
  
 이 컨트롤 \(즉의 `CHotKeyCtrl` 클래스\) Windows NT 및 Windows 95\/98 버전 3.51에서 실행 되는 프로그램에만 사용할 수 있습니다.  
  
 사용자 키 조합을 선택 하는 경우 응용 프로그램 컨트롤에서 지정 된 키 조합을 검색 하 고 사용 수는  **WM\_SETHOTKEY** 메시지 시스템에 바로 가기 키를 설정 합니다.  핫 키 이후부터 시스템의 일부를 누를 때마다 지정한 창에는  **WM\_SETHOTKEY** 메시지를 받고는 `WM_SYSCOMMAND` 메시지를 지정 합니다.  **SC\_HOTKEY**.  이 메시지는 수신 창이 활성화 됩니다.  호출 응용 프로그램이 될 때까지 핫 키 유효  **WM\_SETHOTKEY** 를 종료 합니다.  
  
 이 메커니즘에서 핫 키 지원에 따라 다릅니다의  **WM\_HOTKEY** 메시지 및 Windows  [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309) 및  [UnregisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646327) 함수입니다.  
  
 사용에 대 한 자세한 내용은 `CHotKeyCtrl`를 참조 하십시오  [컨트롤](../../mfc/controls-mfc.md) 및  [CHotKeyCtrl를 사용 하 여](../../mfc/using-chotkeyctrl.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHotKeyCtrl`  
  
## 요구 사항  
 **헤더:**  afxcmn.h  
  
## 참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)