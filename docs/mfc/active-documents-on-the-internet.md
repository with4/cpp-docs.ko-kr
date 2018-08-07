---
title: 인터넷의 액티브 문서 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- active documents [MFC], creating
- application wizards [MFC], active documents
- active documents [MFC], programming steps
- application wizards [MFC]
- active documents [MFC], using application wizards
ms.assetid: a46bd8a0-e27a-4116-b1bf-dacdb7ae78d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a18b84b30445060631589e72f6c158ea9b3626f0
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930890"
---
# <a name="active-documents-on-the-internet"></a>인터넷의 액티브 문서
액티브 문서는 일반적인 포함된 개체에 대 한 확장을 제공합니다. 액티브 문서는 다중 페이지 수 있으며 전체 클라이언트 영역에 표시 됩니다. 기존 메뉴 협상을 수행 하며 현재 위치와 서버 응용 프로그램에서 열려 있는 창에 편집할 수 있습니다. 해치 테두리가 작은 사각형으로 표시를 하는 대신 액티브 문서는 전체 프레임 및 항상 내부 활성입니다.  
  
 액티브 문서는 Excel, Word 등 여러 문서 유형을 이루어진 복합 문서를 만들어야 하는 방법을 제공 하는 Microsoft Office Binder와 같은 컨테이너에서 볼 수 있습니다 및 수 있으며 각 사용자 지정 문서 형식, 전체 프레임을 편집 합니다. 액티브 문서 컨테이너 Microsoft Internet Explorer와 같은 브라우저에서 액티브 문서를 표시할 수도 있습니다.  
  
 **액티브 문서 장점은 다음과 같습니다.**  
  
-   문서를 볼 수는 전체 클라이언트 창에서 전체 프레임입니다.  
  
-   별도 응용 프로그램 창에서 문서를 열 수 있습니다.  
  
     문서를 열에 대 한 도우미 응용 프로그램의 클라이언트에 존재 해야 합니다 또는 응용 프로그램을 실행 하려면 먼저 별도로 다운로드 합니다. (Word, PowerPoint 및 Excel 문서에 대 한 뷰어를 제공) 제한 된 기능을 제공 하는 뷰어를 기록할 수 있습니다. 응용 프로그램의 전체 버전에는 완벽 하 게 편집 지원을 제공할 수 있습니다.  
  
-   문서는 항상 내부 활성화 합니다.  
  
-   컨테이너에서 호출 되는 메뉴 명령 문서에 라우팅할 수 있습니다.  
  
-   웹 브라우저에서 문서를 볼 수 있습니다. 이 문서와 다른 웹 페이지 간의 원활한 통합을 제공합니다.  
  
     사용자는 HTML 웹 페이지, Excel 스프레드시트를 찾아보고 MFC를 사용 하 여 작성 된 문서에 활성 문서에 대 한 지원 수 있습니다. 메뉴 및 HTML 페이지, Excel 및 응용 프로그램의 문서 뷰 간에 원활 하 게 브라우저 스위치로 친숙 한 웹 인터페이스를 사용 하 여 탐색할 수 있습니다.  
  
-   모든 응용 프로그램은 공통 프레임에 표시 됩니다.  
  
## <a name="requirements-for-active-documents"></a>액티브 문서에 대한 요구 사항  
 아래 표에 나열 된 인터페이스에는 이미 포함 된 서버에 필요한 인터페이스와 여러 가지 새로운 인터페이스가 액티브 문서에만 포함 됩니다. MFC에서 이러한 인터페이스의 대부분에 대 한 기본 구현을 제공는 [COleServerDoc](../mfc/reference/coleserverdoc-class.md) 클래스입니다.  
  
|문서 중...|이러한 인터페이스를 구현합니다.|  
|-------------------------|---------------------------------|  
|복합 파일을 저장 메커니즘으로 사용 합니다.|`IPersistStorage`.|  
|파일에서 만들기를 포함 하는 활성 문서의 기본 포함 기능을 지원 합니다.|`IPersistFile`, `IOleObject` 및 `IDataObject`|  
|에서는 내부 활성화.|`IOleInPlaceObject` 및 `IOleInPlaceActiveObject` (컨테이너의를 사용 하 여 `IOleInPlaceSite` 및 `IOleInPlaceFrame` 인터페이스).|  
|이러한 새 인터페이스를 포함 하는 액티브 문서 확장을 지원 합니다. 일부 인터페이스는 선택적입니다.|`IOleDocument`, `IOleDocumentView`, `IOleCommandTarget` 및 `IPrint`가 있습니다.|  
  
 MFC에서는 활성 문서에 포함 된 서버 지원 기존 확장에 대 한 지원을 제공 합니다.  
  
## <a name="add-active-document-support-to-a-new-application"></a>새 응용 프로그램 액티브 문서 지원 추가  
 액티브 문서 지원을 사용 하 여 새 응용 프로그램을 만들려면: MFC 응용 프로그램 마법사에는 **복합 문서 지원** 페이지에서 "Select 복합 문서 지원"에 선택 **풀 서버** 또는  **컨테이너/풀 서버**, "추가 옵션 선택"에서 대 한 확인란을 선택 하 고 **액티브 문서 서버**합니다.  
  
##  <a name="_core_convert_an_existing_mfc_in.2d.process_server_to_an_activex_document_server"></a> 액티브 문서 서버를 기존 MFC In-process 서버 변환  
 응용 프로그램 버전 4.2 이전 버전의 Visual c + +로 만든 있고 이미 in-process 서버 이면 다음 클래스를 변경 하 여 액티브 문서 지원을 추가할 수 있습니다.  
  
|클래스 형식|이전에서 파생|파생 되도록 변경|  
|----------------|---------------------------|---------------------------|  
|내부 프레임|`COleIPFrameWnd`|`COleDocIPFrameWnd`|  
|항목|`COleServerItem`|`CDocObjectServerItem`|  
  
 도 레지스트리에서 정보를 입력 하는 방법을 변경 하 고 여러 다른 변경 됩니다. 현재 응용 프로그램에 COM 구성 요소 지원 없는 경우 응용 프로그램 마법사를 실행 하는 COM 구성 요소 관련 코드 기존 응용 프로그램과 통합 하 여 서버 지원을 추가할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 인터넷 프로그래밍 작업](../mfc/mfc-internet-programming-tasks.md)   
 [MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)

