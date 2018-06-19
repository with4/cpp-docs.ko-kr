---
title: C + + 창 개체와 HWND 간 관계 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- HWND
dev_langs:
- C++
helpviewer_keywords:
- Windows window [MFC]
- window objects [MFC], HWND and
- HWND [MFC]
- CWnd class [MFC], HWND
- HWND, window objects [MFC]
ms.assetid: f2e76340-6691-4ee6-9424-0345634a9469
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b51daa375c3c920443316b6e10b6415ee018fdb4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385780"
---
# <a name="relationship-between-a-c-window-object-and-an-hwnd"></a>C++ 창 개체와 HWND 간 관계
창 *개체* 는 c + + 개체 `CWnd` 클래스 (또는 파생된 클래스) 프로그램에서 직접 만든 합니다. 제공 하 고 프로그램의 생성자와 소멸자 호출에 대 한 응답으로 이동 됩니다. Windows *창*, 반면에 창에 해당 하 고 있는 경우 시스템 리소스를 사용 하는 내부 Windows 데이터 구조에는 불투명 핸들입니다. Windows 창 "창 핸들"으로 식별 됩니다 (`HWND`) 후 생성 되 고는 `CWnd` 를 호출 하 여 개체가 만들어집니다는 **만들기** 클래스의 멤버 함수 `CWnd`합니다. 프로그램 호출 또는 사용자의 작업 창 소멸 됩니다. 창 핸들 window 개체에 저장 된 `m_hWnd` 멤버 변수입니다. 다음 그림 c + + 창 개체 및 Windows 창 사이의 관계를 보여 줍니다. 설명 창을 만드는 [만드는 Windows](../mfc/creating-windows.md)합니다. 설명 창 소멸 시키기 [창 개체 소멸 시키기](../mfc/destroying-window-objects.md)합니다.  
  
 ![CWnd 창 개체 및 결과 창](../mfc/media/vc37fj1.gif "vc37fj1")  
창 개체 및 Windows 창  
  
## <a name="see-also"></a>참고 항목  
 [창 개체](../mfc/window-objects.md)

