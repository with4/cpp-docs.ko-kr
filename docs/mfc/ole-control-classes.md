---
title: "OLE 컨트롤 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- ActiveX classes [MFC]
- custom controls [MFC], classes
- ActiveX controls [MFC], OLE control classes
- ActiveX control classes [MFC]
- OLE controls [MFC], classes
- OLE control classes [MFC]
- reusable component classes [MFC]
ms.assetid: 96495ec3-319e-4163-b839-1af0428ed9dd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e61d0ca8ed269557efbd566da1aca160ef669e83
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ole-control-classes"></a>OLE 컨트롤 클래스
이들은 OLE 컨트롤을 작성할 때 사용 하는 기본 클래스입니다. `COleControlModule` OLE 컨트롤 모듈에서 클래스와 비슷합니다는 [CWinApp](../mfc/reference/cwinapp-class.md) 응용 프로그램의 클래스입니다. 각 모듈에는 하나 이상의 OLE 컨트롤; 구현 이러한 컨트롤은 `COleControl` 개체입니다. 이러한 컨트롤을 사용 하는 컨테이너와 통신 `CConnectionPoint` 개체입니다.  
  
 `CPictureHolder` 및 `CFontHolder` 클래스는 사진 및 글꼴에 대 한 COM 인터페이스를 캡슐화 하는 동안는 `COlePropertyPage` 및 `CPropExchange` 클래스 속성 페이지 및 컨트롤에 대 한 지 속성 속성을 구현 하는 데 도움이 됩니다.  
  
 [COleControlModule](../mfc/reference/colecontrolmodule-class.md)  
 대체는 `CWinApp` OLE 컨트롤 모듈에 대 한 클래스입니다. 파생 되는 `COleControlModule` OLE 컨트롤 모듈 개체를 개발 하는 클래스입니다. OLE 컨트롤의 모듈을 초기화 하기 위한 멤버 함수를 제공 합니다.  
  
 [COleControl](../mfc/reference/colecontrol-class.md)  
 파생 되는 `COleControl` OLE 컨트롤을 개발 하는 클래스입니다. 파생 된 `CWnd`,이 클래스 이벤트 발생과 메서드 및 속성을 지 원하는 기능이 같은 추가 특정 기능을 포함 하 고 Windows 창 개체의 모든 기능을 상속 합니다.  
  
 [CConnectionPoint](../mfc/reference/cconnectionpoint-class.md)  
 `CConnectionPoint` 클래스는 특수 한 유형의 연결 지점 이라는 다른 OLE 개체와 통신 하는 데 사용 되는 인터페이스를 정의 합니다. 연결 지점 이벤트를 발생 시키고 등의 다른 개체에 대 한 작업을 시작 하 고 변경 알림을 할 수 있는 송신 인터페이스를 구현 합니다.  
  
 [CPictureHolder](../mfc/reference/cpictureholder-class.md)  
 Windows 그림 개체의 기능을 캡슐화 하며 `IPicture` COM 인터페이스; OLE 컨트롤의 사용자 지정 그림 속성을 구현 하는 데 사용 합니다.  
  
 [CFontHolder](../mfc/reference/cfontholder-class.md)  
 Windows 글꼴 개체의 기능을 캡슐화 하며 `IFont` COM 인터페이스; OLE 컨트롤의 스톡 글꼴 속성을 구현 하는 데 사용 합니다.  
  
 [에서는 COlePropertyPage](../mfc/reference/colepropertypage-class.md)  
 대화 상자와 유사한 그래픽 인터페이스에서 제어 OLE의 속성을 표시 합니다.  
  
 [CPropExchange](../mfc/reference/cpropexchange-class.md)  
 OLE 컨트롤의 속성 지 속성 구현을 지원합니다. 유사 [CDataExchange](../mfc/reference/cdataexchange-class.md) 대화 상자에 대 한 합니다.  
  
 [CMonikerFile](../mfc/reference/cmonikerfile-class.md)  
 모니커 또는 문자열 표현으로 모니커를 만들 수 있는 걸리며 모니커 이름의 스트림을에 동기적으로 바인딩합니다.  
  
 [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)  
 작동 방식은 `CMonikerFile`있지만 모니커 이름의 스트림의을 비동기적으로 모니커에 바인딩합니다.  
  
 [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)  
 비동기적으로 로드할 수 있는 OLE 컨트롤 속성을 구현합니다.  
  
 [CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md)  
 비동기적으로 전송되고 메모리 파일에 캐싱되는 OLE 컨트롤 속성을 구현합니다.  
  
 [COleCmdUI](../mfc/reference/colecmdui-class.md)  
 액티브 문서 컨테이너의 사용자 인터페이스 (예: FileNew, 열기, 인쇄, 및 등)에서 시작 명령을 받을 수 있으며이 컨테이너가 활성 문서의 사용자 인터페이스에서 시작 명령을 받을 수 있도록 합니다.  
  
 [COleSafeArray](../mfc/reference/colesafearray-class.md)  
 임의의 형식 및 차원 배열에서 작동 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)

