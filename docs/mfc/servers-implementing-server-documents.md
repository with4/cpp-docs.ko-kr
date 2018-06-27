---
title: '서버: 서버 문서 구현 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE server applications [MFC], managing server documents
- OLE server applications [MFC], implementing OLE servers
- servers, server documents
- server documents [MFC], implementing
ms.assetid: cca1451a-ad09-47ed-b56e-bccd78fc86d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 273fd1e5afefb8a10b3e1ae8e3c2f81ccec05e7f
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950830"
---
# <a name="servers-implementing-server-documents"></a>서버: 서버 문서 구현
이 문서에서는 응용 프로그램 마법사에서 OLE 서버 옵션을 지정 하지 않은 서버 문서를 성공적으로 구현 하는 위해 수행 해야 하는 단계를 설명 합니다.  
  
#### <a name="to-define-a-server-document-class"></a>서버 문서 클래스를 정의 하려면  
  
1.  문서 클래스를 파생 `COleServerDoc` 대신 `CDocument`합니다.  
  
2.  파생 된 서버 항목 클래스 만들기 `COleServerItem`합니다.  
  
3.  구현 된 `OnGetEmbeddedItem` 서버 문서 클래스의 멤버 함수입니다.  
  
     `OnGetEmbeddedItem` 컨테이너 응용 프로그램의 사용자가 만들거나 포함된 된 항목을 편집할 때 호출 됩니다. 전체 문서를 나타내는 항목을 반환 합니다. 이 경고가의 개체 수에 `COleServerItem`-클래스를 파생 합니다.  
  
4.  재정의 `Serialize` 문서 내용을 serialize 할 멤버 함수입니다. 문서에 네이티브 데이터를 표시 하는 데 사용 하는 경우가 아니면 서버 항목의 목록을 serialize 할 필요가 없습니다. 자세한 내용은 참조 *서버 항목 구현* 문서의 [서버: 서버 항목](../mfc/servers-server-items.md)합니다.  
  
 서버 문서를 만들면 프레임 워크는 자동으로 문서 OLE 시스템 Dll 등록 합니다. 이렇게 하면 Dll을 서버 문서를 식별할 수 있습니다.  
  
 자세한 내용은 참조 [COleServerItem](../mfc/reference/coleserveritem-class.md) 및 [COleServerDoc](../mfc/reference/coleserverdoc-class.md) 에 *클래스 라이브러리 참조*합니다.  
  
## <a name="see-also"></a>참고 항목  
 [서버](../mfc/servers.md)   
 [서버: 서버 항목](../mfc/servers-server-items.md)   
 [서버: 서버 구현](../mfc/servers-implementing-a-server.md)   
 [서버: 내부 프레임 창 구현](../mfc/servers-implementing-in-place-frame-windows.md)

