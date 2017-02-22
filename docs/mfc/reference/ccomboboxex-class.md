---
title: "CComboBoxEx Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComboBoxEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComboBoxEx class"
  - "콤보 상자[C++], CComboBoxEx class"
  - "common controls [C++], extended combo boxes"
  - "extended combo boxes, CComboBoxEx class"
  - "Internet Explorer 4.0 common controls"
  - "Windows common controls [C++], extended combo boxes"
ms.assetid: 33ca960a-2409-478c-84a4-a2ee8ecfe8f7
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CComboBoxEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

콤보 상자 컨트롤은 이미지 목록에 대 한 지원을 제공 하 여 확장 합니다.  
  
## 구문  
  
```  
class CComboBoxEx : public CComboBox  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CComboBoxEx::CComboBoxEx](../Topic/CComboBoxEx::CComboBoxEx.md)|`CComboBoxEx` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComboBoxEx::Create](../Topic/CComboBoxEx::Create.md)|콤보 상자를 만들고 연결 하는 `CComboBoxEx` 개체입니다.|  
|[CComboBoxEx::CreateEx](../Topic/CComboBoxEx::CreateEx.md)|지정한 Windows 확장된 스타일 콤보 상자를 만들고이에 연결 된  **ComboBoxEx** 개체입니다.|  
|[CComboBoxEx::DeleteItem](../Topic/CComboBoxEx::DeleteItem.md)|항목에서 제거 된  **ComboBoxEx** 제어 합니다.|  
|[CComboBoxEx::GetComboBoxCtrl](../Topic/CComboBoxEx::GetComboBoxCtrl.md)|자식 콤보 상자 컨트롤에 대 한 포인터를 검색합니다.|  
|[CComboBoxEx::GetEditCtrl](../Topic/CComboBoxEx::GetEditCtrl.md)|편집 컨트롤 부분에 대 한 핸들 검색을  **ComboBoxEx** 제어 합니다.|  
|[CComboBoxEx::GetExtendedStyle](../Topic/CComboBoxEx::GetExtendedStyle.md)|검색에 사용 되는 확장된 스타일을  **ComboBoxEx** 제어 합니다.|  
|[CComboBoxEx::GetImageList](../Topic/CComboBoxEx::GetImageList.md)|지정 된 이미지 목록에 대 한 포인터를 검색에  **ComboBoxEx** 제어 합니다.|  
|[CComboBoxEx::GetItem](../Topic/CComboBoxEx::GetItem.md)|검색 항목에 대 한 정보는 지정 된  **ComboBoxEx** 항목.|  
|[CComboBoxEx::HasEditChanged](../Topic/CComboBoxEx::HasEditChanged.md)|결정의 내용을 변경 하는 경우는  **ComboBoxEx** 입력 하 여 컨트롤을 편집 합니다.|  
|[CComboBoxEx::InsertItem](../Topic/CComboBoxEx::InsertItem.md)|새 항목을 삽입 하는  **ComboBoxEx** 제어 합니다.|  
|[CComboBoxEx::SetExtendedStyle](../Topic/CComboBoxEx::SetExtendedStyle.md)|확장된 스타일에서 설정 하는  **ComboBoxEx** 컨트롤.|  
|[CComboBoxEx::SetImageList](../Topic/CComboBoxEx::SetImageList.md)|이미지 목록에 대해 설정 하는  **ComboBoxEx** 제어 합니다.|  
|[CComboBoxEx::SetItem](../Topic/CComboBoxEx::SetItem.md)|항목에 대 한 속성 설정의  **ComboBoxEx** 제어 합니다.|  
|[CComboBoxEx::SetWindowTheme](../Topic/CComboBoxEx::SetWindowTheme.md)|비주얼 스타일의 확장된 콤보 상자 컨트롤을 설정합니다.|  
  
## 설명  
 사용 하 여 `CComboBoxEx` 콤보 상자 컨트롤을 만들려면 사용자 더 이상 이미지 그리기 코드를 직접 구현 해야 합니다.  대신 사용 하 여 `CComboBoxEx` 이미지 목록에서 이미지를 액세스할 수 있습니다.  
  
## 이미지 목록 지원  
 표준 콤보 상자에서 콤보 상자의 소유자 콤보 상자의 소유자 그리기 컨트롤을 만들어 이미지 그리기에 대 한 책임입니다.  사용 하는 경우 `CComboBoxEx`, 그리기 스타일을 설정 하지 않아도  **CBS\_OWNERDRAWFIXED** 및  **CBS\_HASSTRINGS** 는 내포 되어 있기 때문에.  그렇지 않으면 그리기 작업을 수행 하는 코드를 작성 해야 합니다.  A `CComboBoxEx` 컨트롤 지원 항목 당 최대 3 개의 이미지: 선택된 된 상태는 선택 되지 않은 상태 및 오버레이 이미지 하나 하나.  
  
## 스타일  
 `CComboBoxEx`스타일 지원  **CBS\_SIMPLE**,  **CBS\_DROPDOWN**,  **CBS\_DROPDOWNLIST**, 및  **WS\_CHILD**.  창을 만들 때 전달 된 모든 스타일은 컨트롤에서 무시 됩니다.  창이 만들어지면 호출 하 여 상자 스타일 다른 콤보를 제공할 수 있는 `CComboBoxEx` 멤버 함수  [SetExtendedStyle](../Topic/CComboBoxEx::SetExtendedStyle.md).  이러한 스타일을 사용 하면 다음과 같은 작업을 수행할 수 있습니다.  
  
-   문자열 검색에서 대\/소문자 구분 목록 집합.  
  
-   슬래시 \('\/'\)를 사용 하 여 콤보 상자 컨트롤 백슬래시 \('\\ '\), 및 마침표 \('. '\) 단어 구분 기호로.  이 사용자가 word에서 바로 가기 키 CTRL \+ 화살표를 사용 하 여 이동할 수 있습니다.  
  
-   콤보 상자 컨트롤을 표시 하거나 이미지를 표시 하도록 설정 합니다.  이미지가 표시 되지 않으면 콤보 상자 이미지 수용 텍스트 들여쓰기를 제거할 수 있습니다.  
  
-   포함 된 큰 콤보 상자를 클립 있도록 크기를 조정 등 좁은 콤보 상자 컨트롤을 만듭니다.  
  
 이러한 스타일 플래그에 추가로 설명 된  [CComboBoxEx를 사용 하 여](../../mfc/using-ccomboboxex.md).  
  
## 항목 보존 및 콜백 항목 특성  
 Win32 구조로 저장 항목 및 이미지, 들여쓰기 값 및 텍스트 문자열에 대 한 인덱스 항목 정보를  [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746)에 설명 된 대로, 여 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  또한 구조 콜백 플래그에 해당 멤버를 포함 합니다.  
  
 자세한 개념 토론을 참조 하십시오.  [CComboBoxEx를 사용 하 여](../../mfc/using-ccomboboxex.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 `CComboBoxEx`  
  
## 요구 사항  
 **헤더:**  afxcmn.h  
  
## 참고 항목  
 [MFCIE MFC 샘플](../../top/visual-cpp-samples.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)