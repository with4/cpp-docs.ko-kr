---
title: DHTML 컨트롤에 대 한 ATL 지원 | Microsoft Docs
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
- DHTML controls
ms.assetid: 4ba98098-da5d-4362-96ad-8372f816c307
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f57fc841ba2eb3473ccb866df7333ebd24583d40
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32355524"
---
# <a name="atl-support-for-dhtml-controls"></a>DHTML 컨트롤에 대한 ATL 지원
ATL을 사용 하 여 DHTML (동적 HTML) 기능이 있는 컨트롤을 만들 수 있습니다. ATL DHTML 컨트롤:  
  
-   WebBrowser 컨트롤을 호스팅합니다.  
  
-   HTML, DHTML 컨트롤의 사용자 인터페이스 (UI) 사용 여부를 지정 합니다.  
  
-   WebBrowser 개체 및 해당 메서드는 인터페이스를 통해 액세스 하는 [IWebBrowser2](https://msdn.microsoft.com/library/aa752127.aspx)합니다.  
  
-   C + + 코드와 HTML 간의 통신을 관리합니다.  
  
 DHTML 컨트롤 DHTML 컨트롤에는 추가 디스패치 인터페이스 점을 제외 하 고 다른 ATL 컨트롤와 비슷합니다. 그림을 참조 [DHTML 컨트롤 프로젝트의 요소를 식별](../atl/identifying-the-elements-of-the-dhtml-control-project.md) 기본 DHTML 프로젝트에서 제공 하는 인터페이스에 대 한 예제입니다.  
  
 웹 브라우저 또는 ActiveX Control Test Container 같은 다른 컨테이너에서 ATL DHTML 컨트롤을 볼 수 있습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [DHTML 컨트롤 프로젝트의 요소 식별](../atl/identifying-the-elements-of-the-dhtml-control-project.md)  
 DHTML 컨트롤 프로젝트의 요소에 설명 합니다.  
  
 [DHTML에서 C++ 코드 호출](../atl/calling-cpp-code-from-dhtml.md)  
 DHTML 컨트롤에서 c + + 코드를 호출 하는 예를 제공 합니다.  
  
 [ATL DHTML 컨트롤 만들기](../atl/creating-an-atl-dhtml-control.md)  
 DHTML 컨트롤을 만드는 단계를 나열 합니다.  
  
 [ATL DHTML 컨트롤 테스트](../atl/testing-the-atl-dhtml-control.md)  
 빌드하고 초기 DHTML 컨트롤 프로젝트를 테스트 하는 방법을 보여 줍니다.  
  
 [ATL DHTML 컨트롤 수정](../atl/modifying-the-atl-dhtml-control.md)  
 컨트롤에 일부 기능을 추가 하는 방법을 보여 줍니다.  
  
 [변경 된 ATL DHTML 컨트롤 테스트](../atl/testing-the-modified-atl-dhtml-control.md)  
 빌드하고 컨트롤의 추가 기능을 테스트 하는 방법을 보여 줍니다.  
  
## <a name="related-sections"></a>관련 단원  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 액티브 템플릿 라이브러리를 사용하여 프로그래밍하는 방법에 대한 개념 항목의 링크를 제공합니다.

