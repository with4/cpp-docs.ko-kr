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
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33335444"
---
# <a name="stock-properties"></a>스톡 속성
[속성 추가 마법사](../ide/idl-attributes-add-property-wizard.md)를 사용하여 MFC dispinterface에 속성을 추가하는 경우 마법사의 [이름](../ide/names-add-property-wizard.md) 페이지에 있는 **속성 이름** 목록에서 스톡 속성을 선택할 수 있습니다. 속성은 다음과 같습니다.  
  
|속성 이름|설명|  
|-------------------|-----------------|  
|**모양**|컨트롤의 모양을 결정하는 값을 반환하거나 설정합니다. 컨트롤의 **모양** 속성은 3차원 표시 효과를 포함하거나 생략할 수 있습니다. 앰비언트 읽기/쓰기 속성입니다.|  
|`BackColor`|색상표(RGB) 색 또는 미리 정의된 시스템 색에 대한 컨트롤의 앰비언트 `BackColor` 속성을 반환하거나 설정합니다. 기본적으로 해당 값은 컨트롤 컨테이너의 전경색에 해당합니다. 앰비언트 읽기/쓰기 속성입니다.|  
|`BorderStyle`|컨트롤의 테두리 스타일을 반환하거나 설정합니다. 읽기/쓰기 속성입니다.|  
|**캡션**|컨트롤의 **캡션** 속성을 반환하거나 설정합니다. 캡션은 창의 제목입니다. **캡션**에는 **멤버 변수** 구현 형식이 없습니다.|  
|**사용**|컨트롤의 **사용됨** 속성을 반환하거나 설정합니다. 사용 가능한 컨트롤은 사용자가 만든 이벤트에 대응할 수 있습니다.|  
|**글꼴**|컨트롤의 앰비언트 글꼴을 반환하거나 설정합니다. 컨트롤에 글꼴이 없으면 Null입니다.|  
|`ForeColor`|컨트롤의 앰비언트 `ForeColor` 속성을 반환하거나 설정합니다.|  
|**hWnd**|컨트롤의 **hWnd** 속성을 반환하거나 설정합니다. **hWnd**에는 **멤버 변수** 구현 형식이 없습니다.|  
|**ReadyState**|컨트롤의 **ReadyState** 속성을 반환하거나 설정합니다. 컨트롤이는 초기화되지 않거나, 초기화되거나, 로드되거나, 대화형이거나, 완료될 수 있습니다. 자세한 정보는 *인터넷 SDK*에서 [READYSTATE](https://msdn.microsoft.com/en-us/library/aa768362.aspx)를 참조하세요.|  
|**텍스트**|컨트롤에 포함된 텍스트를 반환하거나 설정합니다. **텍스트**에는 **멤버 변수** 구현 형식이 없습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [속성 추가](../ide/adding-a-property-visual-cpp.md)   
 [속성 추가 마법사, IDL 특성](../ide/idl-attributes-add-property-wizard.md)