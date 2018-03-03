---
title: "메뉴 명령 속성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- menu items, properties
ms.assetid: 6d308205-3c9e-42f2-ab42-45e656940e45
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 186790db57c20abf9f67f693ff60029257ebd4f0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="menu-command-properties"></a>메뉴 명령 속성
아래 정보는 메뉴 명령을 선택하면 [속성 창](/visualstudio/ide/reference/properties-window) 에 나타나는 메뉴 속성에 따라 구성됩니다. 이 속성은 사전순으로 나열되어 있으며, 실제 속성 창에서는 이 속성을 범주별로 볼 수 있습니다.  
  
|속성|설명|  
|--------------|-----------------|  
|**Break**|다음 값 중 하나일 수 있습니다.<br /><br /> -   **None** (기본값): 나누기가 없습니다.<br />-   **열**: 정적 메뉴의 경우 이 값은 새 줄에 메뉴 명령을 배치합니다. 팝업 메뉴의 경우 이 값은 열 사이에 구분선이 없이 새 열에 메뉴 명령을 배치합니다. 이 속성을 설정하는 경우 런타임에만 메뉴 모양에 영향이 있으며 메뉴 편집기에서는 영향이 없습니다.<br />-   **막대**: 열의 경우와 같지만, 팝업 메뉴의 경우 이 값은 세로줄로 이전 행과 새 행을 분리합니다. 이 속성을 설정하는 경우 런타임에만 메뉴 모양에 영향이 있으며 메뉴 편집기에서는 영향이 없습니다.|  
|**캡션**|메뉴 명령(메뉴 이름)의 레이블을 지정하는 텍스트입니다. 메뉴 명령의 캡션에 있는 문자 중 하나를 니모닉 키로 만들려면 문자 앞에 앰퍼샌드(&)를 추가합니다.|  
|**선택한 상태**|True이면 메뉴 명령이 처음에 선택됩니다. 형식: 부울입니다. 기본값: False입니다.|  
|**사용**|**False**이면 메뉴 항목이 사용하지 않도록 설정됩니다.|  
|**회색으로 표시**|True이면 메뉴 명령이 처음에 회색으로 표시되고 비활성 상태입니다. 형식: 부울입니다. 기본값: False입니다.|  
|**도움말**|메뉴 항목을 오른쪽에 맞춥니다. 예를 들어 **도움말** 메뉴 명령은 항상 모든 Windows 응용 프로그램에서 오른쪽에 표시됩니다. 메뉴 항목에 이 속성을 설정하는 경우 해당 항목은 맨 오른쪽에 및 메뉴 끝에 표시됩니다. 최상위 항목에 적용됩니다. 기본값: **False**입니다.|  
|**ID**|헤더 파일에 정의된 기호입니다. 형식: 기호, 정수 또는 따옴표 붙은 문자열입니다. [속성 창](/visualstudio/ide/reference/properties-window) 에서 선택할 수 있는 드롭다운 목록을 제공하지 않는 경우에도, 편집기에서 일반적으로 제공되는 기호를 사용할 수 있습니다.|  
|**Popup**|True이면 메뉴 명령이 팝업 메뉴입니다. 형식: 부울입니다. 기본값: 메뉴 모음의 최상위 메뉴인 경우 True이고, 그렇지 않으면 False입니다.|  
|**프롬프트**|이 메뉴 명령이 강조 표시되면 상태 표시줄에 나타날 텍스트를 포함합니다. 이 텍스트는 메뉴 명령과 동일한 식별자를 사용하여 문자열 테이블에 배치됩니다. 이 속성은 모든 종류의 프로젝트에 사용할 수 있지만 런타임 기능은 MFC에 특정합니다.|  
|**오른쪽에서 왼쪽 맞춤**|런타임에 메뉴 명령을 메뉴 모음의 오른쪽에 맞춥니다. 형식: 부울입니다. 기본값: False입니다.|  
|**오른쪽에서 왼쪽 맞춤**|히브리어나 아랍어와 같이 오른쪽에서 왼쪽으로 읽는 언어에 맞춰 지역화된 인터페이스의 경우, 메뉴 명령을 오른쪽에서 왼쪽으로 표시할 수 있습니다.|  
|**구분 기호**|True이면 메뉴 명령이 구분 기호입니다. 형식: 부울입니다. 기본값: False입니다.|  
  

  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [메뉴 편집기](../windows/menu-editor.md)