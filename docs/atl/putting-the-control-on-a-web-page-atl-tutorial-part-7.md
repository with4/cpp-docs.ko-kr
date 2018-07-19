---
title: 웹 페이지 (ATL 자습서, 7 부)에 컨트롤 배치 | Microsoft Docs
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 50dc4c95-c95b-4006-b88a-9826f7bdb222
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0cd4076ac34af6ee4b19687f401376265bf0e872
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362586"
---
# <a name="putting-the-control-on-a-web-page-atl-tutorial-part-7"></a>웹 페이지에 컨트롤 배치(ATL 자습서, 7부)
컨트롤이 완성 되었습니다. 실제 상황에서 작동 하 여 컨트롤을 보려면 웹 페이지에 추가 합니다. 컨트롤을 정의할 때 컨트롤을 포함 하는 HTML 파일을 만들었습니다. PolyCtl.htm 파일 열기 **솔루션 탐색기**, 웹 페이지에 컨트롤을 볼 수 있습니다.  
  
 이 단계에서는 이벤트에 응답 하는 웹 페이지를 스크립팅할 수 있습니다. 또한 컨트롤 스크립팅을 위해 안전 하 게 보호 되는 Internet Explorer가 컨트롤을 수정 합니다.  
  
## <a name="scripting-the-web-page"></a>웹 페이지 스크립팅  
 컨트롤이 아무런 작업도 아직 주므로 보내는 이벤트에 응답 하는 웹 페이지를 변경 합니다.  
  
#### <a name="to-script-the-web-page"></a>웹 페이지를 스크립팅하려면  
  
1.  PolyCtl.htm 열고 HTML 뷰를 선택 합니다. HTML 코드에 다음 줄을 추가 합니다. 다음 추가 합니다 `</OBJECT>` 하기 전에 `</BODY>`합니다.  
  
 ```  
 
 <SCRIPT LANGUAGE="VBScript">  
 <!--  
    Sub PolyCtl_ClickIn(x, y)  
    PolyCtl.Sides = PolyCtl.Sides + 1  
    End Sub  
    Sub PolyCtl_ClickOut(x, y)  
    PolyCtl.Sides = PolyCtl.Sides - 1  
    End Sub  
 -->  
 </SCRIPT>  
 ```  
  
2.  HTM 파일을 저장 합니다.  
  
 컨트롤에서 양쪽 속성을 가져오고 컨트롤 내부를 클릭할 경우 면 수를 1 씩 증가 하는 VBScript 코드를 추가 했습니다. 컨트롤의 바깥쪽을 클릭 하면 씩 측면의 수를 줄입니다.  
  
## <a name="indicating-that-the-control-is-safe-for-scripting"></a>컨트롤 스크립트 임을 나타내는  
 Internet Explorer의 컨트롤을 사용 하 여 웹 페이지를 볼 수 또는 더 편리 하 게 사용 하 여 Visual c + +로 작성 된 웹 브라우저 보기. 웹 브라우저 보기에서 컨트롤을 보려면 PolyCtl.htm을 마우스 오른쪽 단추로 클릭 하 고 클릭 **브라우저에서 보기**합니다.  
  
 현재 Internet Explorer 보안 설정에 따라, 나타날 수 있습니다 보안 경고 손상 시킬 대화 상자가 표시 컨트롤 스크립트에 안전 하 게 보호 되지 않을 수 있습니다 및 가능성이 있습니다. 예를 들어, 파일을 표시 하지만 컨트롤을 설치한 경우는 `Delete` 파일을 삭제 하는 메서드를 안전 하 게 보호 되 면 될 수만 페이지에 볼 수 있습니다. 하지만 것이 안전 스크립트를 다른 사용자가 호출할 수 있으므로 `Delete` 메서드.  
  
> [!IMPORTANT]
>  이 자습서에서는 안전한 것으로 표시 되지 않은 ActiveX 컨트롤을 사용 하려면 Internet Explorer에서 보안 설정을 변경할 수 있습니다. 제어판에서 클릭 **인터넷 속성** 클릭 **보안** 적절 한 설정을 변경할 수 있습니다. 이 자습서를 완료 한 때를 원래 상태로 보안 설정을 변경 합니다.  
  
 프로그래밍 방식으로이 특정 컨트롤에 대 한 보안 경고 대화 상자를 표시 하려면 필요 하지 않는 Internet Explorer을 알릴 수 있습니다. 이를 수행할 수 있습니다는 `IObjectSafety` 인터페이스 및 ATL 클래스의이 인터페이스의 구현을 제공 [IObjectSafetyImpl](../atl/reference/iobjectsafetyimpl-class.md)합니다. 인터페이스에 있는 컨트롤을 추가 하려면 추가 `IObjectSafetyImpl` 상속 된 클래스 목록에 COM 맵에서 대 한 항목을 추가 합니다.  
  
#### <a name="to-add-iobjectsafetyimpl-to-the-control"></a>IObjectSafetyImpl 컨트롤에 추가 하려면  
  
1.  PolyCtl.h에서 상속 된 클래스 목록의 끝에 다음 줄을 추가 하 고 이전 줄으로는 쉼표를 추가 합니다.  
  
 [!code-cpp[NVC_ATL_Windowing#62](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_1.h)]  
  
2.  COM 드에서를 맵에 PolyCtl.h 다음 줄을 추가 합니다.  
  
 [!code-cpp[NVC_ATL_Windowing#63](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_2.h)]  
  
## <a name="building-and-testing-the-control"></a>빌드 및 컨트롤 테스트  
 컨트롤을 빌드하십시오. 빌드가 완료 되 면 PolyCtl.htm를 다시 브라우저 보기에서 엽니다. 이 이번에 웹 페이지는 보안 경고 대화 상자 없이 직접 표시 해야 합니다. 다각형 내부를 클릭 합니다. 변의 수가 하나 증가합니다. 양쪽의 수를 줄이기 위해 다각형 바깥쪽을 클릭 합니다. 3 개 미만 양쪽의 수를 줄이기 위해 시도 하는 경우 설정 하는 오류 메시지가 표시 됩니다.  
  
 [6 단계 이동](../atl/adding-a-property-page-atl-tutorial-part-6.md)  
  
## <a name="next-steps"></a>다음 단계  
 ATL 자습서를 완료 했습니다. ATL에 대 한 자세한 정보에 대 한 링크를 참조 하십시오.는 [ATL 시작 페이지](../atl/active-template-library-atl-concepts.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [자습서](../atl/active-template-library-atl-tutorial.md)

