---
title: ATL DHTML 컨트롤 수정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTML controls, modifying
- DHTML controls
- DHTML controls, modifying
ms.assetid: c053f35f-8629-4600-9595-721f5956777a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3810236aca4661a6cdcd8399294cdb73e97948fd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356497"
---
# <a name="modifying-the-atl-dhtml-control"></a>ATL DHTML 컨트롤 수정
ATL 컨트롤 마법사에서 작성 하 고 해당 컨트롤의 실행 수 있도록 하 고 프로젝트 파일에는 메서드는 작성 하는 방법 및 DHTML 디스패치 메서드를 사용 하 여 컨트롤의 c + + 코드를 호출 하는 방법을 확인할 수 있도록 시작 코드를 제공 합니다. 인터페이스에 디스패치 메서드를 추가할 수 있습니다. 그런 다음 HTML 리소스의 메서드를 호출할 수 있습니다.  
  
#### <a name="to-modify-the-atl-dhtml-control"></a>ATL DHTML 컨트롤을 수정 하려면  
  
1.  클래스 뷰에서 컨트롤 프로젝트를 확장 합니다.  
  
     에 "UI"로 끝나는 인터페이스는 한 가지 방법은 `OnClick`합니다. "I"에 종료 하지 않는 인터페이스는 모든 메서드는 없습니다.  
  
2.  라는 메서드를 추가 `MethodInvoked` "I"에 종료 하지 않는 인터페이스  
  
     이 메서드는 DHTML 컨트롤과 상호 작용을 사용 하는 인터페이스를 하지 않도록 컨테이너 상호 작용에 대 한 컨트롤 컨테이너에서 사용 되는 인터페이스에 추가 됩니다. 컨테이너에만이 메서드를 호출할 수 있습니다.  
  
3.  .Cpp 파일에서 스텁 아웃 메서드를 찾아서 코드를 추가 예를 들어 메시지 상자를 표시:  
  
 [!code-cpp[NVC_ATL_COM#5](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_1.cpp)]  
  
4.  라는 다른 메서드를 추가 `HelloHTML`,이 경우에만 "UI"로 끝나는 인터페이스에 추가 스텁 아웃 찾을 `HelloHTML` 메서드는.cpp에서 파일을 예를 들어 메시지 상자를 표시 하는 코드를 추가:  
  
 [!code-cpp[NVC_ATL_COM#6](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_2.cpp)]  
  
5.  세 번째 메서드에 추가 `GoToURL`, "I"에 종료 하지 않는 인터페이스 이 메서드를 호출 하 여 구현 [IWebBrowser2::Navigate](https://msdn.microsoft.com/library/aa752133.aspx), 다음과 같습니다.  
  
 [!code-cpp[NVC_ATL_COM#7](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_3.cpp)]  
  
     사용할 수는 **IWebBrowser2** 메서드 ATL.h 파일에서 해당 인터페이스에 대 한 포인터를 제공 하기 때문에 있습니다.  
  
 다음으로 만든 메서드를 호출 하는 HTML 리소스를 수정 합니다. 이러한 메서드를 호출 하기 위해 세 개의 단추를 추가 합니다.  
  
#### <a name="to-modify-the-html-resource"></a>HTML 리소스를 수정 하려면  
  
1.  솔루션 탐색기에서 HTML 리소스를 표시 하려면.htm 파일을 두 번 클릭 합니다.  
  
     HTML, 특히 외부 Windows 디스패치 메서드 호출을 검사 합니다. 프로젝트의를 호출 하는 HTML `OnClick` 메서드, 및 매개 변수는 컨트롤의 본문을 나타냅니다 (`theBody`) 색을 할당 하 고 ("`red`"). 메서드 호출 다음 텍스트는 단추에 표시 되는 레이블입니다.  
  
2.  다른 항목 추가 `OnClick` 메서드를 변경 색입니다. 예를 들어:  
  
 ```  
 <br>  
 <br>  
 <BUTTON onclick='window.external.OnClick(theBody, "white");'>Refresh</BUTTON>  
 ```  
  
     이 메서드는 레이블이 붙은 단추 만들어집니다 **새로 고침**, 원래, 흰색 배경으로 컨트롤을 반환 하기 위해 클릭할 수는 있습니다.  
  
3.  에 대 한 호출 추가 `HelloHTML` 만든 메서드. 예를 들어:  
  
 ```  
 <br>  
 <br>  
 <BUTTON onclick='window.external.HelloHTML();'>HelloHTML</BUTTON>  
 ```  
  
     이 메서드는 레이블이 붙은 단추 만들어집니다 **HelloHTML**, 사용자 표시를 클릭할 수 있는 `HelloHTML` 메시지 상자.  
  
 이제 빌드할 수 있습니다 및 [수정 된 DHTML 컨트롤 테스트](../atl/testing-the-modified-atl-dhtml-control.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [DHTML 컨트롤에 대 한 지원](../atl/atl-support-for-dhtml-controls.md)

