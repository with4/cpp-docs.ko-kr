---
title: "대화 상자 테스트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Test Dialog command
- testing, dialog boxes
- dialog boxes, testing
ms.assetid: 45034ee9-c554-4f4b-8c46-6ddefdee8951
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d81d288453e56acfb02a123075692b907d371578
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="testing-a-dialog-box"></a>대화 상자 테스트
대화 상자를 디자인할 때 프로그램을 컴파일하지 않고 런타임에 동작을 시뮬레이션 및 테스트할 수 있습니다. 이 모드에서 다음 작업을 수행할 수 있습니다.  
  
-   텍스트 입력, 콤보 상자 목록에서 선택, 옵션 켜기 또는 끄기, 명령 선택  
  
-   탭 순서 테스트  
  
-   라디오 단추 또는 확인란과 같은 컨트롤의 그룹화 테스트  
  
-   대화 상자의 컨트롤에 대한 바로가기 키 테스트  
  
    > [!NOTE]
    >  마법사를 사용하여 만든 대화 상자 코드에 대한 연결은 시뮬레이션에 포함되지 않습니다.  
  
 대화 상자를 테스트할 때는 일반적으로 주 프로그램 창을 기준으로 상대적인 위치에 표시됩니다. 대화 상자의 Absolute Align 속성을 True로 설정하면 화면의 왼쪽 위 모퉁이를 기준으로 상대적인 위치에 대화 상자가 표시됩니다.  
  
### <a name="to-test-a-dialog-box"></a>대화 상자를 테스트하려면  
  
1.  대화 상자 편집기가 활성 창일 경우 메뉴 모음에서 **서식**, **대화 상자 테스트**를 선택합니다.  
  
2.  시뮬레이션을 종료 하려면 Esc 키를 누르거나 테스트하는 대화 상자에서 **닫기** 단추를 선택합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하십시오. [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index)합니다.  
  
 요구 사항  
  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자의 컨트롤](../windows/controls-in-dialog-boxes.md)   
 [대화 상자 편집기](../windows/dialog-editor.md)   
 [대화 상자 편집기 도구 모음 표시 또는 숨기기](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)

