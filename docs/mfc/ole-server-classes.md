---
title: "OLE 서버 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.ole
dev_langs: C++
helpviewer_keywords:
- OLE server applications [MFC], server classes
- OLE server documents
- COM components, classes [MFC]
- component classes [MFC]
ms.assetid: 8e9b67a2-c0ff-479c-a8d6-19b36c5e6fc6
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d23c7cb23d9221f8f2183c666a99c70ef149db3e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ole-server-classes"></a>OLE 서버 클래스
이러한 클래스는 서버 응용 프로그램에서 사용 됩니다. 서버 문서에서 파생 된 `COleServerDoc` 아닌 **CDocument**합니다. 되므로 `COleServerDoc` 에서 파생 된 `COleLinkingDoc`, 서버 문서 연결을 지원 하는 컨테이너를 수도 있습니다.  
  
 `COleServerItem` 문서나 다른 문서에 포함 하거나 연결할 수 있는 문서의 일부 클래스를 나타냅니다.  
  
 `COleIPFrameWnd`및 `COleResizeBar` 개체가 있는 동안에 컨테이너 내부 편집을 지원 하 고 `COleTemplateServer` 다른 응용 프로그램에서 OLE 개체를 편집할 수 있도록 문서/뷰 쌍의 생성을 지원 합니다.  
  
 [COleServerDoc](../mfc/reference/coleserverdoc-class.md)  
 서버 응용 프로그램 문서 클래스에 대 한 기본 클래스로 사용 합니다. `COleServerDoc`개체와의 상호 작용을 통해 서버 지원 대량의 제공 `COleServerItem` 개체입니다. 비주얼 편집 기능은 클래스 라이브러리의 문서/뷰 아키텍처를 사용 하 여 제공 됩니다.  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 추상 기본 클래스의 `COleClientItem` 및 `COleServerItem`합니다. 클래스의 개체에서 파생 된 `CDocItem` 문서의 일부를 나타냅니다.  
  
 [COleServerItem](../mfc/reference/coleserveritem-class.md)  
 OLE 인터페이스를 나타내는 데 `COleServerDoc` 항목입니다. 일반적으로 하나의 `COleServerDoc` 문서의 포함 된 부분을 나타내는 개체입니다. 링크 문서의 일부를 지 원하는 서버에 있을 수 많은 `COleServerItem` 문서의 일부에 대 한 링크를 나타내는 각각의 개체입니다.  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 서버 문서 위치에서 편집 되는 경우 보기에 대 한 프레임 창을 제공 합니다.  
  
 [COleResizeBar](../mfc/reference/coleresizebar-class.md)  
 내부 크기 조정에 대 한 표준 사용자 인터페이스를 제공합니다. 이 클래스의 개체를 함께에서 항상 사용 `COleIPFrameWnd` 개체입니다.  
  
 [COleTemplateServer](../mfc/reference/coletemplateserver-class.md)  
 프레임 워크의 문서/뷰 아키텍처를 사용 하 여 문서를 생성 하는 데 사용 합니다. A `COleTemplateServer` 개체에 연결 된 작업의 대부분에 위임 `CDocTemplate` 개체입니다.  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 OLE 처리 중 오류로 인해 발생하는 예외입니다. 이 클래스는 컨테이너 및 서버에서 모두 사용됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)

