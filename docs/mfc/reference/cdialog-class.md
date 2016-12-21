---
title: "CDialog Class | Microsoft Docs"
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
  - "CDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDialog class"
  - "MFC 대화 상자, 기본 클래스"
  - "모달 대화 상자, 만들기"
  - "모덜리스 대화 상자, 만들기"
  - "모덜리스 대화 상자, 표시"
ms.assetid: ca64b77e-2cd2-47e3-8eff-c2645ad578f9
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

화면에 대화 상자를 표시 하는 데 사용 되는 기본 클래스입니다.  
  
## 구문  
  
```  
class CDialog : public CWnd  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDialog::CDialog](../Topic/CDialog::CDialog.md)|`CDialog` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDialog::Create](../Topic/CDialog::Create.md)|`CDialog` 개체를 초기화합니다.  모덜리스 대화 상자를 만들고 연결 하는 `CDialog` 개체입니다.|  
|[CDialog::CreateIndirect](../Topic/CDialog::CreateIndirect.md)|모덜리스 대화 상자를 대화 상자 템플릿에서 메모리에서 \(리소스 기반이 아님\)을 만듭니다.|  
|[CDialog::DoModal](../Topic/CDialog::DoModal.md)|모달 대화 상자를 호출 하 고 완료 되 면 반환 합니다.|  
|[CDialog::EndDialog](../Topic/CDialog::EndDialog.md)|모달 대화 상자를 닫습니다.|  
|[CDialog::GetDefID](../Topic/CDialog::GetDefID.md)|대화 상자에 기본 누름 단추 컨트롤의 ID를 가져옵니다.|  
|[CDialog::GotoDlgCtrl](../Topic/CDialog::GotoDlgCtrl.md)|대화 상자에서 지정 된 대화 상자 컨트롤에 포커스를 이동합니다.|  
|[CDialog::InitModalIndirect](../Topic/CDialog::InitModalIndirect.md)|모달 대화 상자를 대화 상자 템플릿에서 메모리에서 \(리소스 기반이 아님\)을 만듭니다.  매개 변수는 함수까지 저장 된 `DoModal` 라고 합니다.|  
|[CDialog::MapDialogRect](../Topic/CDialog::MapDialogRect.md)|대화 상자 단위 사각형의 화면 단위를 변환합니다.|  
|[CDialog::NextDlgCtrl](../Topic/CDialog::NextDlgCtrl.md)|대화 상자에서 다음 대화 상자 컨트롤에 포커스를 이동합니다.|  
|[CDialog::OnInitDialog](../Topic/CDialog::OnInitDialog.md)|대화 상자 초기화를 확대 하도록 재정의 합니다.|  
|[CDialog::OnSetFont](../Topic/CDialog::OnSetFont.md)|재정의 대화 상자 컨트롤의 텍스트를 그릴 때 사용 되는 글꼴을 지정 합니다.|  
|[CDialog::PrevDlgCtrl](../Topic/CDialog::PrevDlgCtrl.md)|대화 상자에서 이전 대화 상자 컨트롤에 포커스를 이동합니다.|  
|[CDialog::SetDefID](../Topic/CDialog::SetDefID.md)|누름 단추에 지정 된 대화 상자의 기본 누름 단추 컨트롤을 변경합니다.|  
|[CDialog::SetHelpID](../Topic/CDialog::SetHelpID.md)|대화 상자에 대 한 상황에 맞는 도움말 ID를 설정합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDialog::OnCancel](../Topic/CDialog::OnCancel.md)|취소 단추 또는 ESC 키 동작을 수행 하도록 재정의 합니다.  기본 대화 상자를 닫습니다 및  **DoModal**  반환  **IDCANCEL**.|  
|[CDialog::OnOK](../Topic/CDialog::OnOK.md)|모달 대화 상자에서 확인 단추 작업을 수행 하는 재정의 합니다.  기본 대화 상자를 닫습니다 및 `DoModal` 반환  **IDOK**.|  
  
## 설명  
 대화 상자는 두 가지 유형의: 모달 및 모덜리스.  모달 대화 상자는 응용 프로그램을 계속 하기 전에 사용자가 닫아야 합니다.  모덜리스 대화 상자 대화 상자를 표시 하 고 다른 작업을 취소 하거나 대화 상자를 제거 하지 않고 반환 하는 사용자 수 있습니다.  
  
 A `CDialog` 개체 대화 상자 템플릿의 조합입니다 a `CDialog`\-클래스를 파생 합니다.  대화 상자 편집기를 사용 하 여 대화 상자 템플릿을 만들고에서 리소스를 저장 하 고 클래스 추가 마법사를 사용 하 여 파생 클래스를 만들려면 `CDialog`.  
  
 다른 창 처럼 대화 상자에서 Windows에서 메시지를 받습니다.  대화 상자에 사용자 사용자 대화 상자와 상호 작용 하는 방법 이므로 대화 상자의 컨트롤에서 알림 메시지 처리에 특히 관심을 가집니다.  속성 창을 사용 하 선택 핸들 및이 메시지를 적절 한 메시지 맵 항목 및 메시지 처리기 멤버 함수를 클래스에 자동으로 추가 됩니다.  응용 프로그램별 코드 처리기 멤버 함수를 작성 해야 합니다.  
  
 원한다 면 하면 항상 메시지 맵 엔트리와 멤버 함수를 직접 작성할 수 있습니다.  
  
 가장 간단한 대화 상자를 제외한 모든에서 멤버 변수 추가 하 여 파생 된 대화 상자 클래스 대화 상자 컨트롤에 사용자가 입력 한 데이터를 저장 하거나 사용자에 대 한 데이터를 표시 합니다.  변수 추가 마법사를 사용 하면 멤버 변수를 만들고 해당 컨트롤에 연결 수 있습니다.  동시에 변수 형식과 각 변수에 대 한 값의 허용 범위를 선택합니다.  코드 마법사를 파생된 대화 상자 클래스에 멤버 변수를 추가합니다.  
  
 데이터 맵은 멤버 변수와 대화 상자의 컨트롤 사이 데이터 교환을 자동으로 처리 하도록 생성 됩니다.  데이터 맵 컨트롤 대화 상자에 적절 한 값을 초기화 하 고 데이터를 검색할 데이터의 유효성을 검사 하는 기능을 제공 합니다.  
  
 모달 대화 상자를 만들려면 개체를 파생된 대화 상자 클래스에 대 한 생성자를 사용 하 여 스택에 생성 한 다음 호출 `DoModal` 대화 창 및 컨트롤을 만들 수 있습니다.  모덜리스 대화 상자를 만들 경우 전화  **만들기** 대화 상자 클래스의 생성자에서.  
  
 서식 파일에서 메모리를 사용 하 여 만들 수도 있습니다는  [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) 데이터 구조에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  구성 후에 `CDialog` 개체, 호출  [CreateIndirect](../Topic/CDialog::CreateIndirect.md) 는 모덜리스 폼을 만들려면 대화 상자 또는 호출  [InitModalIndirect](../Topic/CDialog::InitModalIndirect.md) 및  [DoModal](../Topic/CDialog::DoModal.md) 모달 대화 상자를 만듭니다.  
  
 재정의에서 데이터 교환 및 유효성 검사 지도 작성 `CWnd::DoDataExchange` 새 대화 상자 클래스에 추가 합니다.  참조는  [DoDataExchange](../Topic/CWnd::DoDataExchange.md) 멤버 함수에서 `CWnd` 교환 및 유효성 검사 기능에 대 한 자세한 내용은.  
  
 프로그래머와 프레임 워크 호출 `DoDataExchange` 호출을 통해 간접적으로  [CWnd::UpdateData](../Topic/CWnd::UpdateData.md).  
  
 프레임 워크 호출 `UpdateData` 사용자가 모달 대화 상자를 닫으려면 \[확인\] 단추를 클릭할 때.  \(취소 단추를 클릭 하면 데이터가 검색 되지 않습니다.\) 기본 구현의  [OnInitDialog](../Topic/CDialog::OnInitDialog.md) 도 호출 `UpdateData` 컨트롤의 초기 값을 설정 합니다.  일반적으로 재정의 `OnInitDialog` 추가 컨트롤을 초기화 합니다.  `OnInitDialog`모든 대화 상자 컨트롤을 만들고 방금 전에 대화 상자가 표시 됩니다 후에 호출 됩니다.  
  
 호출할 수 있는 `CWnd::UpdateData` 모달 또는 모덜리스 대화 상자를 실행 하는 동안 언제 든 지.  
  
 대화 상자를 직접 개발 하는 경우 파생 된 대화 상자 클래스에 사용자가 직접 필요한 멤버 변수를 추가 하 고 이러한 값을 가져오거나 설정 하는 멤버 함수를 추가 합니다.  
  
 확인 또는 취소 단추를 누를 때 또는 코드를 호출 하면 자동으로 모달 대화 상자를 닫습니다는 `EndDialog` 멤버 함수입니다.  
  
 모덜리스 대화 상자를 구현 하면 항상 재정의 `OnCancel` 멤버 함수 및 호출 `DestroyWindow` 에서 내.  기본 클래스를 호출 하지 않습니다 `CDialog::OnCancel`호출 하기 때문에, `EndDialog`에 대화 상자가 표시 되지 않게 됩니다 하지만 삭제 하지는 않습니다.  또한 재정의 해야 `PostNcDestroy` 삭제 하려면 모덜리스 대화 상자에 대 한  **이**, 모덜리스 대화 상자에 일반적으로 할당 된 것 이므로  **새**.  모달 대화 상자 프레임에 일반적으로 생성 되 고 필요 하지 않은 `PostNcDestroy` 정리 합니다.  
  
 에 대 한 자세한 내용은 `CDialog`을 참조 하십시오.  
  
-   [대화 상자](../../mfc/dialog-boxes.md)  
  
-   기술 자료 문서 Q262954: 방법: 스크롤 막대와 조 대화 상자 만들기  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDialog`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [MFC 샘플 DLGCBR32](../../top/visual-cpp-samples.md)   
 [DLGTEMPL MFC 샘플](../../top/visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)