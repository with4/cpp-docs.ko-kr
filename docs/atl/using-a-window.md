---
title: 창 (ATL)를 사용 하 여 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ATL, windows
- CWindow class, about CWindow class
- windows [C++], ATL
ms.assetid: b3b9cc8e-4287-486b-b080-38852bc2943a
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a2be573e10190b385274de9afab498c77a094550
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="using-a-window"></a>창을 사용 하 고
클래스 [CWindow](../atl/reference/cwindow-class.md) 창을 사용할 수 있습니다. 다이어그램에 연결한 후는 `CWindow` 개체를 호출할 수 있습니다 `CWindow` 창을 조작 하는 메서드. `CWindow`도 포함 되어는 `HWND` 변환 하는 연산자는 `CWindow` 개체는 `HWND`합니다. 따라서 전달할 수 있습니다는 `CWindow` 개체 창에 대 한 핸들을 필요로 하는 기능입니다. 혼합할 수 `CWindow` 메서드 호출 및 임시 개체를 만들지 않고 Win32 함수 호출을 합니다.  
  
 때문에 `CWindow` 에 두 개의 데이터 멤버가 (창 핸들 및 기본 차원) 코드에 대해 오버 헤드를 부여 하지 않습니다. 또한 다양 한는 `CWindow` 메서드 단순히 해당 Win32 API 함수를 래핑합니다. 사용 하 여 `CWindow`, `HWND` 멤버 Win32 함수를 자동으로 전달 됩니다.  
  
 사용 하는 것 외에도 `CWindow` 를 직접 있습니다 또한에서 파생 될 수 하 클래스를 데이터 나 코드를 추가 합니다. ATL 자체에서 세 개의 클래스를 파생 `CWindow`: [CWindowImpl](../atl/implementing-a-window.md), [CDialogImpl](../atl/implementing-a-dialog-box.md), 및 [CContainedWindowT](../atl/using-contained-windows.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [창 클래스](../atl/atl-window-classes.md)

