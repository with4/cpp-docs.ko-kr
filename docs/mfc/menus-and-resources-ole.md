---
title: "메뉴 및 리소스 (OLE) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- OLE visual editing servers [MFC]
- status bars [MFC], OLE document applications
- visual editing [MFC], application menus and resources
- string tables [MFC], visual editing applications
- OLE containers [MFC], menus and resources
- OLE applications [MFC], menus and resources
- OLE server applications [MFC], menus and resources
- toolbars [MFC], OLE document applications
- string editing [MFC], visual editing applications
- server applications [MFC], OLE menus and resources
- applications [OLE], menus and resources
- menus [MFC], OLE document applications
- in-place activation [MFC], OLE menus and resources
- containers [MFC], OLE container applications
- OLE menus and resources [MFC]
ms.assetid: 52bfa086-7d3d-466f-94c7-c7061f3bdb3a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: efe0a5f6dae2cece571eddabc4094ebb87df175b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="menus-and-resources-ole"></a>메뉴 및 리소스(OLE)
다음이 문서 메뉴와 MFC OLE 문서 응용 프로그램의 리소스 사용에 설명 합니다.  
  
 OLE 비주얼 편집으로 인해 요구 사항이 추가로 적용 하면 메뉴에는 두 컨테이너에는 모드의 수 있기 때문에 OLE 문서 응용 프로그램에서 제공 하는 다른 리소스 고 server-applications (구성 요소)를 시작 하 고 사용할 수 있습니다. 예를 들어 풀 서버 응용 프로그램은 이러한 세 가지 모드 중 하나를 실행할 수 있습니다.  
  
-   독립 실행형 합니다.  
  
-   컨테이너의 컨텍스트 내에서 항목을 편집 하기 위해 준비 합니다.  
  
-   열기, 대개 별도 창에에서 해당 컨테이너의 컨텍스트 외부에서 항목을 편집 합니다.  
  
 이렇게 하려면 응용 프로그램의 가능한 각 모드 당 하나씩 세 가지 별도 메뉴 레이아웃 합니다. 또한 가속기 테이블은 새로운 각 모드에 반드시 필요 합니다. 컨테이너 응용 프로그램 지원 하거나; 내부 활성화를 지원 하지 않을 수 있습니다. 그렇지 않으면 새 메뉴 구조 하며 액셀러레이터 키 테이블에 연결 합니다.  
  
 내부 활성화 필요 컨테이너 및 서버 응용 프로그램에서 메뉴, 도구 모음 및 상태 표시줄 영역에 대 한 협상 해야 합니다. 모든 리소스에에서이 디자인 되어야 합니다. 문서 [메뉴 및 리소스: 메뉴 병합](../mfc/menus-and-resources-menu-merging.md) 자세히이 항목에 설명 합니다.  
  
 이러한 문제 때문에 응용 프로그램 마법사를 사용 하 여 만든 OLE 문서 응용 프로그램에는 최대 4 개의 별도 메뉴 및 액셀러레이터 키 테이블 리소스 있을 수 있습니다. 이러한 작업은 다음과 같은 이유로 사용 됩니다.  
  
|리소스 이름|사용|  
|-------------------|---------|  
|**IDR_MAINFRAME**|파일이 열려 있으면 MDI 응용 프로그램 또는 열려 있는 파일에 관계 없이 SDI 응용 프로그램을 사용 합니다. 비 OLE 응용 프로그램에서 사용 되는 표준 메뉴입니다.|  
|**IDR_\<프로젝트 > 형식**|파일이 열려 있으면 MDI 응용 프로그램에서 사용 합니다. 응용 프로그램을 독립 실행형 실행 중인 경우를 사용 합니다. 비 OLE 응용 프로그램에서 사용 되는 표준 메뉴입니다.|  
|**IDR_\<프로젝트 > TYPE_SRVR_IP**|위치에서 개체를 열 때 해당 서버 또는 컨테이너에 사용 합니다.|  
|**IDR_\<프로젝트 > TYPE_SRVR_EMB**|내부 활성화를 사용 하지 않고 개체가 열린 경우 서버 응용 프로그램에 사용 합니다.|  
  
 리소스 이름은 각 메뉴와 일반적으로 액셀러레이터 키 테이블을 나타냅니다. 응용 프로그램 마법사로 생성 되지 않은 MFC 응용 프로그램에서 비슷한 스키마를 사용 해야 합니다.  
  
 다음 문서는 컨테이너, 서버 및 메뉴에는 내부 활성화 구현 하는 데 필요한 병합와 관련 된 항목을 설명 합니다.  
  
-   [메뉴 및 리소스: 컨테이너 추가](../mfc/menus-and-resources-container-additions.md)  
  
-   [메뉴 및 리소스: 서버 추가](../mfc/menus-and-resources-server-additions.md)  
  
-   [메뉴 및 리소스: 메뉴 병합](../mfc/menus-and-resources-menu-merging.md)  
  
## <a name="see-also"></a>참고 항목  
 [OLE](../mfc/ole-in-mfc.md)

