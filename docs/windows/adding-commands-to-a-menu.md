---
title: "메뉴에 명령 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.menu
dev_langs: C++
helpviewer_keywords:
- menu items, adding to menus
- menus, adding items
- commands, adding to menus
- commands
- menu items
ms.assetid: 1523a755-0ab5-42f8-9e98-bb9881564431
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d53f868fd76877152bb3ec81fdba85c1d97b3aac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-commands-to-a-menu"></a>메뉴에 명령 추가
### <a name="to-add-commands-to-a-menu"></a>메뉴에 명령을 추가하려면  
  
1.  [메뉴 만들기](../windows/creating-a-menu.md)합니다.  
  
2.  파일과 같은 메뉴 이름을 클릭합니다.  
  
     각 메뉴가 확장되고 명령에 대한 새 항목 상자가 표시됩니다. 예를 들어 새로 만들기, 열기 및 닫기와 같은 명령을 파일 메뉴에 추가할 수 있습니다.  
  
3.  새 항목 상자에 새 메뉴 명령에 대한 이름을 입력합니다.  
  
    > [!NOTE]
    >  에 및 메뉴 편집기에 입력 한 텍스트가 표시는 **캡션** 상자에 [속성 창](/visualstudio/ide/reference/properties-window)합니다. 한 위치에서 새 메뉴에 대한 속성을 편집할 수 있습니다.  
  
    > [!TIP]
    >  사용자가 메뉴 명령을 선택할 수 있도록 니모닉 키(바로 가기 키)를 정의할 수 있습니다. 니모닉으로 지정하려면 문자 앞에 앰퍼샌드(&)를 입력합니다. 사용자는 해당 문자를 입력하여 메뉴 명령을 선택할 수 있습니다.  
  
4.  속성 창에서 적용되는 메뉴 명령 속성을 선택합니다. 자세한 내용은 참조 [메뉴 명령 속성](../windows/menu-command-properties.md)합니다.  
  
5.  에 **프롬프트** 속성 창에서 응용 프로그램의 상태 표시줄에 표시할 프롬프트 문자열을 입력 합니다.  
  
     이렇게 하면 앞에서 만든 메뉴 명령과 동일한 리소스 식별자를 사용하는 항목이 문자열 테이블에 만들어집니다.  
  
    > [!NOTE]
    >  표시 되는 메시지 인 메뉴 항목에만 적용할 수 있습니다는 **팝업** 속성 **True**합니다. 예를 들어 최상위 메뉴 항목은 하위 메뉴 항목이 있는 경우 프롬프트가 적용됩니다. 프롬프트의 용도는 사용자가 메뉴 항목을 클릭할 경우 발생하는 동작을 나타내는 것입니다.  
  
6.  키를 눌러 **ENTER** 메뉴 명령을 완료 합니다.  
  
     새 항목 상자를 선택하여 추가 메뉴 명령을 만들 수 있습니다.  
  

  
 **요구 사항**  
  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [메뉴 편집기](../windows/menu-editor.md)   
