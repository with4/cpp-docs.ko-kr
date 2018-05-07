---
title: 창 클래스 등록 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- WndProc
dev_langs:
- C++
helpviewer_keywords:
- window classes [MFC], registering
- registry [MFC], registering classes
- AfxRegisterWndClass method [MFC]
- MFC, windows
- WinMain method [MFC], and registering window classes
- WndProc method [MFC]
- classes [MFC], registering window classes
- WinMain method [MFC]
- registering window classes [MFC]
ms.assetid: 30994bc4-a362-43da-bcc5-1bf67a3fc929
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 00e397f8880f6f42f1930e668b64d3ba62eb2c64
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="registering-window-classes"></a>창 클래스 등록
창 "클래스" Windows 일반 프로그래밍에서 임의 개수의 windows 만들 수 있는 "클래스" (c + + 클래스)의 특성을 정의 합니다. 이러한 종류의 클래스는 템플릿 또는 창 만들기에 대 한 모델.  
  
## <a name="window-class-registration-in-traditional-programs-for-windows"></a>일반적인 Windows 프로그램에 창 클래스 등록  
 MFC, 없이 Windows에 대 한 기존 프로그램에서는 창 자체 "창 프로시저"에 대 한 모든 메시지를 처리할 수 또는 "**WndProc**." A **WndProc** "창 클래스 등록" 프로세스를 사용 하 여 창에 연결 됩니다. 주 창에 등록 되어는 `WinMain` 함수가 있지만 다른 클래스에에서 등록할 수 아무 곳 이나 응용 프로그램입니다. 등록에 대 한 포인터를 포함 하는 구조에 따라 달라 집니다는 **WndProc** 배경 브러시 커서에 대 한 사양을 함께 작동 하 고 등입니다. 구조 한 이전 호출에서 클래스의 문자열 이름 매개 변수로 전달 되는 **RegisterClass** 함수입니다. 따라서 여러 창에서 등록 클래스를 공유할 수 있습니다.  
  
## <a name="window-class-registration-in-mfc-programs"></a>MFC 프로그램의 창 클래스 등록  
 반면, 대부분 창 클래스 등록 활동 MFC 프레임 워크 프로그램에서 자동으로 수행 됩니다. MFC를 사용 하는 경우 일반적으로 클래스 상속에 대 한 일반 c + + 구문을 사용 하 여 기존 라이브러리 클래스에서 c + + 창 클래스를 파생 합니다. 프레임 워크는 여전히 기존의 사용 하며 "등록 classes" 필요할 때에 대해 등록 된 여러 가지 표준 텍스처를 제공 합니다. 호출 하 여 추가 등록 클래스를 등록할 수 있습니다는 [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) 전역 함수와에 등록 된 클래스에 전달 된 **만들기** 의 멤버 함수 `CWnd`합니다. 여기에서 설명한 대로, 기존의 c + + 클래스와 다름은 "Windows에서" 클래스 등록 합니다.  
  
 자세한 내용은 참조 [기술 참고 1](../mfc/tn001-window-class-registration.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [창 만들기](../mfc/creating-windows.md)

