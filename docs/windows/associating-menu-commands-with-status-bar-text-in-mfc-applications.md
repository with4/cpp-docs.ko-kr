---
title: 메뉴 명령과 상태 표시줄 텍스트 MFC 응용 프로그램에 연결 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- status bars, associating menu items
- menus, status bar text
ms.assetid: 757c0e02-bc97-493f-bccd-6cc6887ebc64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d868c9270e23e2ee1fa0dcdc1845d9762cefb16c
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649404"
---
# <a name="associating-menu-commands-with-status-bar-text-in-mfc-applications"></a>MFC 응용 프로그램에서 메뉴 명령과 상태 표시줄 텍스트 연결
응용 프로그램은 사용자가 선택할 수 있는 각 메뉴 명령에 대한 설명 텍스트를 표시할 수 있습니다. 사용 하 여 각 메뉴 명령 텍스트 문자열을 할당 하 여이 작업을 수행 합니다 **프롬프트** 속성에는 **속성** 창입니다. 명령과 동일한 ID를 가진 문자열이 [문자열 테이블](../windows/string-editor.md) 에 있는 경우 MFC 응용 프로그램은 사용자가 메뉴 항목 위로 마우스를 가져갈 때 실행 중인 응용 프로그램의 상태 표시줄에 이 문자열 리소스를 자동으로 표시합니다.  
  
### <a name="to-associate-a-menu-command-with-a-status-bar-text-string"></a>메뉴 명령을 상태 표시줄 텍스트 문자열에 연결하려면  
  
1.  **메뉴** 편집기에서 메뉴 명령을 선택합니다.  
  
2.  [속성 창](/visualstudio/ide/reference/properties-window)의 **프롬프트** 상자에 연결된 상태 표시줄 텍스트를 입력합니다.  
  
## <a name="requirements"></a>요구 사항  
 MFC  
  
## <a name="see-also"></a>참고 항목  
 [문자열 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [메뉴에 명령 추가](../windows/adding-commands-to-a-menu.md)   
 [메뉴 편집기](../windows/menu-editor.md)