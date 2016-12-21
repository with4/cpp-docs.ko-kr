---
title: "CUserTool Class | Microsoft Docs"
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
  - "CUserTool"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUserTool class"
ms.assetid: 7c287d3e-d012-488d-b4e1-aa0f83f294bb
caps.latest.revision: 25
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CUserTool Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사용자 도구 외부 응용 프로그램을 실행 하는 메뉴 항목입니다.  **도구** 탭의  **사용자 지정** 대화 상자 \([CMFCToolBarsCustomizeDialog Class](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)\) 사용자 도구를 추가 하 고 이름, 명령, 인수 및 초기 디렉터리 각 사용자 도구를 지정할 수 있습니다.  
  
## 구문  
  
```  
class CUserTool : public CObject  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CUserTool::CopyIconToClipboard](../Topic/CUserTool::CopyIconToClipboard.md)||  
|[CUserTool::DrawToolIcon](../Topic/CUserTool::DrawToolIcon.md)|사용자 도구 아이콘에서 지정 된 사각형을 그립니다.|  
|[CUserTool::GetCommand](../Topic/CUserTool::GetCommand.md)|사용자 도구와 관련 된 명령 텍스트를 포함 하는 문자열을 반환 합니다.|  
|[CUserTool::GetCommandId](../Topic/CUserTool::GetCommandId.md)|사용자가 도구 메뉴 항목의 명령 ID를 반환합니다.|  
|[CUserTool::Invoke](../Topic/CUserTool::Invoke.md)|사용자 도구와 관련 된 명령을 실행 합니다.|  
|[CUserTool::Serialize](../Topic/CUserTool::Serialize.md)|읽거나 또는 보관 파일에이 개체를 씁니다.  \(재정의 [CObject::Serialize](../Topic/CObject::Serialize.md).\)|  
|[CUserTool::SetCommand](../Topic/CUserTool::SetCommand.md)|사용자 도구와 연결 된 명령을 설정 합니다.|  
|[CUserTool::SetToolIcon](../Topic/CUserTool::SetToolIcon.md)|도구와 관련 된 응용 프로그램에서 사용자 도구에 대 한 아이콘을 로드 합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CUserTool::LoadDefaultIcon](../Topic/CUserTool::LoadDefaultIcon.md)|사용자 도구에 대 한 기본 아이콘을 로드합니다.|  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CUserTool::m\_strArguments](../Topic/CUserTool::m_strArguments.md)|사용자 도구에 대 한 명령줄 인수입니다.|  
|[CUserTool::m\_strInitialDirectory](../Topic/CUserTool::m_strInitialDirectory.md)|사용자 도구에 대 한 초기 디렉터리입니다.|  
|[CUserTool::m\_strLabel](../Topic/CUserTool::m_strLabel.md)|도구 메뉴 항목에 표시 되는 도구 이름입니다.|  
  
## 설명  
 응용 프로그램에서 사용자가 도구를 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오. [CUserToolsManager Class](../../mfc/reference/cusertoolsmanager-class.md).  
  
## 예제  
 다음 예제에서는 도구를 만드는 방법을 보여 줍니다.를 `CUserToolsManager` 개체, 설정의 `m_strLabel` 멤버 변수 및 사용자 도구를 실행 하는 응용 프로그램 설정.  이 코드 조각에 속해 있는  [Visual Studio 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#35](../../mfc/codesnippet/CPP/cusertool-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CUserTool](../../mfc/reference/cusertool-class.md)  
  
## 요구 사항  
 **헤더:** afxusertool.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)   
 [CUserToolsManager Class](../../mfc/reference/cusertoolsmanager-class.md)