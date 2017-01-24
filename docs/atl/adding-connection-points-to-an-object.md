---
title: "Adding Connection Points to an Object | Microsoft Docs"
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
  - "연결 지점[C++], ATL 개체에 추가"
  - "Implement Connection Point ATL wizard"
ms.assetid: 843531be-4a36-4db0-9d54-e029b1a72a8b
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Adding Connection Points to an Object
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[ATL 자습서](../atl/active-template-library-atl-tutorial.md) 연결 지점 지 원하는 컨트롤을 만드는 방법, 이벤트를 추가 하는 방법 및 연결 지점을 구현 하는 방법을 보여 줍니다.  ATL 연결 지점으로 구현 된  [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) 클래스입니다.  
  
 연결 지점을 구현 하려면 두 가지 방법이 있습니다.  
  
-   컨트롤이 나 개체에 연결 지점을 추가 하 여 직접 나가는 이벤트 소스를 구현 합니다.  
  
-   다른 형식 라이브러리에 정의 된 연결 지점 인터페이스를 다시 사용 합니다.  
  
 두 경우 모두 작업 수행을 위해 형식 라이브러리 연결 지점 구현 마법사를 사용 합니다.  
  
### 컨트롤이 나 개체에 연결 지점을 추가 하려면  
  
1.  Dispinterface를.idl 파일 라이브러리 블록에서 정의 합니다.  ATL 컨트롤 마법사에서 컨트롤을 만들 때 연결 지점 지원을 사용 하면 dispinterface 이미 만들어집니다.  컨트롤을 만들 때 연결 지점 지원을 사용 하도록 설정 하지 않으면 수동으로 dispinterface를.idl 파일에 추가 해야 합니다.  다음 예제는 dispinterface의입니다.  나가는 인터페이스 디스패치 인터페이스가 아니어도 되지만 두 dispinterfaces이이 예제를 사용 하 여 여러 스크립트 언어를 VBScript 및 JScript 등이 필요 하므로:  
  
     [!code-cpp[NVC_ATL_Windowing#81](../atl/codesnippet/CPP/adding-connection-points-to-an-object_1.idl)]  
  
     Uuidgen.exe 또는 guidgen.exe 유틸리티를 사용 하는 GUID를 생성 합니다.  
  
2.  Dispinterface로 추가 된 `[default,source]` 개체는 프로젝트의.idl 파일의 coclass에 대 한 인터페이스.  ATL 컨트롤 마법사는 컨트롤을 만들 때 연결 지점 지원을 사용 하는 경우 다시 만들어집니다를 `[default,source`\] 항목.  이 항목을 수동으로 추가 하려면 굵게 줄을 추가 합니다.  
  
     [!code-cpp[NVC_ATL_Windowing#82](../atl/codesnippet/CPP/adding-connection-points-to-an-object_2.idl)]  
  
     .Idl 파일을 참조 하십시오의  [Circ](../top/visual-cpp-samples.md) 예제 ATL 샘플.  
  
3.  이벤트 인터페이스에 메서드와 속성을 추가 하려면 클래스 뷰를 사용 합니다.  클래스 뷰에서 클래스를 마우스 오른쪽 단추로 클릭 하 고  **추가** 클릭 하 고 바로 가기 메뉴에서  **추가연결 지점**.  
  
4.  에  **원본 인터페이스** 의 연결 지점 구현 마법사, 선택 목록 상자  **프로젝트의 인터페이스**.  인터페이스를 제어 하 고 키를 눌러 선택 하면  **확인**를 사용 합니다:  
  
    -   이벤트에 대 한 나가는 호출 하는 코드를 구현 하는 이벤트 프록시 클래스의 헤더 파일을 생성 합니다.  
  
    -   연결 지점 맵에 항목을 추가 합니다.  
  
     모든 형식 라이브러리는 컴퓨터에도 표시 됩니다.  사용자만 이러한 형식 라이브러리 중 하나를 다른 형식 라이브러리에 동일한 정확한 나가는 인터페이스를 구현 하려면 연결점을 정의 하려면 사용 해야 합니다.  
  
### 연결 지점 인터페이스를 다시 사용 하려면 다른 형식 라이브러리에서 정의  
  
1.  클래스 뷰에서 구현 클래스를 마우스 오른쪽 단추로 클릭 한  **BEGIN\_COM\_MAP** 매크로 지점으로  **추가** 클릭 하 고 바로 가기 메뉴에서  **추가연결점**.  
  
2.  연결 지점 구현 마법사, 인터페이스 및 형식 라이브러리에서 형식 라이브러리를 선택 하 고 클릭  **추가**.  
  
3.  하도록.idl 파일을 편집 합니다.  
  
    -   Dispinterface를.idl 파일에 사용 되는 이벤트 소스 개체를 복사 합니다.  
  
    -   사용 된  **importlib** 해당 형식 라이브러리를.  
  
## 참고 항목  
 [연결 지점](../atl/atl-connection-points.md)