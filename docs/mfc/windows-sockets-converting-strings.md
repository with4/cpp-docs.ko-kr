---
title: "Windows 소켓: 문자열 변환 | Microsoft Docs"
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
- Windows Sockets [MFC], multibyte character string conversion
- sockets [MFC], multibyte character string conversion issues
- string conversion, multibyte character strings
ms.assetid: 9df522b5-6b23-41e0-bb96-e4e623baf141
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f87d200ca6c5b0b1edb003636e5f8c33570da50d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="windows-sockets-converting-strings"></a>Windows 소켓: 문자열 변환
이 문서 및 두 개의 참조 문서에서는 Windows 소켓 프로그래밍의 몇 가지 문제를 설명합니다. 이 문서에서는 문자열 변환에 대해 설명 합니다. 다른 문제에 대해서는 설명 [Windows 소켓: 차단](../mfc/windows-sockets-blocking.md) 및 [Windows 소켓: 바이트 순서 지정](../mfc/windows-sockets-byte-ordering.md)합니다.  
  
 사용 하거나 클래스에서 파생 되는 경우 [CAsyncSocket](../mfc/reference/casyncsocket-class.md), 이러한 문제를 직접 관리 해야 합니다. 사용 하거나 클래스에서 파생 되는 경우 [CSocket](../mfc/reference/csocket-class.md), MFC에서를 관리 합니다.  
  
## <a name="converting-strings"></a>문자열 변환  
 유니코드 또는 멀티 바이트 문자 집합 (MBCS), 같은 서로 다른 와이드 문자 형식으로 저장 된 문자열을 사용 하는 응용 프로그램 간의 통신 또는 둘 중와 ANSI 문자열을 사용 하 여 응용 프로그램 간의 변환을 관리 해야 하는 경우 사용자가 직접 `CAsyncSocket`합니다. `CArchive` 사용 되는 개체는 `CSocket` 개체는 이러한 변환 기능을 통해 클래스의 관리 [CString](../atl-mfc-shared/reference/cstringt-class.md)합니다. 자세한 내용은 Windows SDK에 있는 Windows 소켓 사양을 참조 하십시오.  
  
 자세한 내용은 다음을 참조하세요.  
  
-   [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows 소켓: 소켓과 아카이브 함께 사용](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows 소켓: 백그라운드](../mfc/windows-sockets-background.md)  
  
-   [Windows 소켓: 스트림 소켓](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows 소켓: 데이터그램 소켓](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>참고 항목  
 [MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)

