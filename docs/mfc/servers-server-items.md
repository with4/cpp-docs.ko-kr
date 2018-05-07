---
title: '서버: 서버 항목 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- server items, implementing
- servers [MFC], server items
- architecture [MFC], server-item
- server items
- OLE server applications [MFC], server items
ms.assetid: 28ba81a1-726a-4728-a52d-68bc7efd5a3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e83b75183fe226b4ff384a00b0b5260caba01efa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="servers-server-items"></a>서버: 서버 항목
사용자가 포함 또는 연결된 OLE 항목을 편집할 수 있도록 컨테이너가 서버를 시작하면 서버 응용 프로그램은 "서버 항목"을 만듭니다. `COleServerItem`에서 파생된 클래스의 개체인 서버 항목은 서버 문서와 컨테이너 응용 프로그램 사이의 인터페이스를 제공합니다.  
  
 `COleServerItem` 클래스는 일반적으로 컨테이너의 요청에 따라서 OLE에 의해 호출된 여러 재정의 가능한 멤버 함수를 정의합니다. 서버 항목은 서버 문서의 일부 또는 전체 문서를 나타낼 수 있습니다. OLE 항목이 컨테이너 문서에 포함되면 서버 항목은 전체 서버 문서를 나타냅니다. OLE 항목이 연결되면 서버 항목은 연결이 일부에 대한 것인지 또는 전체에 대한 것인지에 따라 서버 문서의 일부나 전체 문서를 나타낼 수 있습니다.  
  
 에 [HIERSVR](../visual-cpp-samples.md) 서버 항목 클래스인 예를 들어 샘플 **CServerItem**, 멤버는 클래스의 개체에 대 한 포인터를 보유 **CServerNode**합니다. **CServerNode** 개체는 트리 인 HIERSVR 응용 프로그램의 문서에서 노드는 합니다. 경우는 **CServerNode** 개체는 루트 노드는 **CServerItem** 개체는 전체 문서를 나타냅니다. 경우는 **CServerNode** 개체가 자식 노드인 경우는 **CServerItem** 개체는 문서의 일부를 나타냅니다. MFC OLE 샘플 [HIERSVR](../visual-cpp-samples.md) 이 상호 작용에 대 한 예제입니다.  
  
##  <a name="_core_implementing_server_items"></a> 서버 항목 구현  
 응용 프로그램 마법사를 사용하여 응용 프로그램에 대한 "시작" 코드를 생성하는 경우 시작 코드에 서버 항목을 포함하려면 OLE 옵션 페이지에서 서버 옵션 중 하나를 선택하기만 하면 됩니다. 기존 응용 프로그램에 서버 항목을 추가하는 경우 다음 단계를 수행합니다.  
  
#### <a name="to-implement-a-server-item"></a>서버 항목을 구현하려면  
  
1.  `COleServerItem`에서 클래스를 파생합니다.  
  
2.  파생 클래스에서 `OnDraw` 멤버 함수를 재정의합니다.  
  
     프레임워크는 `OnDraw`를 호출하여 OLE 항목을 메타파일로 렌더링합니다. 컨테이너 응용 프로그램은 이 메타파일을 사용하여 항목을 렌더링합니다. 응용 프로그램의 뷰 클래스에는 `OnDraw` 멤버 함수도 있습니다. 이 함수는 서버 응용 프로그램이 활성화인 경우 항목을 렌더링하는 데 사용됩니다.  
  
3.  서버 문서 클래스에 대한 `OnGetEmbeddedItem`의 재정의를 구현합니다. 자세한 내용은 문서 참조 [서버: 서버 문서 구현](../mfc/servers-implementing-server-documents.md) 및 MFC OLE 샘플 [HIERSVR](../visual-cpp-samples.md)합니다.  
  
4.  서버 항목 클래스의 `OnGetExtent` 멤버 함수를 구현합니다. 프레임워크는 항목의 크기를 검색하기 위해 이 함수를 호출합니다. 기본 구현은 아무 작업도 수행하지 않습니다.  
  
##  <a name="_core_a_tip_for_server.2d.item_architecture"></a> 서버 항목 아키텍처에 대 한 팁  
 설명한 것 처럼 [서버 항목 구현](#_core_implementing_server_items), 서버 응용 프로그램은 서버의 뷰와 컨테이너 응용 프로그램에서 사용 하는 메타 파일에서 항목을 렌더링 수 있어야 합니다. Microsoft Foundation Class 라이브러리 응용 프로그램 아키텍처에서 뷰 클래스의 `OnDraw` 멤버 함수를 편집 하는 경우 항목을 렌더링 (참조 [cview:: Ondraw](../mfc/reference/cview-class.md#ondraw) 에 *클래스 라이브러리 참조* ). 서버 항목의 `OnDraw` 을 메타 파일로 다른 모든 경우에는 항목 렌더링 (참조 [coleserveritem:: Ondraw](../mfc/reference/coleserveritem-class.md#ondraw)).  
  
 서버 문서 클래스에서 도우미 함수를 작성하고 뷰와 서버 항목 클래스의 `OnDraw` 함수에서 해당 함수를 호출하여 코드의 중복을 방지할 수 있습니다. MFC OLE 샘플 [HIERSVR](../visual-cpp-samples.md) 이 전략을 사용 하 여: 함수 **cserverview:: Ondraw** 및 **cserveritem:: Ondraw** 호출 모두 **CServerDoc::DrawTree**  항목을 렌더링 하 합니다.  
  
 다양한 상황에서 그리기 때문에 뷰 및 항목은 모두 `OnDraw` 멤버 함수를 보유합니다. 뷰는 확대/축소, 크기 및 범위 선택, 클리핑 및 사용자 인터페이스 요소(예: 스크롤 막대)와 같은 요소를 고려해야 합니다. 반면에 서버 항목은 항상 전체 OLE 개체를 그립니다.  
  
 자세한 내용은 참조 [cview:: Ondraw](../mfc/reference/cview-class.md#ondraw), [COleServerItem](../mfc/reference/coleserveritem-class.md), [coleserveritem:: Ondraw](../mfc/reference/coleserveritem-class.md#ondraw), 및 [COleServerDoc::OnGetEmbeddedItem](../mfc/reference/coleserverdoc-class.md#ongetembeddeditem)에 *클래스 라이브러리 참조*합니다.  
  
## <a name="see-also"></a>참고 항목  
 [서버](../mfc/servers.md)

