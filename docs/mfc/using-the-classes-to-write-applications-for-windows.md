---
title: Windows 용 응용 프로그램을 작성 하는 클래스를 사용 하 여 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows applications [MFC], MFC application framework
- MFC, application development
- applications [OLE], MFC application framework
- MFC ActiveX controls [MFC], creating
- OLE applications [MFC], MFC application framework
- database applications [MFC], creating
ms.assetid: 73f63470-857d-43dd-9a54-b38b7be0f1b7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa126f2772e1672a1484453fdffdd487b6c45959
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="using-the-classes-to-write-applications-for-windows"></a>클래스를 사용하여 Windows 응용 프로그램 작성
Microsoft Foundation 클래스 (MFC) 라이브러리의 클래스를 함께 "응용 프로그램 프레임 워크," Windows 운영 체제에 대 한 응용 프로그램을 빌드할 구성 합니다. 매우 일반적인 수준에서 프레임 워크 응용 프로그램의 구조를 정의 하 고 표준 사용자 인터페이스를 구현 하는 구조에 배치할 수를 제공 합니다. 나머지의 구조를 작성 하는 프로그래머 작업은 응용 프로그램에 관련 된 이러한 일 들은입니다. 먼저 매우 철저 하 게 시작 응용 프로그램에 대 한 파일을 만들려면 MFC 응용 프로그램 마법사를 사용 하 여 얻을 수 있습니다. 코드 및 클래스 라이브러리에 이러한 요소를 연결할 명령을 클래스 뷰 사용자 인터페이스 요소를 시각적으로 디자인 하려면 Microsoft Visual c + + 리소스 편집기를 사용 하 여 응용 프로그램별 논리를 구현 합니다.  
  
 버전 3.0 이상 MFC 프레임 워크는 Win32 플랫폼을 비롯 하 여 Microsoft Windows 95 및 이후 버전에 대 한 프로그래밍 및 Windows NT 버전 3.51 이상를 지원합니다. 다중 스레딩 Win32 MFC 지원 포함 됩니다. 사용 하 여 버전 1.5*x* 16 비트 프로그래밍을 수행 해야 합니다.  
  
 문서이에서는 응용 프로그램 프레임 워크의 개요를 제공합니다. 또한 응용 프로그램 및 생성 방법 구성 하는 주요 개체를 탐색 합니다. 다음이 문서에서 다루는 항목 간에 다음과 같습니다.  
  
-   [프레임 워크](../mfc/framework-mfc.md)합니다.  
  
-   프레임 워크와 사용자 코드에 설명 된 대로 간의 분업 [프레임 워크에서 빌드](../mfc/building-on-the-framework.md)합니다.  
  
-   [응용 프로그램 클래스](../mfc/cwinapp-the-application-class.md), 응용 프로그램 수준 기능을 캡슐화 하는입니다.  
  
-   어떻게 [문서 템플릿](../mfc/document-templates-and-the-document-view-creation-process.md) 작성 및 문서와 연결 된 뷰를 관리 및 프레임 창입니다.  
  
-   클래스 [CWnd](../mfc/window-objects.md), 모든 창의 루트 기본 클래스입니다.  
  
-   [그래픽 개체](../mfc/graphic-objects.md), 펜과 브러시 등입니다.  
  
 프레임 워크의 다른 부분 다음과 같습니다.  
  
-   [창 개체 소멸 시키기: 개요](../mfc/window-objects.md)  
  
-   [메시지 처리 및 매핑](../mfc/message-handling-and-mapping.md)  
  
-   [CObject, MFC의 루트 기본 클래스](../mfc/using-cobject.md)  
  
-   [문서/뷰 아키텍처](../mfc/document-view-architecture.md)  
  
-   [대화 상자](../mfc/dialog-boxes.md)  
  
-   [컨트롤](../mfc/controls-mfc.md)  
  
-   [컨트롤 막대](../mfc/control-bars.md)  
  
-   [OLE](../mfc/ole-in-mfc.md)  
  
-   [메모리 관리](../mfc/memory-management.md)  
  
     Windows 운영 체제에 대 한 응용 프로그램을 작성할 때의 이점은 제공할 뿐 아니라 MFC 하면 훨씬 쉽게 특히 OLE 연결 및 포함 기술을 사용 하 여 응용 프로그램을 작성 합니다. 있습니다 수 응용 프로그램이 OLE 비주얼 편집 컨테이너 OLE 비주얼 편집 서버, 또는 둘 다 있으며 다른 응용 프로그램의 응용 프로그램 개체를 사용 하거나 원격으로 수 있도록 자동화를 추가할 수 있습니다.  
  
-   [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)  
  
     OLE 컨트롤 개발 키트 (CDK) 프레임 워크와 완전히 통합 되었습니다. 이 문서에서는 MFC로 ActiveX 컨트롤 개발의 개요를 제공합니다. (ActiveX 컨트롤 된 이전의 OLE 컨트롤입니다.)  
  
-   [데이터베이스 프로그래밍](../data/data-access-programming-mfc-atl.md)  
  
     또한 mfc를 두 가지 쓰기 데이터 액세스를 단순화 하는 데이터베이스 클래스 응용 프로그램입니다. ODBC 데이터베이스 클래스를 사용 하 여 데이터베이스 ODBC (Open Connectivity) 드라이버를 통해 데이터베이스에 연결, 테이블에서 레코드를 선택 하 수 레코드 정보를 표시 한 화면을 형성 합니다. 개체 DAO (Data Access) 클래스를 사용 하면 작업할 수 데이터베이스 Microsoft Jet 데이터베이스 엔진 또는 ODBC 데이터 소스를 포함 하 여 외부 (비 Jet) 데이터 원본을 통해.  
  
     또한 MFC가 완전히 유니코드를 사용 하는 응용 프로그램을 작성 하기 위한 설정 및 멀티 바이트 문자 집합 (MBCS), 특히 더블 바이트 문자 집합 (DBCS).  
  
 MFC 설명서에 대 한 일반 지침을 참조 하십시오. [일반 MFC 항목](../mfc/general-mfc-topics.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [일반 MFC 항목](../mfc/general-mfc-topics.md)

