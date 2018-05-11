---
title: 문서 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.document
dev_langs:
- C++
helpviewer_keywords:
- document classes [MFC]
ms.assetid: 4bf19b02-0a4f-4319-b68e-cddcba2705cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2073e432dd0d0792e358a3f159892aea405197c9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="document-classes"></a>문서 클래스
문서 클래스 개체, 문서 템플릿 개체에서 만든 응용 프로그램의 데이터를 관리 합니다. 이러한 클래스 중 하나에서 문서에 대 한 클래스를 파생 합니다.  
  
 문서 클래스 개체의 뷰 개체와 상호 작용 합니다. 창의 클라이언트 영역 나타내고 문서의 데이터를 표시할 사용자가 상호 작용할 수 있도록 하는 개체 보기. 문서 및 뷰 문서 템플릿 개체에 의해 생성 됩니다.  
  
 [CDocument](../mfc/reference/cdocument-class.md)  
 응용 프로그램 관련 문서에 대 한 기본 클래스입니다. 문서 클래스 또는 클래스에서 파생 **CDocument**합니다.  
  
 [COleDocument](../mfc/reference/coledocument-class.md)  
 기본 컨테이너 지원 뿐 아니라 복합 문서 구현에 사용 합니다. 파생 된 클래스에 대 한 컨테이너 역할 [CDocItem](../mfc/reference/cdocitem-class.md)합니다. 이 클래스 컨테이너에 설명 하며 기본 클래스에 대 한 기본 클래스로 사용할 수 있습니다 `COleServerDoc`합니다.  
  
 [COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)  
 클래스에서 파생 `COleDocument` 하는 링크를 위한 인프라를 제공 합니다. 대신이 클래스에서 컨테이너 응용 프로그램에 대 한 문서 클래스를 파생 시켜야 `COleDocument` 포함 된 개체에 대 한 링크를 지원 하려는 경우.  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 Rich edit 컨트롤에 있는 OLE 클라이언트 항목의 목록을 유지 관리 합니다. 함께 사용할 [CRichEditView](../mfc/reference/cricheditview-class.md) 및 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)합니다.  
  
 [COleServerDoc](../mfc/reference/coleserverdoc-class.md)  
 서버 응용 프로그램 문서 클래스에 대 한 기본 클래스로 사용 합니다. `COleServerDoc` 개체와의 상호 작용을 통해 서버 지원 대량의 제공 [COleServerItem](../mfc/reference/coleserveritem-class.md) 개체입니다. 비주얼 편집 기능은 클래스 라이브러리의 문서/뷰 아키텍처를 사용 하 여 제공 됩니다.  
  
 [CHtmlEditDoc](../mfc/reference/chtmleditdoc-class.md)  
 제공 된 [CHtmlEditView](../mfc/reference/chtmleditview-class.md), MFC 문서 뷰 아키텍처 컨텍스트 내에서 WebBrowser HTML 편집 플랫폼의 기능입니다.  
  
## <a name="related-classes"></a>관련된 클래스  
 문서 클래스 개체를 영구 수-즉, 해당 상태를 저장 매체에 쓸 수와 다시 읽고 합니다. MFC에서 제공 된 `CArchive` 용이 문서의 데이터를 저장 매체를 전송 하는 클래스입니다.  
  
 [CArchive](../mfc/reference/carchive-class.md)  
 와 협력 하 여 한 [CFile](../mfc/reference/cfile-class.md) serialization 통해 개체에 대 한 영구 저장소를 구현 하는 개체 (참조 [cobject:: Serialize](../mfc/reference/cobject-class.md#serialize)).  
  
 문서는 OLE 개체를 포함할 수도 있습니다. `CDocItem` 서버 및 클라이언트 항목의 기본 클래스가입니다.  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 추상 기본 클래스의 [COleClientItem](../mfc/reference/coleclientitem-class.md) 및 [COleServerItem](../mfc/reference/coleserveritem-class.md)합니다. 클래스의 개체에서 파생 된 `CDocItem` 문서의 일부를 나타냅니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)

