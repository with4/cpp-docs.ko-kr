---
title: "CREATESTRUCT 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CREATESTRUCT
dev_langs:
- C++
helpviewer_keywords:
- CREATESTRUCT structure
ms.assetid: 028c7b5e-4fdc-48da-a550-d3e4f9e6cc85
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ec72d4725cb7e5959369b24a6ff7f0e3e9da1ca7
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="createstruct-structure"></a>CREATESTRUCT 구조체
`CREATESTRUCT` 구조는 응용 프로그램의 창 프로시저에 전달 된 초기화 매개 변수를 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
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
  
#### <a name="parameters"></a>매개 변수  
 `lpCreateParams`  
 창을 만드는 데 사용할 데이터를 가리킵니다.  
  
 `hInstance`  
 새 창을 소유 하는 모듈의 모듈 인스턴스 핸들을 식별 합니다.  
  
 `hMenu`  
 새 창에서 사용할 메뉴를 식별 합니다. 정수 ID를 포함 하는 경우 자식 창  
  
 `hwndParent`  
 새 창을 소유 하는 창을 식별 합니다. 이 멤버는 **NULL** 경우 새 최상위 창입니다.  
  
 `cy`  
 새 창의 높이 지정합니다.  
  
 `cx`  
 새 창의 너비를 지정합니다.  
  
 `y`  
 새 창의 왼쪽된 위 모퉁이의 y 좌표를 지정합니다. 새 창의 자식 창이; 면 좌표는 부모 창을 기준으로 그렇지 않으면 좌표는 화면 원점을 기준으로 합니다.  
  
 `x`  
 새 창의 왼쪽된 위 모퉁이의 x 좌표를 지정합니다. 새 창의 자식 창이; 면 좌표는 부모 창을 기준으로 그렇지 않으면 좌표는 화면 원점을 기준으로 합니다.  
  
 `style`  
 새 창을 지정 [스타일](../../mfc/reference/styles-used-by-mfc.md)합니다.  
  
 `lpszName`  
 새 창의 이름을 지정 하는 null로 끝나는 문자열을 가리킵니다.  
  
 `lpszClass`  
 새 창을 Windows 클래스 이름을 지정 하는 null로 끝나는 문자열을 가리킵니다 (한 [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) 구조; 자세한 내용은 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]).  
  
 `dwExStyle`  
 지정 된 [확장 스타일](../../mfc/reference/extended-window-styles.md) 새 창에 대 한 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** winuser.h  
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)



