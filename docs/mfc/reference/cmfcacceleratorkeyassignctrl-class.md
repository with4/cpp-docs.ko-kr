---
title: "CMFCAcceleratorKeyAssignCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCAcceleratorKeyAssignCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCAcceleratorKeyAssignCtrl class"
ms.assetid: 89fb8e62-596e-4e71-8c9a-32740347aaab
caps.latest.revision: 33
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 35
---
# CMFCAcceleratorKeyAssignCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCAcceleratorKeyAssignCtrl` 클래스는 [CEdit Class](../../mfc/reference/cedit-class.md)를 확장하여 ALT, CONTROL, SHIFT 등의 추가 시스템 단추를 지원합니다.  
  
## 구문  
  
```  
class CMFCAcceleratorKeyAssignCtrl : public CEdit  
```  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl](../Topic/CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl.md)|`CMFCAcceleratorKeyAssignCtrl` 개체를 생성합니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCAcceleratorKeyAssignCtrl::GetAccel](../Topic/CMFCAcceleratorKeyAssignCtrl::GetAccel.md)|`CMFCAcceleratorKeyAssignCtrl` 개체에서 누른 바로 가기 키에 대한 `ACCEL` 구조체를 검색합니다.|  
|[CMFCAcceleratorKeyAssignCtrl::IsFocused](../Topic/CMFCAcceleratorKeyAssignCtrl::IsFocused.md)||  
|[CMFCAcceleratorKeyAssignCtrl::IsKeyDefined](../Topic/CMFCAcceleratorKeyAssignCtrl::IsKeyDefined.md)|바로 가기 키가 정의되었는지 여부를 확인합니다.|  
|[CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage](../Topic/CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage.md)|창 메시지가 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및 [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 함수로 디스패치되기 전에 [CWinApp](../../mfc/reference/cwinapp-class.md) 클래스가 이 메시지를 해석하는 데 사용됩니다.  \([CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md)를 재정의합니다.\)|  
|[CMFCAcceleratorKeyAssignCtrl::ResetKey](../Topic/CMFCAcceleratorKeyAssignCtrl::ResetKey.md)|바로 가기 키를 다시 설정합니다.|  
  
## 설명  
 이 클래스는 액셀러레이터 키라고도 하는 바로 가기 키를 지원하여 `CEdit` 클래스의 기능을 확장합니다.  `CMFCAcceleratorKeyAssignCtrl` 클래스는 [CEdit Class](../../mfc/reference/cedit-class.md)로 기능하며 시스템 단추를 인식할 수도 있습니다.  
  
 이 클래스는 실제 바로 가기 키 조합을 문자열 값에 매핑합니다.  예를 들어 키 조합 ALT \+ B가 문자열 "Alt \+ B"에 매핑된다고 가정하겠습니다.  사용자가 `CMFCAcceleratorKeyAssignCtrl` 개체에서 이 키를 조합을 누르면 "Alt \+ B"가 사용자에게 표시됩니다.  바로 가기 키와 문자열 형식 간의 매핑에 대한 자세한 내용은 [CMFCAcceleratorKey Class](../../mfc/reference/cmfcacceleratorkey-class.md)를 참조하세요.  
  
## 예제  
 다음 예제에서는 `CMFCAcceleratorKeyAssignCtrl` 개체를 생성하고 해당 `ResetKey` 메서드를 사용하여 바로 가기 키를 다시 설정하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#31](../../mfc/reference/codesnippet/CPP/cmfcacceleratorkeyassignctrl-class_1.cpp)]  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md)  
  
## 요구 사항  
 **헤더:** afxacceleratorkeyassignctrl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCAcceleratorKey Class](../../mfc/reference/cmfcacceleratorkey-class.md)