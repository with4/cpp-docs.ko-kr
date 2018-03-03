---
title: "DHTML 컨트롤 프로젝트의 요소를 식별 합니다. | Microsoft Docs"
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
- HTML controls, ATL support
- DHTML controls, ATL support
ms.assetid: b627547a-3768-4346-9900-4b7a21fb8e27
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 74b271f56fe7c8d3345ce53de06a18a2700175f2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="identifying-the-elements-of-the-dhtml-control-project"></a>DHTML 컨트롤 프로젝트의 요소를 식별합니다.
ATL 컨트롤에 대 한 대부분 DHTML 제어 코드와 같습니다 만들어집니다. 제네릭 코드의 한 기본적인 이해에 대 한 작업을 통해는 [ATL 자습서](../atl/active-template-library-atl-tutorial.md), 섹션에서 확인 하 고 [ATL 프로젝트 만들기](../atl/reference/creating-an-atl-project.md) 및 [ATL COM 개체 기본 사항](../atl/fundamentals-of-atl-com-objects.md)합니다.  
  
 DHTML 컨트롤은 모든 ATL 컨트롤 비슷합니다 제외:  
  
-   컨트롤에서 구현 하는 일반 인터페이스 뿐만 아니라 c + + 코드와 HTML 사용자 인터페이스 (UI) 간의 통신에 사용 되는 추가 인터페이스를 구현 합니다. HTML UI이이 인터페이스를 사용 하 여 c + + 코드를 호출 합니다.  
  
-   UI 컨트롤에 대 한 HTML 리소스를 만듭니다.  
  
-   멤버 변수를 통해 DHTML 개체 모델에 대 한 액세스를 허용 `m_spBrowser`, 형식의 스마트 포인터는 [IWebBrowser2](https://msdn.microsoft.com/library/aa752127.aspx)합니다. 이 포인터를 사용 하 여 DHTML 개체 모델의 일부에 액세스 합니다.  
  
 다음 그래픽에서는 DLL, DHTML 컨트롤, 웹 브라우저 및 HTML 리소스 간의 관계를 보여 줍니다.  
  
 ![DHTML 컨트롤 프로젝트의 요소](../atl/media/vc52en1.gif "vc52en1")  
  
> [!NOTE]
>  이 그래픽의 이름에는 자리 표시자입니다. HTML 리소스 및 컨트롤에 노출 된 인터페이스의 이름이 ATL 컨트롤 마법사에서 부여한 이름을 기반으로 합니다.  
  
 이 그림에는 요소는 합니다.  
  
-   **DLL 내** ATL 프로젝트 마법사를 사용 하 여 만든 DLL입니다.  
  
-   **DHTML 컨트롤** (`m_spBrowser`) The DHTML 컨트롤, ATL 개체 마법사를 사용 하 여 만들어집니다. 웹 브라우저 개체의 인터페이스를 통해 웹 브라우저 개체 및 해당 메서드를 액세스 하는이 컨트롤 **IWebBrowser2**합니다. 자체 컨트롤은 컨트롤에 필요한 다른 표준 인터페이스 외에도 다음 두 가지 인터페이스를 노출 합니다.  
  
    -   **IDHCTL1** 컨테이너에 의해서만 사용에 대 한 컨트롤에 의해 노출 되는 인터페이스입니다.  
  
    -   **IDHCTLUI1** c + + 코드와 HTML 사용자 인터페이스 간의 통신을 위해 디스패치 인터페이스입니다. 웹 브라우저 컨트롤을 표시 하도록 컨트롤의 디스패치 인터페이스를 사용 합니다. 이 디스패치 인터페이스의 다양 한 메서드를 호출 하 여 컨트롤의 사용자 인터페이스에서 호출할 수 있습니다 `window.external`, 호출 하려면이 디스패치 인터페이스의 메서드 이름입니다. 액세스 하는 것 `window.external` 이 컨트롤에 대 한 UI를 구성 하는 HTML 내에서 스크립트 태그에서 합니다. 리소스 파일에서 외부 메서드를 호출 하는 방법에 대 한 자세한 내용은 참조 [DHTML에서 c + + 코드 호출](../atl/calling-cpp-code-from-dhtml.md)합니다.  
  
-   **IDR_CTL1** HTML 리소스의 리소스 ID입니다. 파일 이름에는 경우 DHCTL1UI.htm입니다. DHTML 컨트롤 표준 HTML 태그 및 텍스트 편집기를 사용 하 여 편집할 수 있는 외부 창 디스패치 명령이 포함 된 HTML 리소스를 사용 합니다.  
  
-   **웹 브라우저** HTML에 HTML 리소스에 따라 컨트롤의 UI, 웹 브라우저에 표시 됩니다. 웹 브라우저에 대 한 포인터 **IWebBrowser2** 인터페이스는 DHTML 개체 모델에 대 한 액세스를 허용 하도록 DHTML 컨트롤에 사용할 수 있습니다.  
  
 ATL 컨트롤 마법사 HTML 리소스와.cpp 파일의 기본 코드에서 컨트롤을 생성합니다. 컴파일 및 마법사에 의해 생성 되는 컨트롤을 실행 하 고 웹 브라우저 또는 ActiveX 컨트롤 테스트 컨테이너에서 컨트롤을 볼 수 있습니다. 아래 그림에는 테스트 컨테이너에 표시 되는 세 가지 단추가 포함 된 기본 ATL DHTML 컨트롤 보여 줍니다.  
  
 ![ATL DHTML 컨트롤](../atl/media/vc52en2.gif "vc52en2")  
  
 참조 [ATL DHTML 컨트롤을 만드는](../atl/creating-an-atl-dhtml-control.md) DHTML 컨트롤 작성을 시작 하려면. 참조 [속성 및 이벤트 테스트 컨테이너와 테스트](../mfc/testing-properties-and-events-with-test-container.md) 테스트 컨테이너에 액세스 하는 방법에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [DHTML 컨트롤에 대 한 지원](../atl/atl-support-for-dhtml-controls.md)

