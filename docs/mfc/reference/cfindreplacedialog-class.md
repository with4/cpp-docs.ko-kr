---
title: "CFindReplaceDialog Class | Microsoft Docs"
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
  - "CFindReplaceDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFindReplaceDialog class"
  - "Find/Replace dialog box"
  - "텍스트 바꾸기"
  - "텍스트 바꾸기, CFindReplaceDialog class"
  - "텍스트 검색, CFindReplaceDialog class"
  - "텍스트 검색, 텍스트 바꾸기"
ms.assetid: 610f0b5d-b398-4ef6-8c05-e9d6641e50a8
caps.latest.revision: 25
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFindReplaceDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

표준 문자열 찾기\/바꾸기 대화 상자에서 응용 프로그램을 구현할 수 있습니다.  
  
## 구문  
  
```  
class CFindReplaceDialog : public CCommonDialog  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CFindReplaceDialog::CFindReplaceDialog](../Topic/CFindReplaceDialog::CFindReplaceDialog.md)|만들려면이 함수를 호출 하는 `CFindReplaceDialog` 개체입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CFindReplaceDialog::Create](../Topic/CFindReplaceDialog::Create.md)|만들고 표시 하는 `CFindReplaceDialog` 대화 상자.|  
|[CFindReplaceDialog::FindNext](../Topic/CFindReplaceDialog::FindNext.md)|사용자 찾기 문자열의 다음 항목을 찾을 것인지를 결정 하기 위해이 함수를 호출 합니다.|  
|[CFindReplaceDialog::GetFindString](../Topic/CFindReplaceDialog::GetFindString.md)|현재 찾기 문자열을 검색 하려면이 함수를 호출 합니다.|  
|[CFindReplaceDialog::GetNotifier](../Topic/CFindReplaceDialog::GetNotifier.md)|검색 하려면이 함수를 호출 하는  **FINDREPLACE** 등록 된 메시지 처리기에서 구조.|  
|[CFindReplaceDialog::GetReplaceString](../Topic/CFindReplaceDialog::GetReplaceString.md)|현재 대체 문자열을 검색 하려면이 함수를 호출 합니다.|  
|[CFindReplaceDialog::IsTerminating](../Topic/CFindReplaceDialog::IsTerminating.md)|대화 상자를 종료 하 고 있는지 여부를 확인 하려면이 함수를 호출 합니다.|  
|[CFindReplaceDialog::MatchCase](../Topic/CFindReplaceDialog::MatchCase.md)|사용자가 찾기 문자열의 대\/소문자를 정확 하 게 일치 하고자 하는지 여부를 확인 하려면이 함수를 호출 합니다.|  
|[CFindReplaceDialog::MatchWholeWord](../Topic/CFindReplaceDialog::MatchWholeWord.md)|단어 전체를 부여할지 여부를 확인 하려면이 함수를 호출 합니다.|  
|[CFindReplaceDialog::ReplaceAll](../Topic/CFindReplaceDialog::ReplaceAll.md)|사용자가 모든 항목을 대체 문자열 원하는 여부를 확인 하려면이 함수를 호출 합니다.|  
|[CFindReplaceDialog::ReplaceCurrent](../Topic/CFindReplaceDialog::ReplaceCurrent.md)|사용자 교체는 현재 유지할지 여부를 확인 하려면이 함수를 호출 합니다.|  
|[CFindReplaceDialog::SearchDown](../Topic/CFindReplaceDialog::SearchDown.md)|사용자 검색 아래쪽 방향으로 진행 하 려 여부를 확인 하려면이 함수를 호출 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CFindReplaceDialog::m\_fr](../Topic/CFindReplaceDialog::m_fr.md)|사용자 지정 하는 데 사용 되는 구조체는 `CFindReplaceDialog` 개체입니다.|  
  
## 설명  
 다른 Windows 공용 대화 상자를 달리 `CFindReplaceDialog` 개체는 모덜리스, 화면에 있지만 다른 창과 상호 작용 하도록 허용 합니다.  두 가지 종류의 `CFindReplaceDialog` 개체: 찾기\/바꾸기 대화 상자 및 대화 상자를 찾습니다.  대화 상자 사용자 입력된 검색 및 검색\/바꾸기 문자열 수는 있지만는 검색 이나 바꾸기 기능을 수행 하지 않습니다.  이러한 응용 프로그램에 추가 해야 합니다.  
  
 생성 하는 `CFindReplaceDialog` 개체, \(인수가 없는\) 제공 된 생성자를 사용 합니다.  모덜리스 대화 상자 이므로 개체를 사용 하 여 힙 할당의  **새** 연산자 대신 스택의.  
  
 한 번에 `CFindReplaceDialog` 개체를 생성 되었습니다, 호출 해야는  [만들기](../Topic/CFindReplaceDialog::Create.md) 멤버 함수를 만들고 대화 상자를 표시 하려면.  
  
 사용 된  [m\_fr](../Topic/CFindReplaceDialog::m_fr.md) 를 호출 하기 전에 대화 상자를 초기화 하는 구조  **만들기**.  `m_fr` 구조체의 형식이  [FINDREPLACE](http://msdn.microsoft.com/library/windows/desktop/ms646835).  이 구조에 대 한 자세한 내용은 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 찾기\/바꾸기 요청을 받으려면 부모 창의 순서로 Windows를 사용 해야  [RegisterWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms644947) 작동 하는  [ON\_REGISTERED\_MESSAGE](../Topic/ON_REGISTERED_MESSAGE.md) 메시지 맵 매크로 프레임 창에 등록 된이 메시지를 처리 합니다.  
  
 사용자 대화 상자를 종료 하기로 결정 했습니다 여부를 확인할 수 있는 `IsTerminating` 멤버 함수.  
  
 `CFindReplaceDialog`COMMDLG에 의존합니다.Windows 3.1 및 이후 버전에 제공 되는 DLL 파일입니다.  
  
 사용자 지정 대화 상자에는 클래스에서 파생 `CFindReplaceDialog`확장된 컨트롤에서 알림 메시지를 처리 하는 메시지 맵 추가, 사용자 지정 대화 상자 템플릿을 제공 합니다.  처리 되지 않은 모든 메시지는 기본 클래스에 전달 합니다.  
  
 후크 함수를 사용자 지정 하지 않아도 됩니다.  
  
 사용에 대 한 자세한 내용은 `CFindReplaceDialog`를 참조 하십시오  [공용 대화 상자 클래스](../../mfc/common-dialog-classes.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFindReplaceDialog`  
  
## 요구 사항  
 **헤더:**  afxdlgs.h  
  
## 참고 항목  
 [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)