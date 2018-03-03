---
title: "데이터 개체 및 데이터 소스 (OLE) | Microsoft Docs"
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
- data objects [MFC], definition
- data transfer [MFC]
- OLE [MFC], data transfer
- data sources [MFC], definition
- data transfer [MFC], definition
- OLE [MFC], data objects
- OLE [MFC], data sources
ms.assetid: 8f68eed8-0ce8-4489-a4cc-f95554f89090
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 04619ee7851d2e2d6ad569583dfbb2e619d37026
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="data-objects-and-data-sources-ole"></a>데이터 개체 및 데이터 소스(OLE)
클립보드 또는 끌어 놓기를 사용 하 여 데이터 전송을 수행 하는 경우 데이터 원본 및 대상에 있습니다. 응용 프로그램 하나를 복사 하기 위한 데이터를 제공 하 고 다른 응용 프로그램 붙여 넣기 위해 수락 키를 누릅니다. 전송의 양쪽에 성공 하려면 전송에 대 한 동일한 데이터에서 다른 작업을 수행 해야 합니다. Microsoft Foundation 클래스 (MFC) 라이브러리에서는이 전송의 양쪽을 나타내는 두 개의 클래스를 제공 합니다.  
  
-   데이터 원본 (에 의해 구현 된 `COleDataSource` 개체) 데이터 전송의 원본 쪽을 나타냅니다. 데이터를 클립보드에 복사 되도록 하거나 끌어서 놓기 작업에 대 한 데이터를 제공 하는 경우 소스 응용 프로그램에 의해 생성 됩니다.  
  
-   데이터 개체 (에 의해 구현 된 `COleDataObject` 개체) 데이터 전송의 대상 쪽을 나타냅니다. 대상 응용 프로그램에 데이터가 클립보드에서 붙여넣기 작업을 수행 하려면 요청 될 때 또는 메서드를 삭제할 때 생성 됩니다.  
  
 다음 문서에서 데이터 개체 및 응용 프로그램에서 데이터 소스를 사용 하는 방법을 설명 합니다. 모두 복사 하 고 데이터를 붙여넣을 때 호출 될 수 있으므로이 정보는 컨테이너와 서버 응용 프로그램에 적용 됩니다.  
  
-   [데이터 개체 및 데이터 소스: 생성 및 소멸](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [데이터 개체 및 데이터 소스: 조작](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## <a name="in-this-section"></a>섹션 내용  
 [끌어서 놓기](../mfc/drag-and-drop-ole.md)  
  
 [클립보드](../mfc/clipboard.md)  
  
## <a name="see-also"></a>참고 항목  
 [OLE](../mfc/ole-in-mfc.md)   
 [COleDataObject 클래스](../mfc/reference/coledataobject-class.md)   
 [COleDataSource 클래스](../mfc/reference/coledatasource-class.md)
