---
title: "클립보드 | Microsoft Docs"
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
- cutting and copying data
- copying data
- Clipboard
- Clipboard, programming
- transferring data
ms.assetid: a71b2824-1f14-4914-8816-54578d73ad4e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 304f20f94880b0bd8cb671788c5c06b69d25d377
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="clipboard"></a>클립보드
이 문서에서는 MFC 응용 프로그램에서 Windows 클립보드에 대 한 지원을 구현 하는 방법을 설명 합니다. 두 가지 방법으로 Windows 클립보드 사용 됩니다.  
  
-   잘라내기, 복사 및 붙여넣기 등의 표준 편집 메뉴 명령을 구현 합니다.  
  
-   놓기 (OLE) 및 끌어서와 전송 균일 한 데이터를 구현 합니다.  
  
 클립보드에는 원본과 대상 간에 데이터를 전송 하는 표준 Windows 방식입니다. 또한 OLE 작업에 매우 유용할 수 있습니다. OLE 도입과 함께 Windows에는 두 가지 클립보드 메커니즘 있습니다. 표준 Windows 클립보드 API를 계속 사용할 수 있지만 OLE 데이터 전송 메커니즘으로 보완 된 했습니다. OLE 단일형 데이터 전송 (UDT) 잘라내기, 복사 및 붙여넣기 클립보드 사용을 지원 하 고 끌어서 놓습니다.  
  
 클립보드는 핸들 또는 자체의 클래스를 포함 하지 않도록 Windows 세션 전체에서 공유 하는 시스템 서비스입니다. 클래스의 멤버 함수를 통해 클립보드 관리 [CWnd](../mfc/reference/cwnd-class.md)합니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [각 클립보드 메커니즘을 사용 하는 경우](../mfc/clipboard-when-to-use-each-clipboard-mechanism.md)  
  
-   [기존의 Windows 클립보드 API를 사용 하 여](../mfc/clipboard-using-the-windows-clipboard.md)  
  
-   [OLE 클립보드 메커니즘 사용](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)  
  
-   [데이터 복사 및 붙여넣기](../mfc/clipboard-copying-and-pasting-data.md)  
  
-   [기타 서식 추가](../mfc/clipboard-adding-other-formats.md)  
  
-   [Windows 클립보드](https://msdn.microsoft.com/library/ms648709)  
  
-   [끌어서 놓기 (OLE)를 구현합니다.](../mfc/drag-and-drop-ole.md)  
  
## <a name="see-also"></a>참고 항목  
 [사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)
