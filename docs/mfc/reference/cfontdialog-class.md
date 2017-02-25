---
title: "CFontDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFontDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFontDialog class"
  - "대화 상자, 글꼴"
  - "글꼴"
  - "글꼴, 선택"
ms.assetid: 6228d500-ed0f-4156-81e5-ab0d57d1dcf4
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CFontDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

글꼴 선택 대화 상자를 응용 프로그램에 통합할 수 있습니다.  
  
## 구문  
  
```  
class CFontDialog : public CCommonDialog  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CFontDialog::CFontDialog](../Topic/CFontDialog::CFontDialog.md)|`CFontDialog` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CFontDialog::DoModal](../Topic/CFontDialog::DoModal.md)|사용자 선택 대화 상자를 표시 합니다.|  
|[CFontDialog::GetCharFormat](../Topic/CFontDialog::GetCharFormat.md)|선택한 글꼴의 문자 서식을 검색 합니다.|  
|[CFontDialog::GetColor](../Topic/CFontDialog::GetColor.md)|선택한 글꼴의 색을 반환 합니다.|  
|[CFontDialog::GetCurrentFont](../Topic/CFontDialog::GetCurrentFont.md)|현재 선택된 된 글꼴의 특성을 지정 된 `LOGFONT` 구조.|  
|[CFontDialog::GetFaceName](../Topic/CFontDialog::GetFaceName.md)|선택한 글꼴의 글꼴 이름을 반환합니다.|  
|[CFontDialog::GetSize](../Topic/CFontDialog::GetSize.md)|선택한 글꼴의 포인트 크기를 반환합니다.|  
|[CFontDialog::GetStyleName](../Topic/CFontDialog::GetStyleName.md)|선택한 글꼴 스타일 이름을 반환합니다.|  
|[CFontDialog::GetWeight](../Topic/CFontDialog::GetWeight.md)|선택한 글꼴의 가중치를 반환합니다.|  
|[CFontDialog::IsBold](../Topic/CFontDialog::IsBold.md)|글꼴을 굵게 표시할지 여부를 결정 합니다.|  
|[CFontDialog::IsItalic](../Topic/CFontDialog::IsItalic.md)|글꼴이 기울임꼴인지 여부를 결정 합니다.|  
|[CFontDialog::IsStrikeOut](../Topic/CFontDialog::IsStrikeOut.md)|글꼴에 취소선을 표시할지 여부를 결정 합니다.|  
|[CFontDialog::IsUnderline](../Topic/CFontDialog::IsUnderline.md)|글꼴에 밑줄이 있는지 여부를 결정 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CFontDialog::m\_cf](../Topic/CFontDialog::m_cf.md)|사용자 지정 하는 데 사용 되는 구조체는 `CFontDialog` 개체입니다.|  
  
## 설명  
 A `CFontDialog` 개체의 현재 시스템에 설치 된 글꼴 목록이 대화 상자입니다.  사용자 목록에서 특정 글꼴을 선택할 수 있습니다 및 응용 프로그램에이 이렇게 다시 다음 보고 합니다.  
  
 생성 하는 `CFontDialog` 개체, 제공 된 생성자를 사용 하거나 새 하위 클래스를 파생 및 고유의 사용자 지정 생성자를 사용 합니다.  
  
 한 번에 `CFontDialog` 개체를 생성 되었습니다, 사용할 수 있습니다는 `m_cf` 값 또는 대화 상자에서 컨트롤의 상태를 초기화 하는 구조.  [M\_cf](../Topic/CFontDialog::m_cf.md) 구조체의 형식이  [CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832).  이 구조에 대 한 자세한 내용은 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 호출 대화 상자 개체의 컨트롤을 초기화 한 후에 `DoModal` 멤버 함수를 대화 상자를 표시 하 고 글꼴을 선택할 수 있습니다.  `DoModal`사용자가 확인 선택 여부를 반환 \(**IDOK**\) 또는 취소 \(**IDCANCEL**\) 단추.  
  
 경우 `DoModal` 반환  **IDOK**, 중 하나를 사용할 수 있습니다 `CFontDialog`의 멤버 함수는 사용자가 입력 한 정보를 검색할 수 있습니다.  
  
 창 수  [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) 함수 대화 상자를 초기화 하는 동안 오류가 있는지 여부를 확인 하 고 오류에 대 한 자세한.  이 함수에 대 한 자세한 내용은 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `CFontDialog`COMMDLG에 의존합니다.Windows 3.1 및 이후 버전에 제공 되는 DLL 파일입니다.  
  
 사용자 지정 대화 상자에는 클래스에서 파생 `CFontDialog`확장된 컨트롤에서 알림 메시지를 처리 하는 메시지 맵 추가, 사용자 지정 대화 상자 템플릿을 제공 합니다.  처리 되지 않은 모든 메시지는 기본 클래스에 전달 합니다.  
  
 후크 함수를 사용자 지정 하지 않아도 됩니다.  
  
 사용에 대 한 자세한 내용은 `CFontDialog`를 참조 하십시오  [공용 대화 상자 클래스](../../mfc/common-dialog-classes.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFontDialog`  
  
## 요구 사항  
 **헤더:**  afxdlgs.h  
  
## 참고 항목  
 [HIERSVR MFC 샘플](../../top/visual-cpp-samples.md)   
 [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)