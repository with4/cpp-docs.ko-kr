---
title: ActiveX 컨트롤을 만드는 작업 시퀀스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], creating
- ActiveX controls [MFC], creating
- sequence [MFC], for creating ActiveX controls
- OLE controls [MFC], MFC
- sequence [MFC]
ms.assetid: 7d868c53-a0af-4ef6-a89c-e1c03c583a53
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: caf4c74f2263505ad5d7112021003f92c85a4b84
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33380372"
---
# <a name="sequence-of-operations-for-creating-activex-controls"></a>ActiveX 컨트롤을 만드는 작업 시퀀스
다음 표에서 사용자의 역할와 프레임 워크의 ActiveX 컨트롤 (이전의 OLE 컨트롤)을 만드는을 보여 줍니다.  
  
### <a name="creating-activex-controls"></a>ActiveX 컨트롤 만들기  
  
|작업|너 해|프레임 워크|  
|----------|------------|------------------------|  
|ActiveX 컨트롤 프레임 워크를 만듭니다.|컨트롤을 만드는 MFC ActiveX 컨트롤 마법사를 실행 합니다. 옵션 페이지에서 원하는 옵션을 지정 합니다. 옵션은 프로젝트, 라이선스, 서브클래싱, 및에 대 한 상자 메서드에 컨트롤의 이름과 유형을 포함 됩니다.|MFC ActiveX 컨트롤 마법사 응용 프로그램, 컨트롤 및 속성 페이지 또는 페이지;에 대 한 소스 파일을 포함 하 여 기본 기능을 통해 ActiveX 컨트롤에 대 한 파일을 만듭니다. 리소스 파일입니다. 프로젝트 파일; 고 사양에 맞는 모든는 다른 사용자에 게 합니다.|  
|뿐만 아니라 사용자 고유의 코드 줄을 추가 하지 않고 컨트롤 및 ActiveX 컨트롤 마법사에서 제공 하는 기능을 참조 하십시오.|ActiveX 컨트롤을 빌드하고 Internet Explorer로 테스트 또는 [TSTCON 샘플](../visual-cpp-samples.md)합니다.|실행 중인 컨트롤에 크기를 조정 하 고 이동할 수 있습니다. 또한는 **정보 상자** 호출할 수 있는 메서드 (선택 됨) 하는 경우.|  
|컨트롤의 메서드 및 속성을 구현 합니다.|컨트롤의 데이터에 노출 된 인터페이스를 제공 하는 멤버 함수를 추가 하 여 컨트롤별 메서드 및 속성을 구현 합니다. 데이터 구조를 유지 하 고 필요할 때 이벤트를 발생 시키는 이벤트 처리기를 사용 하는 멤버 변수를 추가 합니다.|프레임 워크 컨트롤의 이벤트, 속성 및 메서드, 속성 및 메서드 구현 방법에 초점을 맞출 수를 지원 하기 위해 이미 정의 합니다. 기본 속성 페이지를 볼 수 있고 기본 상자에 대 한 메서드를 제공 합니다.|  
|컨트롤의 속성 페이지 또는 페이지를 생성 합니다.|Visual c + + 리소스 편집기를 사용 하 여 시각적으로 인터페이스를 편집 하려면 컨트롤의 속성 페이지:<br /><br /> -추가 속성 페이지를 만듭니다.<br />-만들기 및 비트맵, 아이콘 및 커서를 편집 합니다.<br /><br /> 대화 상자 편집기에서 속성 페이지를 테스트할 수도 있습니다.|MFC 응용 프로그램 마법사에서 만든 기본 리소스 파일에 필요한 리소스를 많이 제공 합니다. Visual c + +를 사용 하 여 기존 리소스를 편집 하 고 쉽게 하 고 시각적으로 새 리소스를 추가할 수 있습니다.|  
|컨트롤의 이벤트, 메서드 및 속성을 테스트 합니다.|컨트롤을 다시 빌드하고 테스트 컨테이너를 사용 하 여 처리기를 올바르게 작동 하는지 테스트 합니다.|컨트롤의 메서드를 호출 하 고 해당 속성 또는 테스트 컨테이너를 속성 페이지 인터페이스를 통해 조작할 수 있습니다. 또한 테스트 컨테이너를 사용 하 여 컨트롤에서 발생 하는 추적 이벤트 및 알림 컨트롤의 컨테이너에서 수신 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [프레임 워크에서 빌드](../mfc/building-on-the-framework.md)   
 [MFC 응용 프로그램을 빌드하기 위한 작업 시퀀스](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [OLE 응용 프로그램을 만들기 위한 작업 시퀀스](../mfc/sequence-of-operations-for-creating-ole-applications.md)   
 [데이터베이스 응용 프로그램을 만드는 작업 시퀀스](../mfc/sequence-of-operations-for-creating-database-applications.md)

