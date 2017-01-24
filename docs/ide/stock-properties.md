---
title: "스톡 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "스톡 속성"
  - "스톡 속성, 스톡 속성 정보"
ms.assetid: a89fc454-0b8e-447a-9033-4c8af46a24d9
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 스톡 속성
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[속성 추가 마법사](../ide/idl-attributes-add-property-wizard.md)를 사용하여 속성을 MFC dispinterface에 추가하는 경우 마법사의 [이름](../ide/names-add-property-wizard.md) 페이지에 있는 **속성 이름**목록에서 스톡 속성을 선택할 수 있습니다.  속성은 다음과 같습니다.  
  
|속성 이름|설명|  
|-----------|--------|  
|**모양**|컨트롤의 모양을 결정하는 값을 반환하거나 설정합니다.  컨트롤의 **Appearance** 속성에는 3차원 디스플레이 효과가 포함되거나 생략될 수 있습니다.  이 속성은 앰비언트 읽기\/쓰기 속성입니다.|  
|`BackColor`|컨트롤의 앰비언트 `BackColor` 속성을 색상표\(RGB\) 색이나 미리 정의된 시스템 색으로 설정하거나 반환합니다.  기본적으로 이 속성 값은 컨트롤에 있는 컨테이너의 전경색에 해당합니다.  이 속성은 앰비언트 읽기\/쓰기 속성입니다.|  
|`BorderStyle`|컨트롤의 테두리 스타일을 반환하거나 설정합니다.  이 속성은 읽기\/쓰기 속성입니다.|  
|**Caption**|컨트롤의 **Caption** 속성을 반환하거나 설정합니다.  이 캡션이 창의 제목이 됩니다.  **Caption**에는 **멤버 변수** 구현 형식이 없습니다.|  
|**Enabled**|컨트롤의 **Enabled** 속성을 반환하거나 설정합니다.  이 속성이 설정된 컨트롤은 사용자가 생성한 이벤트에 응답할 수 있습니다.|  
|**글꼴**|컨트롤의 앰비언트 글꼴을 반환하거나 설정합니다.  컨트롤에 글꼴이 없으면 Null입니다.|  
|`ForeColor`|컨트롤의 앰비언트 `ForeColor` 속성을 반환하거나 설정합니다.|  
|**hWnd**|컨트롤의 **hWnd** 속성을 반환하거나 설정합니다.  **hWnd**에는 **멤버 변수** 구현 형식이 없습니다.|  
|**ReadyState**|컨트롤의 **ReadyState** 속성을 반환하거나 설정합니다.  컨트롤은 uninitialized, initialized, loading, interactive, complete 중 한 가지입니다.  자세한 내용은 *Internet SDK*에서 [READYSTATE](https://msdn.microsoft.com/en-us/library/aa768362.aspx)를 참조하십시오.|  
|**Text**|컨트롤에 포함된 텍스트를 반환하거나 설정합니다.  **Text**에는 **멤버 변수** 구현 형식이 없습니다.|  
  
## 참고 항목  
 [속성 추가](../ide/adding-a-property-visual-cpp.md)   
 [속성 추가 마법사, IDL 특성](../ide/idl-attributes-add-property-wizard.md)