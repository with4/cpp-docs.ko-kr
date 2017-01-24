---
title: "CMFCDynamicLayout 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: c2df2976-f049-47fc-9cf0-abe3e01948bc
caps.latest.revision: 16
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDynamicLayout 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사용자가 창의 크기를 조정할 때 창에서 컨트롤이 이동하고 컨트롤의 크기가 조정되는 방식을 지정합니다.  
  
## 구문  
  
```  
class CMFCDynamicLayout : public CObject  
```  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|`CMFCDynamicLayout::CMFCDynamicLayout`|`CMFCDynamicLayout` 개체를 생성합니다.|  
|`CMFCDynamicLayout::~CMFCDynamicLayout`|소멸자|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCDynamicLayout::AddItem](../Topic/CMFCDynamicLayout::AddItem.md)|자식 창\(일반적으로 컨트롤\)을 동적 레이아웃 관리자가 제어하는 창 목록에 추가합니다.|  
|[CMFCDynamicLayout::Adjust](../Topic/CMFCDynamicLayout::Adjust.md)|자식 창\(일반적으로 컨트롤\)을 동적 레이아웃 관리자가 제어하는 창 목록에 추가합니다.|  
|[CMFCDynamicLayout::Create](../Topic/CMFCDynamicLayout::Create.md)|호스트 창을 저장하고 유효성을 검사합니다.|  
|[CMFCDynamicLayout::GetHostWnd](../Topic/CMFCDynamicLayout::GetHostWnd.md)|호스트 창에 대한 포인터를 반환합니다.|  
|[CMFCDynamicLayout::GetMinSize](../Topic/CMFCDynamicLayout::GetMinSize.md)|레이아웃이 그 이하로 조정되지 않는 창 크기를 반환합니다.|  
|[CMFCDynamicLayout::GetWindowRect](../Topic/CMFCDynamicLayout::GetWindowRect.md)|창의 현재 클라이언트 영역에 대한 사각형을 검색합니다.|  
|[CMFCDynamicLayout::HasItem](../Topic/CMFCDynamicLayout::HasItem.md)|자식 컨트롤이 동적 레이아웃에 추가되었는지 확인합니다.|  
|[CMFCDynamicLayout::IsEmpty](../Topic/CMFCDynamicLayout::IsEmpty.md)|동적 레이아웃에 추가된 자식 창이 없는지 확인합니다.|  
|[CMFCDynamicLayout::LoadResource](../Topic/CMFCDynamicLayout::LoadResource.md)|AFX\_DIALOG\_LAYOUT 리소스에서 동적 레이아웃을 읽고 레이아웃을 호스트 창에 적용합니다.|  
|static [CMFCDynamicLayout::MoveHorizontal](../Topic/CMFCDynamicLayout::MoveHorizontal.md)|사용자가 호스팅 창의 크기를 조정할 때 자식 컨트롤이 가로로 얼마나 이동하는지를 정의하는 [MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md) 값을 가져옵니다.|  
|static [CMFCDynamicLayout::MoveHorizontalAndVertical](../Topic/CMFCDynamicLayout::MoveHorizontalAndVertical.md)|사용자가 호스팅 창의 크기를 조정할 때 자식 컨트롤이 가로로 얼마나 이동하는지를 정의하는 [MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md) 값을 가져옵니다.|  
|static [CMFCDynamicLayout::MoveNone](../Topic/CMFCDynamicLayout::MoveNone.md)|자식 컨트롤의 세로 또는 가로 동작이 없음을 나타내는 [MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md) 값을 가져옵니다.|  
|static [CMFCDynamicLayout::MoveVertical](../Topic/CMFCDynamicLayout::MoveVertical.md)|사용자가 호스팅 창의 크기를 조정할 때 자식 컨트롤이 세로로 얼마나 이동하는지를 정의하는 [MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md) 값을 가져옵니다.|  
|[CMFCDynamicLayout::SetMinSize](../Topic/CMFCDynamicLayout::SetMinSize.md)|레이아웃이 그 이하로 조정되지 않는 창 크기를 설정합니다.|  
|static [CMFCDynamicLayout::SizeHorizontal](../Topic/CMFCDynamicLayout::SizeHorizontal.md)|사용자가 호스팅 창의 크기를 조정할 때 자식 컨트롤이 가로로 얼마나 크기 조정되는지를 정의하는 [SizeSettings](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md) 값을 가져옵니다.|  
|static [CMFCDynamicLayout::SizeHorizontalAndVertical](../Topic/CMFCDynamicLayout::SizeHorizontalAndVertical.md)|사용자가 호스팅 창의 크기를 조정할 때 자식 컨트롤이 가로로 얼마나 크기 조정되는지를 정의하는 [SizeSettings](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md) 값을 가져옵니다.|  
|static [CMFCDynamicLayout::SizeNone](../Topic/CMFCDynamicLayout::SizeNone.md)|자식 컨트롤의 크기에 변경이 없음을 나타내는 [SizeSettings](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md) 값을 가져옵니다.|  
|static [CMFCDynamicLayout::SizeVertical](../Topic/CMFCDynamicLayout::SizeVertical.md)|사용자가 호스팅 창의 크기를 조정할 때 자식 컨트롤이 세로로 얼마나 크기 조정되는지를 정의하는 [SizeSettings](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md) 값을 가져옵니다.|  
  
## 중첩 형식  
  
|이름|설명|  
|--------|--------|  
|[CMFCDynamicLayout::MoveSettings 구조체](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md)|동적 레이아웃의 컨트롤에 대한 이동 데이터를 캡슐화합니다.|  
|[CMFCDynamicLayout::SizeSettings 구조체](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md)|동적 레이아웃의 컨트롤에 대한 크기 변경 데이터를 캡슐화합니다.|  
  
## 설명  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCDynamicLayout](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
## 요구 사항  
 **헤더:** afxlayout.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)