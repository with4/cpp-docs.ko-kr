---
title: "CVSListBox Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CVSListBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CVSListBox class"
  - "CVSListBox::PreTranslateMessage method"
ms.assetid: c79be7b4-46ed-4af8-a41e-68962782d8ef
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CVSListBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CVSListBox` 클래스는 편집할 수 있는 목록 컨트롤을 지원 합니다.  
  
## 구문  
  
```  
class CVSListBox : public CVSListBoxBase  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CVSListBox::CVSListBox](../Topic/CVSListBox::CVSListBox.md)|`CVSListBox` 개체를 생성합니다.|  
|`CVSListBox::~CVSListBox`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CVSListBox::AddItem](../Topic/CVSListBox::AddItem.md)|목록 컨트롤에 문자열을 추가합니다.  \(재정의 `CVSListBoxBase::AddItem`.\)|  
|[CVSListBox::EditItem](../Topic/CVSListBox::EditItem.md)|List 컨트롤 항목의 텍스트 편집 작업을 시작합니다.  \(재정의 `CVSListBoxBase::EditItem`.\)|  
|[CVSListBox::GetCount](../Topic/CVSListBox::GetCount.md)|편집할 수 있는 목록 컨트롤에서 문자열을 검색합니다.  \(재정의 `CVSListBoxBase::GetCount`.\)|  
|[CVSListBox::GetItemData](../Topic/CVSListBox::GetItemData.md)|편집할 수 있는 목록 컨트롤 항목과 연결 되는 응용 프로그램별 32 비트 값을 검색 합니다.  \(재정의 `CVSListBoxBase::GetItemData`.\)|  
|[CVSListBox::GetItemText](../Topic/CVSListBox::GetItemText.md)|편집할 수 있는 목록 항목 컨트롤의 텍스트를 검색합니다.  \(재정의 `CVSListBoxBase::GetItemText`.\)|  
|[CVSListBox::GetSelItem](../Topic/CVSListBox::GetSelItem.md)|편집할 수 있는 목록 컨트롤에서 현재 선택한 항목의 인덱스를 검색합니다.  \(재정의 `CVSListBoxBase::GetSelItem`.\)|  
|`CVSListBox::PreTranslateMessage`|창 메시지를 디스패치하기 전에 변환의  [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및  [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 기능입니다.  자세한 내용과 메서드 구문 [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).  \(재정의 `CVSListBoxBase::PreTranslateMessage`.\)|  
|[CVSListBox::RemoveItem](../Topic/CVSListBox::RemoveItem.md)|편집할 수 있는 목록 컨트롤에서 항목을 제거합니다.  \(재정의 `CVSListBoxBase::RemoveItem`.\)|  
|[CVSListBox::SelectItem](../Topic/CVSListBox::SelectItem.md)|편집할 수 있는 목록 컨트롤 문자열을 선택합니다.  \(재정의 `CVSListBoxBase::SelectItem`.\)|  
|[CVSListBox::SetItemData](../Topic/CVSListBox::SetItemData.md)|응용 프로그램별 32 비트 값을 편집할 수 있는 목록 컨트롤 항목과 연결합니다.  \(재정의 `CVSListBoxBase::SetItemData`.\)|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CVSListBox::GetListHwnd](../Topic/CVSListBox::GetListHwnd.md)|현재 포함 된 목록 뷰 컨트롤에는 핸들을 반환합니다.|  
  
## 설명  
 `CVSListBox` 클래스 만들기, 수정, 삭제 또는 목록 컨트롤에 있는 항목을 다시 정렬할 수 있게 하는 편집 단추를 제공 합니다.  
  
 다음 그림을 편집할 수 있는 목록 컨트롤입니다.  제목이 "Item2", 두 번째 목록 항목을 편집할 수 있도록 선택 됩니다.  
  
 ![CVSListBox 컨트롤](../../mfc/reference/media/cvslistbox.png "cvslistbox")  
  
 편집할 수 있는 목록 컨트롤을 추가 하려면 리소스 편집기를 사용 하는 경우는  **도구** 편집기 창 편집 가능한 미리 정의 된 목록 컨트롤을 제공 하지 않습니다.  같은 정적 컨트롤을 대신 추가 된  **그룹 상자** 제어 합니다.  프레임 워크 정적 컨트롤 자리 표시자로 사용 하 여 편집할 수 있는 목록 컨트롤의 위치와 크기를 지정 합니다.  
  
 대화 상자 템플릿에 편집 가능한 목록 컨트롤을 사용 하려면 선언에 `CVSListBox` 변수 대화 상자 클래스에 있습니다.  변수 및 컨트롤 간의 데이터 교환을 지원 하려면 정의 `DDX_Control` 매크로 항목에는 `DoDataExchange` 메서드는 대화 상자.  기본적으로 편집할 수 있는 목록 컨트롤 편집 단추 없이 만들어집니다.  상속 된 사용 [CVSListBoxBase::SetStandardButtons](http://msdn.microsoft.com/ko-kr/129e530f-97e9-42eb-b128-371c2a5686ba) 편집 단추를 사용 하는 방법.  
  
 자세한 내용은 Samples 디렉터리는 `New Controls` 샘플, Page3.cpp 및 Page3.h 파일.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CStatic](../../mfc/reference/cstatic-class.md)  
  
 `CVSListBoxBase`  
  
 [CVSListBox](../../mfc/reference/cvslistbox-class.md)  
  
## 요구 사항  
 **헤더:** afxvslistbox.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)