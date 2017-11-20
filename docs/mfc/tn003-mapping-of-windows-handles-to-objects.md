---
title: "TN003: windows 핸들을 개체로 매핑 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mapping
dev_langs: C++
helpviewer_keywords:
- TN003
- handle maps
- Windows handles to objects [MFC]
- mappings [MFC], Windows handles to objects
ms.assetid: fbea9f38-992c-4091-8dbc-f29e288617d6
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7427ca7cbe6de30581153eb6d3269a83b9b456ed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="tn003-mapping-of-windows-handles-to-objects"></a>TN003: Windows 핸들을 개체로 매핑
이 노트에서는 MFC 설명 루틴을 지 원하는 Windows 매핑 개체 c + + 개체에 대 한 핸들입니다.  
  
## <a name="the-problem"></a>문제  
 Windows 개체는 일반적으로 여러 표시 [처리](http://msdn.microsoft.com/library/windows/desktop/aa383751) 개체는 MFC 클래스 c + + 개체와 함께 Windows 개체 핸들을 래핑합니다. MFC 클래스 라이브러리의 함수를 배치 하는 핸들을 통해 특정 핸들이 있는 Windows 개체에 배치 되는 c + + 개체를 찾을 수 있습니다. 그러나 경우에 따라 개체에 c + + 래퍼 개체를 없고 시스템이 해당이 시간에 c + + 래퍼 역할을 하는 임시 개체를 만듭니다.  
  
 핸들 맵을 사용 하는 Windows 개체는 다음과 같습니다.  
  
-   HWND ([CWnd](../mfc/reference/cwnd-class.md) 및 `CWnd`-파생 된 클래스)  
  
-   HDC ([CDC](../mfc/reference/cdc-class.md) 및 `CDC`-파생 된 클래스)  
  
-   HMENU ([CMenu](../mfc/reference/cmenu-class.md))  
  
-   HPEN ([CGdiObject](../mfc/reference/cgdiobject-class.md))  
  
-   HBRUSH (`CGdiObject`)  
  
-   HFONT (`CGdiObject`)  
  
-   HBITMAP (`CGdiObject`)  
  
-   HPALETTE (`CGdiObject`)  
  
-   HRGN (`CGdiObject`)  
  
-   HIMAGELIST ([CImageList](../mfc/reference/cimagelist-class.md))  
  
-   소켓 ([CSocket](../mfc/reference/csocket-class.md))  
  
 이러한 개체 중 하나에에 핸들을 지정한 정적 메서드를 호출 하 여 핸들을 래핑하는 MFC 개체를 찾을 수 `FromHandle`합니다. 예를 들어 호출 HWND `hWnd`, 다음 줄에 대 한 포인터를 반환 합니다는 `CWnd` 를 래핑하는 `hWnd`:  
  
```  
CWnd::FromHandle(hWnd)  
```  
  
 경우 `hWnd` 임시 특정 래퍼 개체를 없는 `CWnd` 래핑할 만들어집니다 `hWnd`합니다. 따라서 올바른 c + + 개체 핸들에서 가져올 수 있습니다.  
  
 래퍼 개체를 사용 하는 다음에 래퍼 클래스의 public 멤버 변수에서 해당 핸들을 검색할 수 있습니다. 경우에 `CWnd`, `m_hWnd` 해당 개체에 대 한 HWND를 포함 합니다.  
  
## <a name="attaching-handles-to-mfc-objects"></a>MFC 개체에 연결 하는 핸들  
 Windows 개체에 대 한 핸들 및 새로 만든된 핸들 래퍼 개체를 들어 두 호출 하 여 연결할 수 있습니다는 `Attach` 다음이 예제와 같이 작동 합니다.  
  
```  
CWnd myWnd;  
myWnd.Attach(hWnd);
```  
  
 이렇게 하면 항목에 영구 맵에 연결 `myWnd` 및 `hWnd`합니다. 호출 `CWnd::FromHandle(hWnd)` 은 이제 반환에 대 한 포인터 `myWnd`합니다. 때 `myWnd` 은 삭제 된 소멸자가 자동으로 삭제 합니다 `hWnd` Windows를 호출 하 여 [DestroyWindow](http://msdn.microsoft.com/library/windows/desktop/ms632682) 함수입니다. 이 원치 않을 경우 `hWnd` 에서 분리 해야 `myWnd` 하기 전에 `myWnd` 소멸 됩니다 (되는 범위를 벗어나면 될 때 정상적으로 `myWnd` 정의 된). `Detach` 메서드는이 수행 합니다.  
  
```  
myWnd.Detach();
```  
  
## <a name="more-about-temporary-objects"></a>임시 개체에 대 한 자세한 정보  
 임시 개체가 생성 될 때마다 `FromHandle` 래퍼 개체를 아직 포함 되지 않은 하는 핸들을 지정 합니다. 이러한 임시 개체는 해당 핸들에서 분리 하 고 삭제는 `DeleteTempMap` 함수입니다. 기본적으로 [CWinThread::OnIdle](../mfc/reference/cwinthread-class.md#onidle) 자동으로 호출 `DeleteTempMap` 지 원하는 임시 핸들 맵 각 클래스에 대 한 합니다. 이 임시 개체에 대 한 포인터를 사용할 수의 함수에서 종료 된 시점 이후의 포인터 얻는 데 사용 된 가정할 수 없음을 의미 합니다.  
  
## <a name="wrapper-objects-and-multiple-threads"></a>래퍼 개체와 여러 스레드  
 임시 및 영구 개체는 스레드 단위 별로 유지 관리 됩니다. 즉, 한 스레드가 다른 스레드에서 c + + 래퍼 개체 일시적 또는 영구적 인지에 관계 없이 액세스할 수 없습니다.  
  
 다른 스레드 간에 이러한 개체를 전달할, 항상으로 보낼 기본 `HANDLE` 유형입니다. 한 스레드에서 c + + 래퍼 개체를 전달 예기치 않은 결과가 발생할 경우가 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

