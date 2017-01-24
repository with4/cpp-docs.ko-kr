---
title: "웹 페이지에 컨트롤 배치(ATL 자습서, 7부) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
ms.assetid: 50dc4c95-c95b-4006-b88a-9826f7bdb222
caps.latest.revision: 15
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 웹 페이지에 컨트롤 배치(ATL 자습서, 7부)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

컨트롤이 이제 완료되었습니다.  실제 환경에서 컨트롤 작업을 보려면 웹 페이지에 배치합니다.  컨트롤이 포함된 HTML 파일이 컨트롤을 정의할 때 만들어졌습니다.  **솔루션 탐색기**에서 PolyCtl.htm 파일을 열면 웹 페이지에 컨트롤을 볼 수 있습니다.  
  
 이 단계에서는 이벤트에 응답하는 웹 페이지를 스크립팅할 수 있습니다.  컨트롤이 스크립팅에 대해 안전한지 Internet Explorer에게 알리기 위해 컨트롤을 수정해야 합니다.  
  
## 웹 페이지 스크립팅  
 컨트롤에서 수행하는 작업이 없기 때문에 사용자가 전송하는 이벤트에 응답하도록 웹 페이지를 변경합니다.  
  
#### 웹 페이지를 스크립트로 작성하려면  
  
1.  PolyCtl.htm을 열고, HTML 뷰를 선택합니다.  다음 줄을 HTML 코드에 추가합니다.  `</OBJECT>` 뒤,  `</BODY>` 앞에 추가해야 합니다.  
  
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
  
2.  HTM 파일을 저장합니다.  
  
 컨트롤에서 면 속성을 가져오고 컨트롤 내부를 클릭하면 면의 수가 하나씩 증가하는 VBScript 코드를 추가했습니다.  컨트롤 외부를 클릭하면 모서리의 수가 1로 줄어듭니다.  
  
## 스크립트 사용에 안전한 컨트롤임을 나타냄  
 Internet Explorer에서 컨트롤을 사용하여 웹 페이지를 보거나 더 편리하게 Visual C\+\+에 내장된 웹 브라우저 뷰를 사용할 수 있습니다.  웹 브라우저 보기에서 컨트롤을 보려면 PolyCtl.htm을 마우스 오른쪽 단추로 클릭하고 **브라우저에서 보기**를 클릭합니다.  
  
 최신 Internet Explorer 보안 설정을 기반으로 컨트롤을 스크립팅하는 것이 안전하지 않을 수 있고 손상 가능성이 있다는 보안 경고 대화 상자가 나타날 수 있습니다.  예를 들어, 파일을 표시한 컨트롤은 있지만 파일을 삭제한 `Delete` 메서드도 있는 경우 페이지에서만 확인하는 것이 안전할 것입니다.  다른 사람이 `Delete` 메서드를 호출할 수 있으므로 스크립트에 사용하는 것은 안전하지 않을 수 있습니다.  
  
> [!IMPORTANT]
>  이 자습서의 경우 Internet Explorer에서 보안 설정을 변경하여 안전하게 표시된 ActiveX 컨트롤을 실행할 수 있습니다.  제어판에서 **인터넷 속성**을 클릭하고 **보안**을 클릭하여 적절한 설정을 변경합니다.  이 자습서를 완료했으면 보안 설정을 다시 원래 상태로 변경합니다.  
  
 이 특정 컨트롤의 경우 보안 경고 대화 상자를 표시할 필요가 없음을 Internet Explorer에 프로그래밍 방식으로 알릴 수 있습니다.  `IObjectSafety` 인터페이스를 사용하면 ATL이 [IObjectSafetyImpl](../atl/reference/iobjectsafetyimpl-class.md) 클래스에서 해당 인터페이스의 구현을 제공합니다.  컨트롤에 인터페이스를 추가하려면 상속된 클래스 목록에 `IObjectSafetyImpl`을 추가하고 COM 맵에 이에 대한 항목을 추가합니다.  
  
#### 컨트롤에 IObjectSafetyImpl을 추가하려면  
  
1.  다음 줄을 PolyCtl.h에 있는 상속된 클래스 목록 끝에 추가하고 앞의 줄에 쉼표를 추가합니다.  
  
     [!code-cpp[NVC_ATL_Windowing#62](../atl/codesnippet/CPP/putting-the-control-on-a-web-page-atl-tutorial-part-7_1.h)]  
  
2.  다음 줄을 PolyCtl.h의 COM 맵에 추가합니다.  
  
     [!code-cpp[NVC_ATL_Windowing#63](../atl/codesnippet/CPP/putting-the-control-on-a-web-page-atl-tutorial-part-7_2.h)]  
  
## 컨트롤 빌드 및 테스트  
 컨트롤을 빌드합니다.  빌드가 완료되면 브라우저 보기에서 PolyCtl.htm를 다시 엽니다.  이번에는 보안 경고 대화 상자 없이 웹 페이지가 직접 표시됩니다.  다각형 내부를 클릭하면 변 수가 1씩 늘어납니다.  다각형 외부를 클릭하면 변 수가 줄어듭니다.  모서리 수를 3 이하로 줄이려고 하면 설정한 오류 메시지가 나타납니다.  
  
 [6단계로 돌아가기](../atl/adding-a-property-page-atl-tutorial-part-6.md)  
  
## 다음 단계  
 이것으로 ATL 자습서를 마칩니다.  ATL에 대한 자세한 내용은 [ATL 시작 페이지](../atl/active-template-library-atl-concepts.md)를 참조하십시오.  
  
## 참고 항목  
 [자습서](../atl/active-template-library-atl-tutorial.md)