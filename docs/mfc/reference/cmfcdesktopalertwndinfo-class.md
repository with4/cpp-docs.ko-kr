---
title: "CMFCDesktopAlertWndInfo Class | Microsoft Docs"
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
  - "CMFCDesktopAlertWndInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDesktopAlertWndInfo class"
ms.assetid: 5c9bb84e-6c96-4748-8e74-6951b6ae8e84
caps.latest.revision: 26
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDesktopAlertWndInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCDesktopAlertWndInfo` 클래스는 [CMFCDesktopAlertWnd Class](../../mfc/reference/cmfcdesktopalertwnd-class.md)와 함께 사용됩니다.  바탕 화면 알림 창이 열리면 표시 되는 컨트롤을 지정 합니다.  
  
## 구문  
  
```  
class CMFCDesktopAlertWndInfo  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|`CMFCDesktopAlertWndInfo::~CMFCDesktopAlertWndInfo`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCDesktopAlertWndInfo::operator\=](../Topic/CMFCDesktopAlertWndInfo::operator=.md)||  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CMFCDesktopAlertWndInfo::m\_hIcon](../Topic/CMFCDesktopAlertWndInfo::m_hIcon.md)|표시 되는 아이콘에 대 한 핸들입니다.|  
|[CMFCDesktopAlertWndInfo::m\_nURLCmdID](../Topic/CMFCDesktopAlertWndInfo::m_nURLCmdID.md)|바탕 화면 알림 창에 링크로 연결 된 명령 ID입니다.|  
|[CMFCDesktopAlertWndInfo::m\_strText](../Topic/CMFCDesktopAlertWndInfo::m_strText.md)|바탕 화면 알림 창에 표시 되는 텍스트입니다.|  
|[CMFCDesktopAlertWndInfo::m\_strURL](../Topic/CMFCDesktopAlertWndInfo::m_strURL.md)|바탕 화면 알림 창에 표시 되는 링크입니다.|  
  
## 설명  
 `CMFCDesktopAlertWndInfo` 클래스에 전달 되는 [CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md) 바탕 화면 경고 창이 기본 대화 상자에 표시 되는 요소를 지정할 수 있는 메서드.  기본 대화 세 가지 항목을 포함할 수 있습니다.  
  
-   호출 하 여 설정 된 아이콘을 [CMFCDesktopAlertWndInfo::m\_hIcon](../Topic/CMFCDesktopAlertWndInfo::m_hIcon.md).  
  
-   레이블 또는 텍스트 메시지를 호출 하 여 설정 된 [CMFCDesktopAlertWndInfo::m\_strText](../Topic/CMFCDesktopAlertWndInfo::m_strText.md).  
  
-   링크를 호출 하 여 설정 된 [CMFCDesktopAlertWndInfo::m\_strURL](../Topic/CMFCDesktopAlertWndInfo::m_strURL.md).  링크를 클릭할 때 실행 될 명령을 설정 하려면 호출 [CMFCDesktopAlertWndInfo::m\_nURLCmdID](../Topic/CMFCDesktopAlertWndInfo::m_nURLCmdID.md).  
  
 기본 대화 충분 하지 않으면, 사용자 지정 대화 상자 만들기 및 전달의 [CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md) 메서드 대신이 클래스를 사용 합니다.  자세한 내용은 [CMFCDesktopAlertDialog Class](../../mfc/reference/cmfcdesktopalertdialog-class.md)를 참조하십시오.  
  
## 예제  
 다양 한 구성원을 사용 하는 방법 다음 예제는 `CMFCDesktopAlertWndInfo` 클래스입니다.  표시 되는 바탕 화면 알림 창, 바탕 화면 알림 창에 표시 되는 링크 및 바탕 화면 경고 창에서 링크로 연결 된 명령 ID 표시 텍스트 아이콘 핸들을 설정 하는 예제입니다.  이 이때의 일부인의  [바탕 화면 경고 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#3](../../mfc/reference/codesnippet/CPP/cmfcdesktopalertwndinfo-class_1.cpp)]  
  
## 상속 계층 구조  
 [CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)  
  
## 요구 사항  
 **헤더:** afxDesktopAlertDialog.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertWnd Class](../../mfc/reference/cmfcdesktopalertwnd-class.md)   
 [CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md)   
 [CMFCDesktopAlertDialog Class](../../mfc/reference/cmfcdesktopalertdialog-class.md)