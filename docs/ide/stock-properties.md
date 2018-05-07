---
title: 스톡 속성 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- stock properties, about stock properties
- stock properties
ms.assetid: a89fc454-0b8e-447a-9033-4c8af46a24d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3586fb33c30148c870b096d0d49a41d7ad8c6c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="stock-properties"></a>스톡 속성
사용 하 여 MFC dispinterface 속성을 추가 하는 경우는 [속성 추가 마법사](../ide/idl-attributes-add-property-wizard.md)에서 스톡 속성을 선택할 수는 **속성 이름** 목록에 [이름](../ide/names-add-property-wizard.md) 의 페이지는 마법사입니다. 속성은 다음과 같습니다.  
  
|속성 이름|설명|  
|-------------------|-----------------|  
|**모양**|반환 하거나 컨트롤의 모양을 결정 하는 값을 설정 합니다. 컨트롤의 **모양** 속성 포함 또는 3 차원 표시 효과 생략할 수 있습니다. 앰비언트 읽기/쓰기 속성입니다.|  
|`BackColor`|반환 하거나 컨트롤의 앰비언트 설정 `BackColor` 색상표 RGB 색 이나 미리 정의 된 시스템 색 속성입니다. 기본적으로 해당 값은 컨트롤 컨테이너의 전경색에 해당합니다. 앰비언트 읽기/쓰기 속성입니다.|  
|`BorderStyle`|반환 하거나 컨트롤의 테두리 스타일을 설정 합니다. 이 속성은 읽기/쓰기 속성입니다.|  
|**캡션**|반환 하거나 컨트롤의 설정 **캡션** 속성입니다. 캡션이 창의 제목이 됩니다. **캡션** 아무런 **멤버 변수** 구현 형식입니다.|  
|**사용**|반환 하거나 컨트롤의 설정 **Enabled** 속성입니다. 사용 가능한 컨트롤은 사용자가 만든 이벤트에 응답할 수 있습니다.|  
|**글꼴**|반환 하거나 컨트롤의 앰비언트 글꼴을 설정 합니다. 컨트롤에 글꼴이 없으면 null입니다.|  
|`ForeColor`|반환 하거나 컨트롤의 앰비언트 설정 `ForeColor` 속성입니다.|  
|**hWnd**|반환 하거나 컨트롤의 설정 **hWnd** 속성입니다. **hWnd** 아무런 **멤버 변수** 구현 형식입니다.|  
|**ReadyState**|반환 하거나 컨트롤의 설정 **ReadyState** 속성입니다. 컨트롤이는 초기화 되지 않은, 초기화, 로드, 대화형 또는 완료 될 수 있습니다. 참조 [READYSTATE](https://msdn.microsoft.com/en-us/library/aa768362.aspx) 에 *인터넷 SDK* 자세한 정보에 대 한 합니다.|  
|**텍스트**|컨트롤에 포함 된 텍스트를 설정 하거나 반환 합니다. **텍스트** 아무런 **멤버 변수** 구현 형식입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [속성 추가](../ide/adding-a-property-visual-cpp.md)   
 [속성 추가 마법사, IDL 특성](../ide/idl-attributes-add-property-wizard.md)