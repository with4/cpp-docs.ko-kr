---
title: "MFC의 OLE | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC, OLE and
- OLE items
- OLE applications [MFC], about OLE
- OLE [MFC]
- OLE containers [MFC], about OLE
- applications [OLE], about OLE
- OLE component object model (COM)
ms.assetid: 5193479d-1239-4697-aea4-e82f92c707ab
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 38b2f6c936ff314f56e4b1868837729ad00efce4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ole-in-mfc"></a>MFC의 OLE
이 문서에서는 MFC를 사용 하 여 OLE 프로그래밍의 기본적인 사항을 설명 합니다. MFC는 OLE를 사용 하는 프로그램을 작성 하는 가장 쉬운 방법은 제공 합니다.  
  
-   활성화를 사용 하도록 OLE 비주얼 편집 (전체).  
  
-   실행 되도록 OLE 컨테이너 또는 서버로 합니다.  
  
-   끌어서 놓기 기능을 구현 하 합니다.  
  
-   날짜 및 시간 데이터는 되도록 합니다.  
  
-   MFC의 상태 데이터를 관리 하려면 모듈을 포함 하 여 내보낸 DLL 함수 시작 지점, OLE/COM 인터페이스 진입점 및 창 프로시저 진입점입니다.  
  
 사용할 수도 있습니다 [자동화](../mfc/automation.md) 또는 [원격 자동화](../mfc/remote-automation.md) 프로그램에서 다른 프로그램을 작동 하도록 합니다.  
  
> [!NOTE]
>  OLE 나타냅니다는 등의 기술 관련 연결 및, 포함 된 OLE 컨테이너, OLE 서버, OLE 항목, 내부 활성화 (또는 비주얼 편집) 추적기, 끌어서 놓기, 용어 및 메뉴 병합 합니다. 활성은 ActiveX 컨트롤 같은 구성 요소 개체 모델 (COM) 및 COM 기반 개체에 적용 됩니다 용어입니다. OLE 자동화 자동화를 라고 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [OLE 백그라운드](../mfc/ole-background.md)  
 OLE에 설명 하 고 작동 방법에 대 한 개념 정보를 제공 합니다.  
  
 [활성화](../mfc/activation-cpp.md)  
 OLE 항목을 편집할 경우 활성화의 역할에 설명 합니다.  
  
 [컨테이너](../mfc/containers.md)  
 OLE의 컨테이너 사용에 대 한 링크를 제공 합니다.  
  
 [데이터 개체 및 데이터 소스](../mfc/data-objects-and-data-sources-ole.md)  
 사용을 설명 하는 항목에 대 한 링크를 제공 된 `COleDataObject` 및 `COleDataSource` 클래스입니다.  
  
 [끌어서 놓기](../mfc/drag-and-drop-ole.md)  
 복사 및 붙여넣기 ole를 사용 하 여 설명 합니다.  
  
 [OLE 메뉴 및 리소스](../mfc/menus-and-resources-ole.md)  
 메뉴 및 MFC OLE 문서 응용 프로그램의 리소스 사용에 설명 합니다.  
  
 [등록](../mfc/registration.md)  
 서버 설치 및 초기화에 설명합니다.  
  
 [서버](../mfc/servers.md)  
 컨테이너 응용 프로그램에서 사용 하기 위해 OLE 항목 (또는 구성 요소)를 만드는 방법에 설명 합니다.  
  
 [추적기](../mfc/trackers.md)  
 에 대 한 정보를 제공는 `CRectTracker` OLE 클라이언트 항목와 상호 작용할 수 있도록 그래픽 인터페이스를 제공 하는 클래스입니다.  
  
## <a name="related-sections"></a>관련 단원  
 [연결 지점](../mfc/connection-points.md)  
 연결 지점 (이전의 OLE 연결점)를 구현 하는 방법에 설명 하는 MFC 클래스를 사용 하 여 `CCmdTarget` 및 `CConnectionPoint`합니다.  
  
 [컨테이너/서버 COM 구성 요소](../mfc/containers-advanced-features.md)  
 기존 컨테이너 응용 프로그램에 선택적 고급 기능을 통합 하는 데 필요한 단계를 설명 합니다.  
  
 [구성 요소 개체 모델](http://msdn.microsoft.com/library/windows/desktop/ms694363)  
 MFC 없이 OLE를 사용 하 여 설명 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [개념](../mfc/mfc-concepts.md)

