---
title: "CKeyboardManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CKeyboardManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CKeyboardManager class"
ms.assetid: 4809ece6-89df-4479-8b53-9bf476ee107b
caps.latest.revision: 33
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 35
---
# CKeyboardManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

주 프레임 창과 자식 프레임 창에 대 한 바로 가기 키 테이블을 관리합니다.  
  
## 구문  
  
```  
class CKeyboardManager : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|||  
|-|-|  
|Name|설명|  
|[CKeyboardManager::CKeyboardManager](../Topic/CKeyboardManager::CKeyboardManager.md)|`CKeyboardManager` 개체를 생성합니다.|  
  
### Public 메서드  
  
|||  
|-|-|  
|Name|설명|  
|[CKeyboardManager::CleanUp](../Topic/CKeyboardManager::CleanUp.md)|바로 가기 키 테이블을 지웁니다.|  
|[CKeyboardManager::FindDefaultAccelerator](../Topic/CKeyboardManager::FindDefaultAccelerator.md)|지정 된 명령 및 창에 대 한 기본 바로 가기 키를 검색합니다.|  
|[CKeyboardManager::IsKeyHandled](../Topic/CKeyboardManager::IsKeyHandled.md)|액셀러레이터 키 테이블에서 키를 처리할지 여부를 결정 합니다.|  
|[CKeyboardManager::IsKeyPrintable](../Topic/CKeyboardManager::IsKeyPrintable.md)|문자를 인쇄할 수 있는지 여부를 나타냅니다.|  
|[CKeyboardManager::IsShowAllAccelerators](../Topic/CKeyboardManager::IsShowAllAccelerators.md)|메뉴 명령의 바로 가기 키를 모두 또는 기본 바로 가기 키를 표시할지 여부를 나타냅니다.|  
|[CKeyboardManager::LoadState](../Topic/CKeyboardManager::LoadState.md)|바로 가기 키 테이블 Windows 레지스트리에서 로드 됩니다.|  
|[CKeyboardManager::ResetAll](../Topic/CKeyboardManager::ResetAll.md)|바로 가기 키 테이블에서 응용 프로그램 리소스를 다시 로드합니다.|  
|[CKeyboardManager::SaveState](../Topic/CKeyboardManager::SaveState.md)|바로 가기 키 테이블은 Windows 레지스트리에 저장합니다.|  
|[CKeyboardManager::ShowAllAccelerators](../Topic/CKeyboardManager::ShowAllAccelerators.md)|프레임 워크는 각 명령에 대 한 단일 바로 가기 키 또는 모든 명령에 대 한 모든 바로 가기 키 표시 여부를 지정 합니다.  이 메서드는 하나의 연결 된 바로 가기 키가 명령 적용 되지 않습니다.|  
|[CKeyboardManager::TranslateCharToUpper](../Topic/CKeyboardManager::TranslateCharToUpper.md)|해당 상위 레지스터에 문자를 변환합니다.|  
|[CKeyboardManager::UpdateAccelTable](../Topic/CKeyboardManager::UpdateAccelTable.md)|바로 가기 키 테이블에 새 바로 가기 키 테이블을 업데이트합니다.|  
  
## 설명  
 이 클래스의 멤버를 사용 하 여 저장 및 로드 Windows 레지스트리를 바로 가기 키 테이블, 서식 파일을 사용 하 여 바로 가기 키 테이블을 업데이트 하 고 프레임 창에는 명령에 대 한 기본 바로 가기 키 찾기.  또한는 `CKeyboardManager` 개체를 사용 하면 사용자에 게 바로 가기 키 표시 방법을 제어 합니다.  
  
 만들어야지 않습니다는 `CKeyboardManager` 수동으로 개체입니다.  응용 프로그램 프레임 워크에서 자동으로 작성 됩니다.  그러나 호출 해야 [CWinAppEx::InitKeyboardManager](../Topic/CWinAppEx::InitKeyboardManager.md) 응용 프로그램 초기화 중입니다.  키보드 관리자에 게 응용 프로그램에 대 한 포인터를 가져오려면 호출 [CWinAppEx::GetKeyboardManager](../Topic/CWinAppEx::GetKeyboardManager.md).  
  
## 예제  
 다음 예제에 대 한 포인터를 검색 하는 방법을 보여 줍니다.을 `CKeyboardManager` 에서 개체는 `CWinAppEx` 클래스 및 메뉴 명령과 관련 된 모든 바로 가기 키를 표시 하는 방법.  이 코드 조각에 속하지는  [샘플 사용자 지정 페이지](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages#5](../../mfc/reference/codesnippet/CPP/ckeyboardmanager-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)  
  
## 요구 사항  
 **헤더:** afxkeyboardmanager.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)   
 [CWinAppEx::InitKeyboardManager](../Topic/CWinAppEx::InitKeyboardManager.md)   
 [키보드 및 마우스 사용자 지정](../../mfc/keyboard-and-mouse-customization.md)