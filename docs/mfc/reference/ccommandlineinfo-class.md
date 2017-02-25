---
title: "CCommandLineInfo Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CCommandLineInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "application flags [C++]"
  - "argv argument"
  - "CCommandLineInfo class"
  - "명령줄, 구문 분석"
  - "구문 분석, 명령줄 인수"
  - "시작 코드, parsing command-line arguments"
ms.assetid: 3e313ddb-0a82-4991-87ac-a27feff4668c
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CCommandLineInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

보조 응용 프로그램을 시작할 때 명령줄을 구문 분석 합니다.  
  
## 구문  
  
```  
class CCommandLineInfo : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CCommandLineInfo::CCommandLineInfo](../Topic/CCommandLineInfo::CCommandLineInfo.md)|기본 구문 `CCommandLineInfo` 개체입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CCommandLineInfo::ParseParam](../Topic/CCommandLineInfo::ParseParam.md)|개별 매개 변수를 구문 분석 하는이 콜백을 재정의 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CCommandLineInfo::m\_bRunAutomated](../Topic/CCommandLineInfo::m_bRunAutomated.md)|명령줄을 나타내는 **\/Automation** 옵션을 발견 했습니다.|  
|[CCommandLineInfo::m\_bRunEmbedded](../Topic/CCommandLineInfo::m_bRunEmbedded.md)|명령줄을 나타내는 **\/Embedding** 옵션을 발견 했습니다.|  
|[CCommandLineInfo::m\_bShowSplash](../Topic/CCommandLineInfo::m_bShowSplash.md)|시작 화면을 표시할지 여부를 나타냅니다.|  
|[CCommandLineInfo::m\_nShellCommand](../Topic/CCommandLineInfo::m_nShellCommand.md)|셸 명령을 처리를 나타냅니다.|  
|[CCommandLineInfo::m\_strDriverName](../Topic/CCommandLineInfo::m_strDriverName.md)|드라이버를 나타내는 이름 경우 셸 명령을 인쇄 합니다. 그렇지 않으면 빈.|  
|[CCommandLineInfo::m\_strFileName](../Topic/CCommandLineInfo::m_strFileName.md)|열거나 인쇄할 파일 이름을 나타냅니다. 셸 명령 또는 새 DDE 이면 빈.|  
|[CCommandLineInfo::m\_strPortName](../Topic/CCommandLineInfo::m_strPortName.md)|포트를 나타내는 이름 경우 셸 명령을 인쇄 합니다. 그렇지 않으면 빈.|  
|[CCommandLineInfo::m\_strPrinterName](../Topic/CCommandLineInfo::m_strPrinterName.md)|프린터 표시 이름을 경우 셸 명령을 인쇄 합니다. 그렇지 않으면 빈.|  
|[CCommandLineInfo::m\_strRestartIdentifier](../Topic/CCommandLineInfo::m_strRestartIdentifier.md)|다시 시작 관리자는 응용 프로그램이 다시 시작 된 경우 다시 시작 관리자에 대 한 다시 시작을 고유 식별자를 나타냅니다.|  
  
## 설명  
 일반적으로 MFC 응용 프로그램에서이 클래스의 로컬 인스턴스 만듭니다는  [InitInstance](../Topic/CWinApp::InitInstance.md) 응용 프로그램 개체를 함수입니다.  이 개체 다음 전달  [CWinApp::ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md)는 반복적으로 호출  [ParseParam](../Topic/CCommandLineInfo::ParseParam.md) 채울 수는 `CCommandLineInfo` 개체.  `CCommandLineInfo` 개체에 전달 되 고  [CWinApp::ProcessShellCommand](../Topic/CWinApp::ProcessShellCommand.md) 명령줄 인수와 플래그를 처리할 수 있습니다.  
  
 다음 명령줄 옵션 및 매개 변수를 캡슐화 합니다.이 개체를 사용할 수 있습니다.  
  
|명령줄 인수|명령 실행|  
|------------|-----------|  
|*응용 프로그램*|새 파일입니다.|  
|*응용 프로그램* 파일 이름|파일을 엽니다.|  
|*응용 프로그램* **\/p** 파일 이름|파일을 기본 프린터로 인쇄 합니다.|  
|*응용 프로그램* **\/pt** 프린터 드라이버가 포트 파일 이름|파일에 지정한 프린터로 인쇄 합니다.|  
|*app* **\/dde**|시작 하 고 DDE 명령을 기다립니다.|  
|*응용 프로그램* **\/Automation**|OLE 자동화 서버로 시작 합니다.|  
|*응용 프로그램* **\/Embedding**|포함 된 OLE 항목을 편집 하려면 시작 합니다.|  
|*응용 프로그램* **\/Register**<br /><br /> *응용 프로그램* **\/Regserver**|모든 등록 작업을 수행 하는 응용 프로그램을 알려 줍니다.|  
|*응용 프로그램* **\/Unregister**<br /><br /> *응용 프로그램* **\/Unregserver**|등록 취소 작업을 수행 하는 응용 프로그램을 알려 줍니다.|  
  
 새 클래스를 파생 시키는 `CCommandLineInfo` 다른 플래그와 매개 변수 값을 처리 합니다.  재정의  [ParseParam](../Topic/CCommandLineInfo::ParseParam.md) 새 플래그 처리 하도록 합니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CCommandLineInfo`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWinApp::ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md)   
 [CWinApp::ProcessShellCommand](../Topic/CWinApp::ProcessShellCommand.md)