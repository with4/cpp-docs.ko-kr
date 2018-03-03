---
title: "활성화: 동사 | Microsoft Docs"
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
- verbs [MFC]
- OLE [MFC], activation
- edit verb [MFC]
- activation [MFC], verbs
- OLE [MFC], editing
- Primary verb [MFC]
- OLE activation {MFC]
ms.assetid: eb56ff23-1de8-43ad-abeb-dc7346ba7b70
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c2a443f4ce65dcc7e9460bd016638aa5069e7e6d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="activation-verbs"></a>활성화: 동사
이 문서에서는 OLE의 역할 기본 및 보조 동사 플레이 설명 [활성화](../mfc/activation-cpp.md)합니다.  
  
 일반적으로 포함된 된 항목을 두 번 클릭 하는 사용자를 편집할 수 있습니다. 그러나 특정 항목은이 방식으로 동작 하지 않습니다. 예를 들어 녹음기 응용 프로그램을 사용 하 여 만든 항목을 두 번 클릭 하면 열리지 않으면 서버 별도 창. 대신, 소리를 재생 합니다.  
  
 이 동작 차이 대 한 이유는 녹음기 항목 한지 다른 "기본 동사입니다." 기본 동사에는 OLE 항목을 두 번 클릭할 때 수행할 동작입니다. 대부분의 OLE 항목 형식에 대 한 기본 동사는 편집, 항목을 만든 서버를 시작 합니다. 일부 유형의 녹음기 항목과 같은 항목에 대 한 기본 동사는 재생 합니다.  
  
 하나의 동사를 지 원하는 많은 유형의 OLE 항목으 며 편집이 가장 일반적인 합니다. 그러나 항목의 일부 형식은 여러 동사를 지원 합니다. 예를 들어 항목 지원 녹음기 보조 동사로 편집 합니다.  
  
 자주 사용 되는 또 다른 동사는 열기입니다. Open 동사는 편집, 서버 응용 프로그램이 별도 창에서 시작 하는 제외 합니다. 컨테이너 응용 프로그램 또는 서버 응용 프로그램이 내부 활성화를 지원 하지 않을 때이 동사를 사용 해야 합니다.  
  
 기본 동사 이외의 모든 동사는 항목을 선택할 때 하위 메뉴 명령을 통해 호출 되어야 합니다. 이 하위 메뉴 항목에서 지 원하는 모든 동사를 포함 하며 대개으로 *typename* **개체** 명령을 **편집** 메뉴. 에 대 한 내용은 *typename* **개체** 명령 문서를 참조 하십시오. [메뉴 및 리소스: 컨테이너 추가](../mfc/menus-and-resources-container-additions.md)합니다.  
  
 서버 응용 프로그램에서 지원 되는 동사는 Windows 등록 데이터베이스에 나열 됩니다. 서버 응용 프로그램이 Microsoft Foundation Class 라이브러리를 작성 하는 경우 서버를 시작할 때 모든 동사 자동으로 등록 됩니다. 그렇지 않으면 서버 응용 프로그램의 초기화 단계 중에 등록 해야 합니다. 자세한 내용은 문서 참조 [등록](../mfc/registration.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [정품 인증](../mfc/activation-cpp.md)   
 [컨테이너](../mfc/containers.md)   
 [서버](../mfc/servers.md)

