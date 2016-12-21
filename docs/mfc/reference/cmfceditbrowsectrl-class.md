---
title: "CMFCEditBrowseCtrl Class | Microsoft Docs"
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
  - "CMFCEditBrowseCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCEditBrowseCtrl class"
  - "CMFCEditBrowseCtrl constructor"
  - "CMFCEditBrowseCtrl::PreTranslateMessage method"
ms.assetid: 69cfd886-3d35-4bee-8901-7c88fcf9520f
caps.latest.revision: 33
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCEditBrowseCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCEditBrowseCtrl` 클래스 편집 찾아보기 찾아보기 단추가 선택적으로 포함 하는 편집 가능한 텍스트 상자에는 컨트롤을 지원 합니다.  찾아보기 단추를 클릭할 때 컨트롤 사용자 지정 작업을 수행 하거나 파일 브라우저 또는 브라우저 폴더에 있는 표준 대화 상자를 표시 합니다.  
  
## 구문  
  
```  
class CMFCEditBrowseCtrl : public CEdit  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|`CMFCEditBrowseCtrl::CMFCEditBrowseCtrl`|기본 생성자입니다.|  
|`CMFCEditBrowseCtrl::~CMFCEditBrowseCtrl`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCEditBrowseCtrl::EnableBrowseButton](../Topic/CMFCEditBrowseCtrl::EnableBrowseButton.md)|\(숨깁니다\)를 사용 하거나 \[찾아보기\] 단추.|  
|[CMFCEditBrowseCtrl::EnableFileBrowseButton](../Topic/CMFCEditBrowseCtrl::EnableFileBrowseButton.md)|찾아보기 단추를 사용 하 고 찾아보기 편집 컨트롤에  *파일 찾아보기* 모드.|  
|[CMFCEditBrowseCtrl::EnableFolderBrowseButton](../Topic/CMFCEditBrowseCtrl::EnableFolderBrowseButton.md)|찾아보기 단추를 사용 하 고 찾아보기 편집 컨트롤에  *폴더 찾아보기* 모드.|  
|[CMFCEditBrowseCtrl::GetMode](../Topic/CMFCEditBrowseCtrl::GetMode.md)|현재 찾아보기 모드를 반환합니다.|  
|[CMFCEditBrowseCtrl::OnAfterUpdate](../Topic/CMFCEditBrowseCtrl::OnAfterUpdate.md)|편집 컨트롤 찾아보기 찾아보기 작업의 결과를 업데이트 한 후 프레임 워크에 의해 호출 됩니다.|  
|[CMFCEditBrowseCtrl::OnBrowse](../Topic/CMFCEditBrowseCtrl::OnBrowse.md)|사용자가 찾아보기 단추를 클릭 한 후 프레임 워크에 의해 호출 됩니다.|  
|[CMFCEditBrowseCtrl::OnChangeLayout](../Topic/CMFCEditBrowseCtrl::OnChangeLayout.md)|현재 찾아보기 편집 컨트롤을 다시 그립니다.|  
|[CMFCEditBrowseCtrl::OnDrawBrowseButton](../Topic/CMFCEditBrowseCtrl::OnDrawBrowseButton.md)|찾아보기 단추를 그리려면 프레임 워크에서 호출 됩니다.|  
|[CMFCEditBrowseCtrl::OnIllegalFileName](../Topic/CMFCEditBrowseCtrl::OnIllegalFileName.md)|잘못 된 파일 이름 편집 컨트롤에 입력할 때 프레임 워크에 의해 호출 됩니다.|  
|`CMFCEditBrowseCtrl::PreTranslateMessage`|창 메시지를 디스패치하기 전에 변환의  [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및  [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 기능입니다.  구문 및 자세한 정보를 참조 하십시오. [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).|  
|[CMFCEditBrowseCtrl::SetBrowseButtonImage](../Topic/CMFCEditBrowseCtrl::SetBrowseButtonImage.md)|사용자 지정 이미지에 대 한 찾아보기 단추를 설정합니다.|  
  
## 설명  
 찾아보기 편집 컨트롤을 사용 하 여 파일 또는 폴더 이름을 선택 합니다.  원하는 경우 컨트롤을 대화 상자를 표시 하는 같은 작업을 수행할 수 있습니다.  표시 하거나 \[찾아보기\] 단추를 표시 하 고 단추에 사용자 지정 레이블 또는 이미지를 적용할 수 있습니다.  
  
 *찾아보기 모드로* 의 찾아보기 편집 찾아보기 단추 표시 여부 및 단추를 눌렀을 때 어떤 동작을 발생 컨트롤을 결정 합니다.  자세한 내용은  [GetMode](../Topic/CMFCEditBrowseCtrl::GetMode.md) 메서드.  
  
 `CMFCEditBrowseCtrl` 클래스는 다음 모드를 지원 합니다.  
  
 `custom mode`  
 \[찾아보기\] 단추를 클릭할 때 사용자 지정 작업이 수행 됩니다.  예를 들어, 응용 프로그램 특정 대화 상자를 표시할 수 있습니다.  
  
 `file mode`  
 \[찾아보기\] 단추를 클릭할 때 표준 파일 선택 대화 상자가 표시 됩니다.  
  
 `folder mode`  
 \[찾아보기\] 단추를 클릭할 때 표준 폴더 선택 대화 상자가 표시 됩니다.  
  
## 찾아보기 편집 컨트롤을 지정 하는 방법:  
 찾아보기 편집 컨트롤을 응용 프로그램에 통합 하려면 다음 단계를 수행 하십시오.  
  
1.  사용자 지정 모드를 구현 하려면 클래스에서 파생 되는 `CMFCEditBrowseCtrl` 클래스 및 재정의 하 고 있는 [CMFCEditBrowseCtrl::OnBrowse](../Topic/CMFCEditBrowseCtrl::OnBrowse.md) 메서드.  재정의 된 메서드를 사용자 지정 탐색 기능을 실행 하 고 찾아보기 편집 컨트롤을 결과를 업데이트 합니다.  
  
2.  하나 포함 된 `CMFCEditBrowseCtrl` 또는 파생된 편집 찾아보기 컨트롤 개체의 부모 창 개체에.  
  
3.  사용 하는 경우는  **클래스 마법사** 편집 컨트롤 대화 상자를 만들려면 추가 \(`CEdit`\) 대화 상자 폼에.  또한 액세스 제어 헤더 파일에 변수를 추가 합니다.  헤더 파일에서 변수 유형을 변경 `CEdit` 에 `CMFCEditBrowseCtrl`.  찾아보기 편집 컨트롤이 자동으로 만들어집니다.  사용 하지 않는 경우는  **클래스 마법사**, 추가 `CMFCEditBrowseCtrl` 헤더 파일 및 다음 호출 변수는 `Create` 메서드.  
  
4.  찾아보기 편집 컨트롤을 대화 상자에 추가 하는 경우 사용 하는  **클래스 마법사** 데이터 교환을 위한 도구.  
  
5.  호출 하는  [EnableFolderBrowseButton](../Topic/CMFCEditBrowseCtrl::EnableFolderBrowseButton.md),  [EnableFileBrowseButton](../Topic/CMFCEditBrowseCtrl::EnableFileBrowseButton.md), 또는  [EnableBrowseButton](../Topic/CMFCEditBrowseCtrl::EnableBrowseButton.md) 찾아보기 모드를 설정 하 고 \[찾아보기\] 단추를 표시 하는 방법.  호출을  [GetMode](../Topic/CMFCEditBrowseCtrl::GetMode.md) 메서드는 현재 찾아보기 모드를 얻을 수 있습니다.  
  
6.  찾아보기 단추를 사용자 지정 이미지를 제공 하기 위해 호출 하는  [SetBrowseButtonImage](../Topic/CMFCEditBrowseCtrl::SetBrowseButtonImage.md) 메서드 또는 재정의  [OnDrawBrowseButton](../Topic/CMFCEditBrowseCtrl::OnDrawBrowseButton.md) 메서드.  
  
7.  찾아보기 편집 컨트롤에서 찾아보기 단추를 제거 하려면 전화는  [EnableBrowseButton](../Topic/CMFCEditBrowseCtrl::EnableBrowseButton.md) 메서드로 `bEnable` 매개 변수를 설정 `FALSE`.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCEditBrowseCtrl](../../mfc/reference/cmfceditbrowsectrl-class.md)  
  
## 예제  
 다음 예제에서는 두 가지 방법을 사용 하는 방법의 `CMFCEditBrowseCtrl` 클래스: `EnableFolderBrowseButton` 및 `EnableFileBrowseButton`.  이 이때의 일부인의  [새 컨트롤 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#6](../../mfc/reference/codesnippet/CPP/cmfceditbrowsectrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#7](../../mfc/reference/codesnippet/CPP/cmfceditbrowsectrl-class_2.cpp)]  
  
## 요구 사항  
 **헤더:** afxeditbrowsectrl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)