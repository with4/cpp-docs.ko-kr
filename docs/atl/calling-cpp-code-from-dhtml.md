---
title: DHTML에서 c + + 코드 호출 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DHTML, calling C++ code from
ms.assetid: 37329acd-4c22-40ca-a85a-b7480748f75f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f24c7c1e3cd6cd1b24d74fcc1eee3209562a138a
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848966"
---
# <a name="calling-c-code-from-dhtml"></a>DHTML에서 c + + 코드 호출
DHTML 컨트롤 테스트 컨테이너 또는 Internet Explorer와 같은 컨테이너에서 호스트할 수 있습니다. 참조 [속성 및 이벤트 테스트 컨테이너를 사용 하 여 테스트](../mfc/testing-properties-and-events-with-test-container.md) 테스트 컨테이너에 액세스 하는 방법에 대 한 정보에 대 한 합니다.  
  
 컨테이너 컨트롤을 호스팅하는 표준 컨트롤 인터페이스를 사용 하 여 컨트롤을 사용 하 여 통신 합니다. DHTML c + + 코드 및 HTML 리소스와 통신 하는 "UI"로 끝나는 디스패치 인터페이스를 사용 합니다. [ATL DHTML 컨트롤 수정](../atl/modifying-the-atl-dhtml-control.md), 이러한 다른 인터페이스에서 호출할 메서드를 추가 연습해 볼 수 있습니다.  
  
 DHTML에서 c + + 코드를 호출 하는 예제를 보려면 [DHTML 컨트롤 만들기](../atl/creating-an-atl-dhtml-control.md) ATL 컨트롤 마법사를 사용 하 고 HTML 파일 및 헤더 파일에서 코드를 검사 합니다.  
  
## <a name="declaring-webbrowser-methods-in-the-header-file"></a>헤더 파일에서 WebBrowser 메서드를 선언합니다.  
 DHTML UI에서 c + + 메서드를 호출 하려면 컨트롤의 UI 인터페이스에 메서드를 추가 해야 합니다. ATL 컨트롤 마법사에서 만든 헤더 파일에서 c + + 메서드를 포함 하는 예를 들어 `OnClick`, 마법사에서 생성 된 컨트롤의 UI 인터페이스의 멤버인입니다.  
  
 검사 `OnClick` 컨트롤.h 파일에서:  
  
 [!code-cpp[NVC_ATL_COM#4](../atl/codesnippet/cpp/calling-cpp-code-from-dhtml_1.h)]  
  
 첫 번째 매개 변수를 *pdispBody*, 본문 개체의 디스패치 인터페이스에 대 한 포인터입니다. 두 번째 매개 변수를 *varColor*를 컨트롤에 적용할 색을 식별 합니다.  
  
## <a name="calling-c-code-in-the-html-file"></a>HTML 파일에서 c + + 코드를 호출합니다.  
 헤더 파일에서 WebBrowser 메서드를 선언한 후에 HTML 파일에서 메서드를 호출할 수 있습니다. ATL 컨트롤 마법사 3 Windows 디스패치 메서드를 삽입 하는 HTML 파일에서 알림: 세 가지 `OnClick` 컨트롤의 배경색을 변경 하도록 메시지를 디스패치 하는 메서드.  
  
 HTML 파일의 메서드 중 하나를 검사 합니다.  
  
 `<BUTTON onclick='window.external.OnClick(theBody, "red");'>Red</BUTTON>`  
  
 창 외부 메서드를 위의 HTML 코드에 `OnClick`, 단추 태그의 일부로 호출 됩니다. 메서드에 두 매개 변수가: `theBody`를 참조 하는 HTML 문서 본문의 및 `"red"`, 단추를 클릭할 때 컨트롤의 배경 색을 빨강 변경할 수를 나타내는입니다. `Red` 버튼의 레이블은 태그 뒤에 있습니다.  
  
 참조 [ATL DHTML 컨트롤 수정](../atl/modifying-the-atl-dhtml-control.md) 사용자 고유의 메서드를 제공 하는 방법에 대 한 자세한 내용은 합니다. 참조 [DHTML 컨트롤 프로젝트의 요소 식별](../atl/identifying-the-elements-of-the-dhtml-control-project.md) HTML 파일에 대 한 자세한 내용은 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [DHTML 컨트롤에 대 한 지원](../atl/atl-support-for-dhtml-controls.md)

