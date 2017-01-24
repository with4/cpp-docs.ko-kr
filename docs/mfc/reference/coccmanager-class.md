---
title: "COccManager Class | Microsoft Docs"
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
  - "COccManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX 컨트롤 컨테이너[C++], control site"
  - "CNoTrackObject class"
  - "COccManager class"
  - "사용자 지정 컨트롤[MFC], sites"
ms.assetid: 7d47aeed-d1ab-48e3-b4cf-d429718e370a
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COccManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사용자 정의 컨트롤의 다양 한 사이트를 관리 합니다. 구현에서 `COleControlContainer` 및 `COleControlSite` 개체입니다.  
  
## 구문  
  
```  
class COccManager : public CNoTrackObject  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COccManager::CreateContainer](../Topic/COccManager::CreateContainer.md)|생성 된  **COleContainer** 개체.|  
|[COccManager::CreateDlgControls](../Topic/COccManager::CreateDlgControls.md)|호스트에서 연결 된 ActiveX 컨트롤을 만드는 `COleContainer` 개체입니다.|  
|[COccManager::CreateSite](../Topic/COccManager::CreateSite.md)|`COleClientSite` 개체를 만듭니다.|  
|[COccManager::GetDefBtnCode](../Topic/COccManager::GetDefBtnCode.md)|기본 단추 코드를 검색합니다.|  
|[COccManager::IsDialogMessage](../Topic/COccManager::IsDialogMessage.md)|대화 메시지의 대상을 결정합니다.|  
|[COccManager::IsLabelControl](../Topic/COccManager::IsLabelControl.md)|지정 된 컨트롤에 label 컨트롤 인지 확인 합니다.|  
|[COccManager::IsMatchingMnemonic](../Topic/COccManager::IsMatchingMnemonic.md)|현재 니모닉 지정 된 컨트롤의 니모닉 일치 하는지 확인 합니다.|  
|[COccManager::OnEvent](../Topic/COccManager::OnEvent.md)|지정 된 이벤트를 처리 하려고 시도 합니다.|  
|[COccManager::PostCreateDialog](../Topic/COccManager::PostCreateDialog.md)|대화 상자를 생성 하는 동안 할당 된 리소스를 해제 합니다.|  
|[COccManager::PreCreateDialog](../Topic/COccManager::PreCreateDialog.md)|ActiveX 컨트롤에 대 한 대화 상자 템플릿을 처리합니다.|  
|[COccManager::SetDefaultButton](../Topic/COccManager::SetDefaultButton.md)|지정 된 컨트롤의 기본 상태를 전환합니다.|  
|[COccManager::SplitDialogTemplate](../Topic/COccManager::SplitDialogTemplate.md)|공용 컨트롤에서 지정 된 대화 상자 템플릿 기존 ActiveX 컨트롤을 구분합니다.|  
  
## 설명  
 기본 클래스를  **CNoTrackObject**에 문서화 되지 않은 기본 클래스 \(AFXTLS에 위치 합니다.H\)입니다.  MFC 프레임 워크에서 사용 하기 위해 설계 된 클래스에서 파생 된  **CNoTrackObject** 클래스에서 메모리 누수 탐지 제외 됩니다.  직접 파생 권장 되지 않습니다  **CNoTrackObject**.  
  
## 상속 계층 구조  
 `CNoTrackObject`  
  
 `COccManager`  
  
## 요구 사항  
 **헤더:** afxocc.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleControlSite Class](../../mfc/reference/colecontrolsite-class.md)   
 [COleControlContainer Class](../../mfc/reference/colecontrolcontainer-class.md)