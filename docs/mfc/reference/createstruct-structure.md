---
title: "CREATESTRUCT 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CREATESTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CREATESTRUCT 구조체"
ms.assetid: 028c7b5e-4fdc-48da-a550-d3e4f9e6cc85
caps.latest.revision: 14
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CREATESTRUCT 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CREATESTRUCT`  구조는 응용 프로그램의 창 프로시저에 전달 된 초기화 매개 변수를 정의 합니다.  
  
## 구문  
  
```  
  
      typedef struct tagCREATESTRUCT {  
   LPVOID lpCreateParams;  
   HANDLE hInstance;  
   HMENU hMenu;  
   HWND hwndParent;  
   int cy;  
   int cx;  
   int y;  
   int x;  
   LONG style;  
   LPCSTR lpszName;  
   LPCSTR lpszClass;  
   DWORD dwExStyle;  
} CREATESTRUCT;  
```  
  
#### 매개 변수  
 `lpCreateParams`  
 창을 만드는 데 사용할 데이터를 가리킵니다.  
  
 `hInstance`  
 새 창을 담당 하는 모듈의 모듈 인스턴스 핸들을 식별 합니다.  
  
 `hMenu`  
 새 창에서 사용할 메뉴를 식별 합니다.  자식 창이 포함 된 정수 id입니다.  
  
 `hwndParent`  
 새 창을 소유 하는 창을 식별 합니다.  이 멤버는 **NULL** 경우 새로운 최상위 창입니다.  
  
 `cy`  
 창의 새 높이\(픽셀\)입니다.  
  
 `cx`  
 창의 새 높이\(픽셀\)입니다.  
  
 `y`  
 새 창의 왼쪽된 위 모퉁이의 y 좌표를 지정합니다.  새 창의 자식 창입니다;이 좌표는 부모 창을 기준으로 그렇지 않으면 좌표가 화면 원점을 기준으로 합니다.  
  
 `x`  
 새 창의 왼쪽된 위 모퉁이의 x 좌표를 지정합니다.  새 창의 자식 창입니다;이 좌표는 부모 창을 기준으로 그렇지 않으면 좌표가 화면 원점을 기준으로 합니다.  
  
 `style`  
 새 [스타일](../../mfc/reference/styles-used-by-mfc.md)창을 지정합니다.  
  
 `lpszName`  
 새 창에 이름을 지정 하는 null로 끝나는 문자열을 가리킵니다.  
  
 `lpszClass`  
 새 창은 Windows 클래스의 이름을 지정 하는 null로 끝나는 문자열을 가리키는 \(에  [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) 구조체입니다. 자세한 내용은 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]\) 하세요.  
  
 `dwExStyle`  
 [확장된 스타일](../../mfc/reference/extended-window-styles.md) 새 창에 대해 지정합니다.  
  
## 요구 사항  
 **헤더:** winuser.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCreate](../Topic/CWnd::OnCreate.md)