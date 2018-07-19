---
title: DHTML 컨트롤 프로젝트의 요소를 식별 합니다. | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTML controls, ATL support
- DHTML controls, ATL support
ms.assetid: b627547a-3768-4346-9900-4b7a21fb8e27
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f415d9b52179d83617cefe94d4f4525d3cf9808e
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852442"
---
# <a name="identifying-the-elements-of-the-dhtml-control-project"></a>DHTML 컨트롤 프로젝트의 요소를 식별합니다.
ATL 컨트롤에 대 한 대부분의 DHTML 컨트롤 코드는 정확 하 게 만들어집니다. 제네릭 코드의 기본적인 이해를 통해 작업을 [ATL 자습서](../atl/active-template-library-atl-tutorial.md), 섹션을 읽고 [ATL 프로젝트 만들기](../atl/reference/creating-an-atl-project.md) 하 고 [ATL COM 개체 기본 사항](../atl/fundamentals-of-atl-com-objects.md)합니다.  
  
 DHTML 컨트롤은 모든 ATL 컨트롤과 비슷하지만 제외:  
  
-   컨트롤을 구현 하는 일반 인터페이스 외에도 c + + 코드와 HTML 사용자 인터페이스 (UI) 간의 통신에 사용 되는 추가 인터페이스를 구현 합니다. HTML UI는이 인터페이스를 사용 하 여 c + + 코드를 호출 합니다.  
  
-   UI 컨트롤에 대 한 HTML 리소스를 만듭니다.  
  
-   멤버 변수를 통해 DHTML 개체 모델에 대 한 액세스를 허용 `m_spBrowser`, 하는 형식의 스마트 포인터 [IWebBrowser2](https://msdn.microsoft.com/library/aa752127.aspx)합니다. 이 포인터를 사용 하 여 DHTML 개체 모델의 일부에 액세스 합니다.  
  
 다음 그림에서는 DLL, DHTML 컨트롤, 웹 브라우저 및 HTML 리소스 간의 관계를 보여 줍니다.  
  
 ![DHTML 컨트롤 프로젝트의 요소](../atl/media/vc52en1.gif "vc52en1")  
  
> [!NOTE]
>  이 그래픽에서 이름은 자리 표시자입니다. HTML 리소스 및 컨트롤에 노출 된 인터페이스의 이름은 ATL 컨트롤 마법사에 할당할 이름을 기반으로 합니다.  
  
 이 그래픽에서 요소는 다음과 같습니다.  
  
-   **DLL 내** ATL 프로젝트 마법사를 사용 하 여 만든 DLL입니다.  
  
-   **DHTML 컨트롤** (`m_spBrowser`)는 DHTML 컨트롤, ATL 개체 마법사를 사용 하 여 생성 합니다. 웹 브라우저 개체의 인터페이스를 통해 웹 브라우저 개체 및 해당 메서드를 액세스 하는이 컨트롤 `IWebBrowser2`합니다. 자체 컨트롤은 컨트롤에 필요한 다른 표준 인터페이스 외에도 다음 두 가지 인터페이스를 노출 합니다.  
  
    -   `IDHCTL1` 컨테이너에 의해서만 사용에 대 한 컨트롤에서 노출 하는 인터페이스입니다.  
  
    -   `IDHCTLUI1` C + + 코드와 HTML 사용자 인터페이스 간의 통신에 대 한 디스패치 인터페이스입니다. 웹 브라우저 컨트롤을 표시 하려면 컨트롤의 디스패치 인터페이스를 사용 합니다. 이 디스패치 인터페이스의 다양 한 메서드를 호출 하 여 컨트롤의 사용자 인터페이스에서 호출할 수 있습니다 `window.external`고 호출 하려는이 디스패치 인터페이스의 메서드 이름 뒤에 있습니다. 액세스 `window.external` 이 컨트롤에 대 한 UI를 구성 하는 HTML 내 스크립트 태그에서. 리소스 파일의 외부 메서드를 호출 하는 방법에 대 한 자세한 내용은 참조 하세요. [DHTML에서 c + + 코드 호출](../atl/calling-cpp-code-from-dhtml.md)합니다.  
  
-   **IDR_CTL1** HTML 리소스의 리소스 ID입니다. 해당 파일 이름에는 예제의 경우 DHCTL1UI.htm 되었습니다. DHTML 컨트롤에는 표준 HTML 태그 및 텍스트 편집기를 사용 하 여 편집할 수 있는 외부 창 디스패치 명령이 포함 된 HTML 리소스를 사용 합니다.  
  
-   **웹 브라우저** 웹 브라우저에 HTML 리소스의 HTML에 따라 컨트롤의 UI를 표시 합니다. 웹 브라우저에 대 한 포인터 `IWebBrowser2` 인터페이스는 DHTML 개체 모델에 액세스할 수 있도록 DHTML 컨트롤에서 사용할 수 있습니다.  
  
 ATL 컨트롤 마법사 HTML 리소스 및.cpp 파일에서 기본 코드를 사용 하 여 컨트롤을 생성합니다. 컴파일 및 마법사에 의해 생성 된 컨트롤을 실행 하 고 웹 브라우저 또는 ActiveX 컨트롤 테스트 컨테이너에서 컨트롤을 볼 수 있습니다. 아래 그림은 테스트 컨테이너에 표시 된 세 개의 단추를 사용 하 여 기본 ATL DHTML 컨트롤을 보여줍니다.  
  
 ![ATL DHTML 컨트롤](../atl/media/vc52en2.gif "vc52en2")  
  
 참조 [ATL DHTML 컨트롤 만들기](../atl/creating-an-atl-dhtml-control.md) 여 DHTML 컨트롤 빌드를 시작 합니다. 참조 [속성 및 이벤트 테스트 컨테이너를 사용 하 여 테스트](../mfc/testing-properties-and-events-with-test-container.md) 테스트 컨테이너에 액세스 하는 방법에 대 한 정보에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [DHTML 컨트롤에 대 한 지원](../atl/atl-support-for-dhtml-controls.md)

