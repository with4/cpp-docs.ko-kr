---
title: "서버: 서버 구현 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- servers, implementing
- OLE server applications [MFC], implementing OLE servers
ms.assetid: 5bd57e8e-3b23-4f23-9597-496fac2d24b5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 148a3da3c904f5c314c75fb71deede3c92163cc6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="servers-implementing-a-server"></a>서버: 서버 구현
이 문서에서는 MFC 응용 프로그램 마법사에서 비주얼 편집 서버 응용 프로그램 코드를 설명 합니다. 응용 프로그램 마법사를 사용 하지 않는 경우이 문서에서는 서버 응용 프로그램을 구현 하는 코드를 작성 해야 하는 영역을 나열 합니다.  
  
 새 서버 응용 프로그램을 만드는 응용 프로그램 마법사를 사용 하면에 대 한 상당한 양의 서버 관련 코드가 제공 합니다. 기존 응용 프로그램에 비주얼 편집 서버 기능을 추가 하는 경우에 필요한 서버 코드의 나머지 부분을 추가 하기 전에 응용 프로그램 마법사가 제공 하는 코드를 복제 해야 합니다.  
  
 응용 프로그램 마법사가 제공 하는 서버 코드 몇 가지 범주에 해당 됩니다.  
  
-   서버 리소스를 정의 합니다.  
  
    -   서버는 별도 창에서 포함된 된 항목을 편집할 때 사용할 메뉴 리소스입니다.  
  
    -   서버 내부에서 활성화 될 때 사용 되는 메뉴 및 도구 모음 리소스입니다.  
  
     이러한 리소스에 대 한 자세한 내용은 참조 하십시오. [메뉴 및 리소스: 서버 추가](../mfc/menus-and-resources-server-additions.md)합니다.  
  
-   파생 된 항목 클래스 정의 `COleServerItem`합니다. 서버 항목에 자세한 내용은 참조 하십시오. [서버: 서버 항목](../mfc/servers-server-items.md)합니다.  
  
-   문서 클래스의 기본 클래스 변경 `COleServerDoc`합니다. 자세한 내용은 참조 하십시오. [서버: 서버 문서 구현](../mfc/servers-implementing-server-documents.md)합니다.  
  
-   프레임 창 클래스 정의에서 파생 된 `COleIPFrameWnd`합니다. 자세한 내용은 참조 하십시오. [서버: 내부 프레임 창 구현](../mfc/servers-implementing-in-place-frame-windows.md)합니다.  
  
-   Windows 등록 데이터베이스에 서버 응용 프로그램에 대 한 항목을 만들고 OLE 시스템과 서버의 새 인스턴스를 등록 합니다. 이 항목에 대 한 자세한 내용은 참조 하십시오. [등록](../mfc/registration.md)합니다.  
  
-   초기화 하 고 서버 응용 프로그램을 시작 합니다. 이 항목에 대 한 자세한 내용은 참조 하십시오. [등록](../mfc/registration.md)합니다.  
  
 자세한 내용은 참조 [COleServerItem](../mfc/reference/coleserveritem-class.md), [COleServerDoc](../mfc/reference/coleserverdoc-class.md), 및 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md) 에 *클래스 라이브러리 참조*합니다.  
  
## <a name="see-also"></a>참고 항목  
 [서버](../mfc/servers.md)   
 [컨테이너](../mfc/containers.md)   
 [메뉴 및 리소스 (OLE)](../mfc/menus-and-resources-ole.md)   
 [등록](../mfc/registration.md)

