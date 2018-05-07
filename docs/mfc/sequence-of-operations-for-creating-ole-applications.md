---
title: OLE 응용 프로그램을 만들기 위한 작업 시퀀스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE applications [MFC], creating
- OLE applications [MFC]
- applications [OLE], creating
- applications [OLE]
ms.assetid: 84b0f606-36c1-4253-9cea-44427f0074b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 412fa5c104d6e85bcaa6ba3703cc8c7ba535f25f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="sequence-of-operations-for-creating-ole-applications"></a>OLE 응용 프로그램을 만드는 작업 시퀀스
다음 표에서 OLE 연결 및 포함 응용 프로그램을 만드는 사용자의 역할 및 프레임 워크의 역할을 보여 줍니다. 이러한 수행 하려면 단계의 시퀀스 하는 대신 사용할 수 있는 옵션을 나타냅니다.  
  
### <a name="creating-ole-applications"></a>OLE 응용 프로그램 만들기  
  
|작업|너 해|프레임 워크|  
|----------|------------|------------------------|  
|COM 구성 요소를 만듭니다.|MFC 응용 프로그램 마법사를 실행 합니다. 선택 **풀 서버** 또는 **미니 서버** 에 **복합 문서 지원** 탭 합니다.|프레임 워크는 COM 구성 요소 기능을 사용할 수 있는 기초 응용 프로그램을 생성 합니다. 모든 COM 기능을 약간만 수정 하 여 기존 응용 프로그램에 전송할 수 있습니다.|  
|처음부터 컨테이너 응용 프로그램을 만듭니다.|MFC 응용 프로그램 마법사를 실행 합니다. 선택 **컨테이너** 에 **복합 문서 지원** 탭 합니다. 클래스 뷰를 사용 하 여 소스 코드 편집기로 이동 합니다. COM 처리기 함수에 대 한 코드를 입력 합니다.|프레임 워크는 COM 구성 요소 (서버) 응용 프로그램에 의해 생성 되는 COM 개체를 삽입할 수 있는 기초 응용 프로그램을 생성 합니다.|  
|응용 프로그램 자동화를 지 원하는 처음부터 새로 만듭니다.|MFC 응용 프로그램 마법사를 실행 합니다. 선택 **자동화** 에서 **고급 기능** 탭 합니다. 클래스 뷰를 사용 하 여 자동화에 대 한 응용 프로그램의 메서드와 속성을 노출 합니다.|프레임 워크 활성화 하 고 다른 응용 프로그램에서 자동화할 수 있는 기초 응용 프로그램을 생성 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [프레임 워크에서 빌드](../mfc/building-on-the-framework.md)   
 [MFC 응용 프로그램을 빌드하기 위한 작업 시퀀스](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [ActiveX 컨트롤을 만드는 작업 시퀀스](../mfc/sequence-of-operations-for-creating-activex-controls.md)   
 [데이터베이스 응용 프로그램을 만드는 작업 시퀀스](../mfc/sequence-of-operations-for-creating-database-applications.md)

