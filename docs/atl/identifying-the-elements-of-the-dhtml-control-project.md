---
title: "Identifying the Elements of the DHTML Control Project | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DHTML controls, ATL 지원"
  - "HTML 컨트롤, ATL 지원"
ms.assetid: b627547a-3768-4346-9900-4b7a21fb8e27
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Identifying the Elements of the DHTML Control Project
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

대부분의 DHTML 컨트롤 코드와 ATL 컨트롤에 대해 생성 됩니다.  제네릭 코드에 대 한 기본적인 이해를 통해 작업의  [ATL 자습서](../atl/active-template-library-atl-tutorial.md), 읽고 섹션  [ATL 프로젝트 만들기](../atl/reference/creating-an-atl-project.md) 및  [ATL COM 개체의 기본 사항](../atl/fundamentals-of-atl-com-objects.md).  
  
 DHTML 컨트롤 모든 ATL 컨트롤과 유사 제외:  
  
-   컨트롤을 구현 하는 일반 인터페이스 외에 C\+\+ 코드와 HTML 사용자 인터페이스 \(UI\) 간의 통신에 사용 되는 추가 인터페이스를 구현 합니다.  이 인터페이스를 사용 하 여 C\+\+ 코드로 HTML UI를 호출 합니다.  
  
-   HTML UI 컨트롤에 대 한 리소스를 만듭니다.  
  
-   DHTML 개체 모델 멤버 변수를 통해 액세스할 수 있도록 `m_spBrowser`, 스마트 포인터 형식에  [IWebBrowser2](https://msdn.microsoft.com/en-us/library/aa752127.aspx).  이 포인터를 사용 하 여 DHTML 개체 모델의 일부에 액세스할 수 있습니다.  
  
 다음 그래픽 DLL, DHTML 컨트롤, 웹 브라우저, HTML 리소스 사이의 관계를 보여 줍니다.  
  
 ![DHTML 컨트롤 프로젝트의 요소](../atl/media/vc52en1.png "vc52EN1")  
  
> [!NOTE]
>  이 그래픽의 이름을 자리 표시자입니다.  ATL 컨트롤 마법사에서 할당 이름 컨트롤에 노출 된 인터페이스와 HTML 리소스의 이름은 기반으로 합니다.  
  
 이 그림에서 요소는 다음과 같습니다.  
  
-   **DLL** 는 ATL 프로젝트 마법사를 사용 하 여 만든 DLL입니다.  
  
-   **DHTML 컨트롤** \(`m_spBrowser`\)는 DHTML 컨트롤, ATL 개체 마법사를 사용 하 여 만든.  이 컨트롤은 웹 브라우저 개체와 해당 메서드 웹 브라우저 개체 인터페이스를 통해 액세스 하는  **IWebBrowser2**.  컨트롤 자체를 컨트롤에 필요한 다른 표준 인터페이스 외에 다음 두 개의 인터페이스를 노출 합니다.  
  
    -   **IDHCTL1** 컨트롤 컨테이너에 의해서만 사용에 의해 노출 된 인터페이스.  
  
    -   **IDHCTLUI1** C\+\+ 코드와 HTML 사용자 인터페이스 간의 통신에 대 한 디스패치 인터페이스입니다.  웹 브라우저 컨트롤의 디스패치 인터페이스를 사용 하 여 컨트롤을 표시 합니다.  호출 하 여 컨트롤의 사용자 인터페이스에서이 디스패치 인터페이스의 다양 한 메서드를 호출할 수 있습니다 `window.external`, 호출 하려는이 디스패치 인터페이스에는 메서드 이름 다음에 이어집니다.  액세스할 수 `window.external` 에서이 컨트롤에 대 한 UI를 구성 하는 HTML 스크립트 태그에서.  리소스 파일에서 외부 메서드를 호출 하는 방법에 대 한 자세한 내용은  [를 호출 하는 C\+\+ 코드에서 DHTML](../atl/calling-cpp-code-from-dhtml.md).  
  
-   **IDR\_CTL1** HTML 리소스의 리소스 ID입니다.  이 경우 해당 파일 이름 dhctl1ui.htm를입니다.  DHTML 컨트롤 표준 HTML 태그 및 텍스트 편집기를 사용 하 여 편집할 수 있는 외부 창 디스패치 명령을 포함 하는 HTML 리소스를 사용 합니다.  
  
-   **웹 브라우저** 웹 브라우저는 HTML에서 HTML 리소스를 기반으로 컨트롤의 UI를 표시 합니다.  웹 브라우저에 대 한 포인터  **IWebBrowser2** 인터페이스는 DHTML 개체 모델에 액세스할 수 있도록 하려면 DHTML 컨트롤에서 사용할 수 있습니다.  
  
 ATL 컨트롤 마법사는 HTML 리소스와.cpp 파일에서 기본 코드를 사용 하 여 컨트롤을 생성합니다.  컴파일 및 마법사에 의해 생성 되는 컨트롤을 실행 하 고 웹 브라우저 또는 ActiveX 컨트롤 테스트 컨테이너에서 컨트롤을 볼 수 있습니다.  아래 그림 기본 ATL DHTML 컨트롤 테스트 컨테이너에 표시 되는 세 개의 단추와 같습니다.  
  
 ![ATL DHTML 컨트롤](../atl/media/vc52en2.png "vc52EN2")  
  
 참조  [ATL DHTML 컨트롤 만들기](../atl/creating-an-atl-dhtml-control.md) DHTML 컨트롤 빌드를 시작할 수 있습니다.  참조  [속성 및 이벤트 테스트 컨테이너 테스트](../mfc/testing-properties-and-events-with-test-container.md) 테스트 컨테이너에 액세스 하는 방법에 대 한 정보.  
  
## 참고 항목  
 [DHTML 컨트롤에 대한 지원](../atl/atl-support-for-dhtml-controls.md)