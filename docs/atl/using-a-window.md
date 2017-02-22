---
title: "Using a Window | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, windows"
  - "CWindow class, about CWindow class"
  - "windows [C++], ATL"
ms.assetid: b3b9cc8e-4287-486b-b080-38852bc2943a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Using a Window
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

클래스  [CWindow](../atl/reference/cwindow-class.md) 창을 사용할 수 있습니다.  창에 연결 된 후에 `CWindow` 개체를 호출할 수 있습니다 다음 `CWindow` 창을 조작 하는 방법.  `CWindow`도 포함 된 `HWND` 변환 연산자는 `CWindow` 개체는 `HWND`.  따라서 전달할 수 있는 `CWindow` 개체에 창 핸들을 필요로 하는 모든 함수.  쉽게 혼합할 수 `CWindow` 메서드를 호출 하 고 임시 개체를 만들지 않고 Win32 함수 호출 합니다.  
  
 때문에 `CWindow` 해당 하지 않습니다 부여 코드에서 두 개의 데이터 멤버 \(창 핸들 및 기본 크기\)가 있습니다.  또한 많은 `CWindow` 메서드가 단순히 해당 Win32 API 함수를 줄 바꿈 합니다.  사용 하 여 `CWindow`, `HWND` 멤버는 Win32 함수에 자동으로 전달 합니다.  
  
 사용 `CWindow` 직접에서 데이터 나 코드를 클래스에 추가 하 여 산출할 수도 있습니다.  ATL 자체 세 클래스에서 파생 된 `CWindow`:  [CWindowImpl](../atl/implementing-a-window.md),  [CDialogImpl](../atl/implementing-a-dialog-box.md), 및  [CContainedWindowT](../atl/using-contained-windows.md).  
  
## 참고 항목  
 [창 클래스](../atl/atl-window-classes.md)