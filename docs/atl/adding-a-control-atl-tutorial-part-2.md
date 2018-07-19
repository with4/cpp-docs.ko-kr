---
title: 컨트롤 (ATL 자습서, 2 부) 추가 | Microsoft Docs
ms.custom: get-started-article
ms.date: 06/18/2018
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c9575a75-1064-41f1-9697-7aada560c669
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f1547d48b5b5914d9b32ff8b476b0c007f972067
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238710"
---
# <a name="adding-a-control-atl-tutorial-part-2"></a>컨트롤 추가(ATL 자습서, 2부)
이 단계에서는 프로젝트에 컨트롤을 추가를 빌드하고 웹 페이지에서 테스트 합니다.  
  
## <a name="procedures"></a>절차  
  
#### <a name="to-add-an-object-to-an-atl-project"></a>ATL 프로젝트에 개체를 추가 하려면
  
1.  **솔루션 탐색기**, 다각형 프로젝트를 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  가리킨 **추가** 를 바로 가기 메뉴를 클릭 한 **새 항목** 하위 메뉴에 있습니다.
  
     **새 항목 추가** 대화 상자가 나타납니다. 왼쪽의 트리 구조에 다른 개체 범주 나열 됩니다.
  
3.  **ATL** 폴더를 클릭합니다.  
  
4.  오른쪽의 템플릿 목록에서 **ATL 컨트롤**을 선택합니다. **추가**를 클릭합니다. ATL 컨트롤 마법사가 열리고 컨트롤을 구성할 수 있습니다.  
  
5.  이름을 짧게 줄여 `PolyCtl`으로 입력하면 다른 필드는 자동으로 완성됩니다. 아직 일부를 변경해야 하기 때문에 **마침**을 클릭하지 마십시오.  
  
 ATL 컨트롤 마법사의 **이름** 페이지에는 다음 필드가 포함 됩니다.  
  
|필드|목차|  
|-----------|--------------|  
|**짧은 이름**|컨트롤에 입력 한 이름입니다.|  
|**클래스**|컨트롤을 구현하기 위해 만든 C++ 클래스 이름입니다.|  
|**.h 파일**|C++ 클래스의 정의 포함 하기 위해 만들어진 파일입니다.|  
|**.cpp 파일**|C++ 클래스의 구현에 포함 하기 위해 만들어진 파일입니다.|  
|**CoClass**|이 컨트롤에 대한 구성 요소 클래스의 이름입니다.|  
|**Interface**|구현해야 할 컨트롤의 사용자 지정 메서드 및 속성의 인터페이스 이름입니다.|  
|**Type**|컨트롤에 대한 설명입니다.|  
|**ProgID**|컨트롤의 CLSID를 찾는 데 사용할 읽을 수 있는 이름입니다.| 
  
 ATL 컨트롤 마법사에서 몇 가지 추가 설정을 확인 해야 합니다.  
  
#### <a name="to-enable-support-for-rich-error-information-and-connection-points"></a>자세한 오류 정보 및 연결 지점에 대한 지원을 사용 하도록 설정  
  
1.  **옵션** 페이지를 열기 위해 **옵션**을 선택합니다.  
  
2.  **연결점** 체크박스를 선택합니다. 이렇게 하면 송신 인터페이스에 대한 지원이 IDL 파일에서 만들어집니다.  
  
 또한 Excel 또는 Word와 같이 포함된 개체를 지원하는 응용 프로그램에 삽입될 수 있도록 삽입 가능 컨트롤을 만들 수 있습니다.  
  
#### <a name="to-make-the-control-insertable"></a>삽입 가능한 컨트롤 만들기  
  
1.  **모양** 페이지를 열기 위해 **모양**을 클릭합니다.  
  
2.  **삽입 가능** 체크박스를 선택합니다.  
  
 개체에서 표시하는 다각형은 채우기 색이 단색이므로 `Fill Color` 스톡 속성을 추가해야 합니다.  
  
#### <a name="to-add-a-fill-color-stock-property-and-create-the-control"></a>채우기 색 스톡 속성을 추가하고 컨트롤 만들기  
  
1.  **스톡 속성**을 클릭하여 **스톡 속성** 페이지를 엽니다.  
  
2.  **지원되지 않습니다**의 아래에 가능한 스톡 속성 목록 아래로 스크롤합니다. `Fill Color`를 더블클릭하여 **Supported** 목록으로 옮깁니다.  
  
3.  컨트롤에 대한 옵션을 완료합니다. **마침**을 클릭합니다.  
  
 마법사 컨트롤을 만들 때 몇 가지 코드 변경 내용 및 파일 추가 발생 했습니다. 다음 파일을 만들었습니다.  
  
|파일|설명|  
|----------|-----------------|  
|PolyCtl.h|대부분의 C++ 클래스 `CPolyCtl`의 구현이 포함됩니다.|  
|PolyCtl.cpp|`CPolyCtl` 의 나머지 부분이 포함됩니다.|  
|PolyCtl.rgs|컨트롤을 등록 하는데 사용 하는 레지스트리 스크립트를 포함 하는 텍스트 파일입니다.|  
|PolyCtl.htm|새로 만든된 컨트롤에 대한 참조를 포함 하는 웹 페이지입니다.|  
  
 마법사는 또한 다음 코드 변경 내용을 수행:
  
-   컨트롤을 지원하는 데 필요한 ATL 파일들이 포함되도록 stdafx.h 및 stdafx.cpp 파일을 `#include`에 추가합니다.  
  
-   새 컨트롤의 세부 정보를 포함하도록 Polygon.idl을 변경합니다.  
  
-   Polygon.cpp의 개체맵에 새 컨트롤을 추가합니다.  
  
 이제 작동을 확인 하도록 컨트롤을 작성할 수 있습니다.  
  
## <a name="building-and-testing-the-control"></a>빌드 및 컨트롤 테스트  
  
#### <a name="to-build-and-test-the-control"></a>컨트롤을 빌드하고 테스트하려면  
  
1.  **빌드** 메뉴의 **빌드 다각형**을 클릭합니다.  
  
    컨트롤 빌드를 완료한 후에 **솔루션 탐색기**에서 PolyCtl.htm을 마우스 오른쪽 단추로 클릭하여 **브라우저에서 보기**를 선택합니다. 컨트롤을 포함하는 HTML 웹 페이지가 표시됩니다. "PolyCtl 개체에 대한 ATL 8.0 테스트 페이지" 제목 페이지와 **PolyCtl** 텍스트가 표시되어야 합니다. 보고 있는 것이 만들어진 컨트롤입니다.
  
> [!NOTE]
>  이 자습서를 완료했을 때 DLL 파일을 만들 수 없다는 오류 메세지가 표시되면 PolyCtl.htm 파일 및 ActiveX Control Test container를 닫고 솔루션을 다시 빌드하십시오. 그래도 DLL을 만들 수 없다면 컴퓨터를 다시 부팅하거나 (터미널 서비스를 사용하는 경우) 로그오프합니다.
  
  
 다음으로, 컨트롤에 사용자 지정 속성을 추가합니다.
  
  
 [1 단계를 다시](../atl/creating-the-project-atl-tutorial-part-1.md) &#124; [3 단계로](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md)  
  
## <a name="see-also"></a>참고 항목  
 [자습서](../atl/active-template-library-atl-tutorial.md)

