---
title: "CCmdUI Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CCmdUI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "단추[C++], 컨텍스트 변경으로 업데이트"
  - "CCmdUI class"
  - "command user interface"
  - "명령[C++], updating UI"
  - "menus [C++], 컨텍스트 변경으로 업데이트"
  - "상태, updating user interface object"
  - "도구 모음[C++], 업데이트"
  - "updating user interfaces for commands"
  - "사용자 인터페이스, 업데이트"
ms.assetid: 04eaaaf5-f510-48ab-b425-94665ba24766
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CCmdUI Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

내 에서만 사용 되는 `ON_UPDATE_COMMAND_UI` 처리기에는 `CCmdTarget`\-클래스를 파생 합니다.  
  
## 구문  
  
```  
class CCmdUI  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CCmdUI::ContinueRouting](../Topic/CCmdUI::ContinueRouting.md)|계속 다운 처리기 체인이 현재 메시지 라우팅 명령 라우팅 메커니즘을 설명 합니다.|  
|[CCmdUI::Enable](../Topic/CCmdUI::Enable.md)|이 명령에 대 한 사용자 인터페이스 항목을 사용할 수 있거나.|  
|[CCmdUI::SetCheck](../Topic/CCmdUI::SetCheck.md)|이 명령에 대 한 사용자 인터페이스 항목의 선택 상태를 설정합니다.|  
|[CCmdUI::SetRadio](../Topic/CCmdUI::SetRadio.md)|같은 `SetCheck` 멤버 함수는 하지만 라디오 그룹에서 작동 합니다.|  
|[CCmdUI::SetText](../Topic/CCmdUI::SetText.md)|이 명령에 대 한 사용자 인터페이스 항목에 대 한 텍스트를 설정합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CCmdUI::m\_nID](../Topic/CCmdUI::m_nID.md)|사용자 인터페이스 개체의 ID입니다.|  
|[CCmdUI::m\_nIndex](../Topic/CCmdUI::m_nIndex.md)|사용자 인터페이스 개체의 인덱스입니다.|  
|[CCmdUI::m\_pMenu](../Topic/CCmdUI::m_pMenu.md)|가리키는 표시 메뉴에 있는 `CCmdUI` 개체입니다.|  
|[CCmdUI::m\_pOther](../Topic/CCmdUI::m_pOther.md)|알림 전송 창 개체를 가리킵니다.|  
|[CCmdUI::m\_pSubMenu](../Topic/CCmdUI::m_pSubMenu.md)|표시 되는 포함 된 하위 메뉴를 가리키는 있는 `CCmdUI` 개체입니다.|  
  
## 설명  
 `CCmdUI`기본 클래스에 없는 것입니다.  
  
 때 사용자가 응용 프로그램의 메뉴, 각 메뉴 항목 요구 사항이 사용으로 표시 되는지 여부를 확인 또는 사용 안 함 아래로 끌어옵니다.  대상의 메뉴 명령 구현 하 여이 정보를 제공 된 `ON_UPDATE_COMMAND_UI` 처리기.  응용 프로그램에서 사용자 인터페이스 명령 개체 마다 각 처리기에 대 한 메시지 맵 항목 및 함수 프로토타입을 만들려면 속성 창을 사용 합니다.  
  
 메뉴를 끌어오면 프레임 워크에 대 한 검색 하 고 각 호출 `ON_UPDATE_COMMAND_UI` 각 처리기를 호출 하는 처리기를 `CCmdUI` 멤버 함수 같은  **사용** 및  **체크**, 프레임 워크는 적절 하 게 다음 각 메뉴 항목 표시.  
  
 메뉴 항목 컨트롤 도구 모음 단추나 다른 명령 사용자 인터페이스 개체 내의 코드를 변경 하지 않고도 대체 될 수 있는 `ON_UPDATE_COMMAND_UI` 처리기.  
  
 다음 표에서 효과 `CCmdUI`의 멤버 함수에 다양 한 명령을 사용자 인터페이스 항목에.  
  
|사용자 인터페이스 항목|사용|SetCheck|SetRadio|SetText|  
|------------------|--------|--------------|--------------|-------------|  
|Menu item|활성화 또는 비활성화|선택 하거나 확인 \(×\)|점 \(•\)를 사용 하 여 검사|텍스트 설정 항목|  
|도구 모음 단추|활성화 또는 비활성화|선택, 선택 취소, 또는 비활성화|동일`SetCheck`|적용할 수 없음|  
|상태 표시줄 창|텍스트를 표시 하거나 숨길 수 있습니다.|팝업 또는 기본 테두리 설정|동일`SetCheck`|창 텍스트를 설정합니다.|  
|기본 단추`CDialogBar`|활성화 또는 비활성화|확인란을 선택 하거나|동일`SetCheck`|텍스트 설정 단추|  
|일반 컨트롤에서`CDialogBar`|활성화 또는 비활성화|적용할 수 없음|적용할 수 없음|창 텍스트를 설정합니다.|  
  
 자세한 내용은이 클래스의 사용을 참조 하십시오.  [는 사용자 인터페이스 개체 업데이트 방법](../../mfc/how-to-update-user-interface-objects.md).  
  
## 상속 계층 구조  
 `CCmdUI`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [MDI MFC 샘플](../../top/visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)