---
title: 개체에 연결 지점 추가 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], adding to ATL objects
- Implement Connection Point ATL wizard
ms.assetid: 843531be-4a36-4db0-9d54-e029b1a72a8b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71f9d136ccdeded02303894195c7b8126acafd9c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="adding-connection-points-to-an-object"></a>개체에 연결 지점 추가
[ATL 자습서](../atl/active-template-library-atl-tutorial.md) 컨트롤을 만드는 방법을 연결 지점에 대 한 지원, 이벤트를 추가 하는 방법 및 연결 지점을 구현 하는 방법을 보여 줍니다. ATL 연결 지점을 구현 하는 [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) 클래스입니다.  
  
 연결점을 구현 하려면 두 가지 옵션이 있습니다.  
  
-   컨트롤이 나 개체에 연결 지점을 추가 하 여 사용자 지정 송신 이벤트 소스를 구현 합니다.  
  
-   다른 형식 라이브러리에 정의 된 연결 지점 인터페이스를 다시 사용 합니다.  
  
 두 경우 모두 연결 지점 구현 마법사 형식 라이브러리를 사용 하 여 작업을 수행 합니다.  
  
### <a name="to-add-a-connection-point-to-a-control-or-object"></a>컨트롤 또는 개체에 연결 요소를 추가 하려면  
  
1.  .Idl 파일의 라이브러리 블록에는 인터페이스를 정의 합니다. ATL 컨트롤 마법사를 사용 하 여 컨트롤을 만든 연결점에 대 한 지원을 설정한 경우 dispinterface 이미 만들어질 수 있습니다. 컨트롤을 만들 때 연결 지점에 대 한 지원을 설정 하지 않은,.idl 파일에는 dispinterface을 수동으로 추가 해야 합니다. 다음은 dispinterface의 예입니다. 송신 인터페이스가 디스패치 인터페이스 될 필요가 없지만 VBScript 및 JScript와 같은 여러 스크립트 언어 필요 하므로이 예에서는 두 개의 dispinterface이를 합니다.  
  
     [!code-cpp[NVC_ATL_Windowing#81](../atl/codesnippet/cpp/adding-connection-points-to-an-object_1.idl)]  
  
     Uuidgen.exe 또는 guidgen.exe 유틸리티를 사용 하 여 여 GUID를 생성 합니다.  
  
2.  으로 dispinterface 추가 `[default,source]` coclass 프로젝트의.idl 파일에서 개체에 대 한 인터페이스입니다. 다시 사용 하도록 설정한 연결 지점에 대 한 지원 컨트롤을 만들 때, ATL 컨트롤 마법사 만들어집니다는 `[default,source`] 항목입니다. 이 항목을 수동으로 추가 하려면 굵게 표시 된 줄을 추가 합니다.  
  
     [!code-cpp[NVC_ATL_Windowing#82](../atl/codesnippet/cpp/adding-connection-points-to-an-object_2.idl)]  
  
     .Idl 파일을 참조는 [Circ](../visual-cpp-samples.md) 예에 대 한 ATL 샘플입니다.  
  
3.  클래스 뷰를 사용 하 여 이벤트 인터페이스에 메서드 및 속성을 추가 합니다. 클래스 뷰에서 클래스를 마우스 오른쪽 단추로 클릭, 가리킨 **추가** 를 바로 가기 메뉴를 클릭 한 **연결 지점 추가**합니다.  
  
4.  에 **소스 인터페이스** 연결 지점 구현 마법사, 선택 목록 상자 **프로젝트의 인터페이스**합니다. 제어 및 키를 눌러에 대 한 인터페이스를 선택 하는 경우 **확인**를 수행 합니다.  
  
    -   이벤트에 대 한 보내는 호출에 있도록 코드를 구현 하는 이벤트 프록시 클래스 헤더 파일을 생성 합니다.  
  
    -   연결 지점 맵은에 항목을 추가 합니다.  
  
     또한 컴퓨터에 형식 라이브러리의 모든 목록이 나타납니다. 다른 형식 라이브러리에 정확히 동일한 송신 인터페이스를 구현 하려는 경우 연결 지점을 정의 하려면 이러한 다른 형식 라이브러리 중 하나를 사용 해야 합니다.  
  
### <a name="to-reuse-a-connection-point-interface-defined-in-another-type-library"></a>다른 형식 라이브러리에 정의 된 연결 지점 인터페이스를 다시 사용 하려면  
  
1.  구현 하는 클래스를 마우스 오른쪽 단추로 클릭 클래스 뷰에서 **BEGIN_COM_MAP** 매크로 가리키고 **추가** 를 바로 가기 메뉴를 클릭 한 **연결 지점 추가**합니다.  
  
2.  연결 지점 구현 마법사에서 형식 라이브러리의 형식 라이브러리와 인터페이스를 선택 하 고 클릭 **추가**합니다.  
  
3.  .Idl 파일을 편집 합니다.  
  
    -   이벤트 소스를 사용 하는 개체에 대 한.idl 파일에서 dispinterface를 복사 합니다.  
  
    -   사용 하 여 **importlib** 지침을 보려면 해당 형식 라이브러리.  
  
## <a name="see-also"></a>참고 항목  
 [연결 지점](../atl/atl-connection-points.md)

