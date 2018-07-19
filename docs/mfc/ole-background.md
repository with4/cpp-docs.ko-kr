---
title: OLE 백그라운드 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE, about OLE
ms.assetid: 5f654eb5-66b1-40c9-9215-bb85356a67f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 262eee08e1bea410fd8e6d12d9209d35877e4a5f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355563"
---
# <a name="ole-background"></a>OLE 백그라운드
OLE를 만들고 항목 또는 "개체"를 포함 하는 문서를 편집할 수 있는 메커니즘이 만들어집니다는 여러 응용 프로그램.  
  
> [!NOTE]
>  OLE 개체 연결 및 포함에 대 한 약어 원래 합니다. 그러나 이제 라고 OLE로 합니다. 연결 및 포함 관련이 없는 OLE의 부분 액티브 기술 부분이 됩니다.  
  
 복합 문서 라고 하는 OLE 문서의 다양 한 유형의 데이터 또는 구성 요소를 원활 하 게 통합 합니다. 사운드 클립, 스프레드시트 및 비트맵은 일반적인 예 OLE 문서에 있는 구성 요소입니다. OLE 지원 응용 프로그램에 사용자를가 다른 응용 프로그램; 간에 전환에 대 한 걱정 없이 OLE 문서를 사용할 수 있습니다. OLE를 전환 하는 수행 하지 않습니다.  
  
 복합 문서를 만들고 컨테이너 응용 프로그램 및 서버 응용 프로그램이 나 컨테이너 문서 내에서 항목을 만드는 응용 프로그램 구성 요소를 사용 합니다. 작성 하는 응용 프로그램의 컨테이너, 서버, 또는 둘 다를 수 있습니다.  
  
 OLE는 모든 응용 프로그램 간의 원활한 상호 작용의 목표에 대해 작동 하는 여러 다른 개념을 통합 합니다. 다양 한이 분야는 다음과 같습니다.  
  
 연결 및 포함  
 연결 및 포함 된 다른 응용 프로그램에서 생성 된 OLE 문서 내에 만들어진 항목을 저장 하는 두 가지 방법입니다. 둘 사이의 차이점에 대 한 일반적인 내용은 문서 참조 [OLE 백그라운드: 연결 및 포함](../mfc/ole-background-linking-and-embedding.md)합니다. 자세한 내용은 문서를 참조 하십시오. [컨테이너](../mfc/containers.md) 및 [서버](../mfc/servers.md)합니다.  
  
 내부 활성화 (시각적 편집)  
 컨텍스트에서 컨테이너 문서의 포함 된 항목을 활성화 한 위치에서 활성화 또는 비주얼 편집 라고 합니다. 컨테이너 응용 프로그램의 인터페이스는 포함된 된 항목을 생성 한 구성 요소 응용 프로그램의 기능을 통합으로 변경 합니다. 연결 된 항목 실제 데이터 항목에 대 한 링크를 포함 하는 응용 프로그램의 컨텍스트 외부의 별도 파일에 들어 있으므로 전체에서 활성화 되지 않습니다. 내부 활성화에 대 한 자세한 내용은 문서 참조 [활성화](../mfc/activation-cpp.md)합니다.  
  
> [!NOTE]
>  연결 및 포함 하 고 내부 활성화 OLE 비주얼 편집의 주요 기능을 제공 합니다.  
  
 자동화  
 자동화를 다른 응용 프로그램 실행 하는 하나의 응용 프로그램을 허용 합니다. 구동 응용 프로그램 자동화 클라이언트 라고 하 고 구동 되 고 응용 프로그램 서버 또는 자동화 구성 요소 라고도 합니다. 자동화에 대 한 자세한 내용은 문서를 참조 [자동화 클라이언트](../mfc/automation-clients.md) 및 [자동화 서버](../mfc/automation-servers.md)합니다.  
  
> [!NOTE]
>  자동화는 OLE 및 액티브 기술 컨텍스트 모두에서 작동합니다. Com 기반 개체를 자동화할 수 있습니다.  
  
 복합 파일  
 OLE 응용 프로그램에 대 한 복합 문서의 구조적 저장을 간소화 하는 표준 파일 형식을 제공 하는 복합 파일입니다. 복합 파일 내에서 저장소 디렉터리의 여러 기능 있고 스트림 파일의 여러 기능입니다. 이 기술은 구조적된 저장소를 라고도 합니다. 복합 파일에 대 한 자세한 내용은 문서 참조 [컨테이너: 복합 파일](../mfc/containers-compound-files.md)합니다.  
  
 단일형 데이터 전송  
 균일 한 데이터 전송 (UDT)는 데이터를 보내고 받을 데이터를 전송 하기로 선택 하는 실제 방법에 관계 없이 표준 방식를 허용 하는 인터페이스의 집합입니다. 기본 데이터를 전송 하는 UDT forms 끌어서 놓습니다. UDT는 이제 클립보드 및 동적 데이터 교환 (DDE) 등의 기존 Windows 데이터 전송에 대 한 기준으로 사용 됩니다. UDT에 대 한 자세한 내용은 문서 참조 [데이터 개체 및 데이터 소스 (OLE)](../mfc/data-objects-and-data-sources-ole.md)합니다.  
  
 끌어서 놓기  
 끌어서 놓기는 사용 하기 쉬운, 직접 조작 기술 응용 프로그램을 windows 응용 프로그램 내에서 또는 응용 프로그램에 단일 창 내 에서도 데이터를 전송 합니다. 데이터를 전송 선택한 원하는 대상으로 끌어 놓을 합니다. 끌어서 놓기 단일형 데이터 전송에 기반 합니다. 끌어서 놓기에 대 한 자세한 내용은 문서 참조 [끌어서 놓기](../mfc/drag-and-drop-ole.md)합니다.  
  
 구성 요소 개체 모델  
 OLE 개체는 서로 통신할 때 사용 되는 인프라를 제공 하는 구성 요소 개체 모델 (COM). MFC OLE 클래스는 COM 프로그래머에 대 한 단순화합니다. COM는 COM 개체 기반이 OLE와 액티브 기술 하기 때문에 일부 액티브 기술입니다. COM에 대 한 자세한 내용은 참조는 [라이브러리 ATL (액티브 템플릿)](../atl/active-template-library-atl-concepts.md) 항목입니다.  
  
 더 중요 OLE 항목 중 일부는 다음 문서에 포함 됩니다.  
  
-   [OLE 백그라운드: 연결 및 포함](../mfc/ole-background-linking-and-embedding.md)  
  
-   [OLE 백그라운드: 컨테이너 및 서버](../mfc/ole-background-containers-and-servers.md)  
  
-   [OLE 백그라운드 구현 전략](../mfc/ole-background-implementation-strategies.md)  
  
-   [OLE 백그라운드: MFC 구현](../mfc/ole-background-mfc-implementation.md)  
  
 위의 문서에서 찾을 수 없는 일반 OLE 정보에 대 한 MSDN에서 OLE에 대 한 검색 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE](../mfc/ole-in-mfc.md)

