---
title: 창 (ATL)를 사용 하 여 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, windows
- CWindow class, about CWindow class
- windows [C++], ATL
ms.assetid: b3b9cc8e-4287-486b-b080-38852bc2943a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44b9988c0ecde4d0aee917fea686ec6511473318
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37847926"
---
# <a name="using-a-window"></a>창을 사용 하 여
클래스 [CWindow](../atl/reference/cwindow-class.md) 창을 사용할 수 있습니다. 창을 연결한 후에 `CWindow` 개체를 호출할 수 있습니다 `CWindow` 창을 조작 하는 메서드. `CWindow` 변환할 HWND 연산자도 포함을 `CWindow` 개체 HWND입니다. 따라서 전달할 수 있습니다는 `CWindow` 개체 창에 대 한 핸들을 필요로 하는 기능입니다. 쉽게 혼합할 수 있습니다 `CWindow` 메서드 호출 및 모든 임시 개체를 만들지 않고도 Win32 함수 호출을 합니다.  
  
 때문에 `CWindow` 에 두 데이터 멤버 (창 핸들 및 기본 크기) 코드에 오버 헤드가 적용 하지 않습니다. 또한 많은 `CWindow` 메서드 단순히 해당 Win32 API 함수를 래핑합니다. 사용 하 여 `CWindow`, HWND 멤버는 자동으로 Win32 함수에 전달 됩니다.  
  
 사용 하는 것 외에도 `CWindow` 직접를 파생할 수도 있습니다를 클래스에 데이터 또는 코드를 추가할 수 있습니다. 세 가지 클래스를 파생 하는 자체 ATL `CWindow`: [CWindowImpl](../atl/implementing-a-window.md)를 [CDialogImpl](../atl/implementing-a-dialog-box.md), 및 [CContainedWindowT](../atl/using-contained-windows.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [창 클래스](../atl/atl-window-classes.md)

