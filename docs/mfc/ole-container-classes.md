---
title: "OLE 컨테이너 클래스 | Microsoft Docs"
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
- ActiveX classes [MFC]
- container classes [MFC]
- OLE classes [MFC]
- visual editing [MFC], classes
- OLE [MFC], classes
- containers [MFC], OLE container applications
ms.assetid: 1e27e1ab-4c22-41eb-8547-6915c72668ae
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 212e9f67f699281bebd85506e895c22cf012b4be
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="ole-container-classes"></a>OLE 컨테이너 클래스
이러한 클래스는 컨테이너 응용 프로그램에서 사용 됩니다. 둘 다 `COleLinkingDoc` 및 `COleDocument` 의 컬렉션을 관리 `COleClientItem` 개체입니다. 문서 클래스 파생 하지 않고 **CDocument**에서 파생 됩니다 `COleLinkingDoc` 또는 `COleDocument`문서에 포함 된 개체에 대 한 링크에 대 한 지원이 필요 여부에 따라 합니다.  
  
 사용 하 여 한 `COleClientItem` 다른 문서에서 포함 되어 있거나 다른 문서에 대 한 링크가 있는 문서에 각 OLE 항목을 나타내는 개체입니다.  
  
 [COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md)  
 액티브 문서 포함을 지원합니다.  
  
 [COleDocument](../mfc/reference/coledocument-class.md)  
 기본 컨테이너 지원 뿐 아니라 복합 문서 구현에 사용 합니다. 파생 된 클래스에 대 한 컨테이너 역할 `CDocItem`합니다. 이 클래스 컨테이너에 설명 하며 기본 클래스에 대 한 기본 클래스로 사용할 수 있습니다 `COleServerDoc`합니다.  
  
 [COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)  
 클래스에서 파생 `COleDocument` 하는 링크를 위한 인프라를 제공 합니다. 대신이 클래스에서 컨테이너 응용 프로그램에 대 한 문서 클래스를 파생 시켜야 `COleDocument` 포함 된 개체에 대 한 링크를 지원 하려는 경우.  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 Rich edit 컨트롤에 있는 OLE 클라이언트 항목의 목록을 유지 관리 합니다. 함께 사용할 [CRichEditView](../mfc/reference/cricheditview-class.md) 및 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)합니다.  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 추상 기본 클래스의 `COleClientItem` 및 `COleServerItem`합니다. 클래스의 개체에서 파생 된 `CDocItem` 문서의 일부를 나타냅니다.  
  
 [활성화](../mfc/reference/coleclientitem-class.md)  
 클라이언트 항목 클래스 포함 또는 연결 된 OLE 항목에 대 한 연결의 클라이언트의 측면을 나타내고입니다. 클라이언트 항목을이 클래스 로부터 파생 됩니다.  
  
 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)  
 OLE와 함께 사용할 경우 서식 있는 편집 컨트롤에 저장 된 항목에 대 한 클라이언트 쪽 액세스할 `CRichEditView` 및 `CRichEditDoc`합니다.  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 OLE 처리 중 오류로 인해 발생하는 예외입니다. 이 클래스는 컨테이너 및 서버에서 모두 사용됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)

