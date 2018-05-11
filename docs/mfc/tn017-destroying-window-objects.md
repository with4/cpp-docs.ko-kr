---
title: 'TN017: 창 개체 제거 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.objects
dev_langs:
- C++
helpviewer_keywords:
- destroying windows
- TN017
- PostNcDestroy method [MFC]
ms.assetid: 5bf208a5-5683-439b-92a1-547c5ded26cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c6bba255403d31e7a1fa03febb0c760d20cdc81c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="tn017-destroying-window-objects"></a>TN017: 창 개체 제거
사용을 설명 하는이 노트는 [CWnd::PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy) 메서드. 사용자 지정 자동으로 할당 하려는 경우이 메서드를 사용 하 여 `CWnd`-파생 개체입니다. 이 노트도 사용 하는 이유 설명 [CWnd::DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow) 대신 c + + Windows 개체를 제거 하는 `delete` 연산자입니다.  
  
 이 항목의 지침을 따르는 경우에 몇 가지 정리 문제 갖습니다. C + + 메모리와 같은 시스템 리소스를 해제 하지 않으면 delete/해제 하지 않으면 같은 문제에 이러한 문제가 발생할 수 있습니다 `HWND`s, 또는 개체를 너무 여러 번 해제 합니다.  
  
## <a name="the-problem"></a>문제  
 각 windows 개체 (에서 파생 된 클래스의 개체 `CWnd`) c + + 개체를 모두 나타내는 및 `HWND`합니다. C + + 개체는 응용 프로그램의 힙에 할당 하 고 `HWND`의창 관리자가 시스템 리소스에 할당 됩니다. 시스템을 방해 하는 규칙 집합을 제공 해야 있기 때문에 window 개체를 제거 하는 여러 가지 방법으로, 리소스 또는 메모리 누수 합니다. 이러한 규칙 개체 및 Windows 핸들을 한 번도 차단 해야 합니다.  
  
## <a name="destroying-windows"></a>소멸 창  
 다음은 Windows 개체를 제거 하는 두 개의 허용 된 방법입니다.  
  
-   호출 `CWnd::DestroyWindow` 또는 Windows API `DestroyWindow`합니다.  
  
-   사용 하 여 명시적으로 삭제는 `delete` 연산자입니다.  
  
 첫 번째 경우는 단연 가장 일반적입니다. 이 경우 코드를 호출 하지 않는 경우에 적용 됩니다. `DestroyWindow` 직접 합니다. 사용자를 직접 프레임 창을 닫은 경우에이 작업 생성는 `WM_CLOSE` 호출 하는 메시지 및이 메시지에 대 한 기본 응답 `DestroyWindow.` 부모 창이 소멸 될 때 Windows 호출 `DestroyWindow` 모든 자식에 대 한 합니다.  
  
 두 번째 경우, 사용 된 `delete` Windows 개체에 연산자는 거의 발생 하지 않아야 합니다. 다음은 사용 하는 경우에 따라 `delete` 올바른 선택입니다.  
  
## <a name="auto-cleanup-with-cwndpostncdestroy"></a>CWnd::PostNcDestroy와 자동 정리  
 창에 전송 마지막 Windows 메시지는 Windows 창을 제거 하는 시스템 때 `WM_NCDESTROY`합니다. 기본 `CWnd` 해당 메시지에 대 한 처리기는 [:: Onncdestroy](../mfc/reference/cwnd-class.md#onncdestroy)합니다. `OnNcDestroy` 분리 됩니다는 `HWND` 가상 함수를 호출 하 고 개체는 c + +에서 `PostNcDestroy`합니다. 일부 클래스는 c + + 개체를 삭제 하려면이 함수를 재정의 합니다.  
  
 기본 구현은 `CWnd::PostNcDestroy` 아무 것도 수행 된 스택 프레임에 할당 된 파일이 나 다른 개체에 포함 된 창 개체에 대 한 적합 합니다. 다른 개체가 없는 힙에 할당 하도록 설계 된 창 개체에 대 한 적합 하지 않습니다. 즉, 다른 c + + 개체에 포함 되지 않는 창 개체에 대 한 적합 하지 않습니다.  
  
 이러한 클래스는 힙에 할당 하도록 설계 된 재정의 `PostNcDestroy` 수행 하는 메서드는 `delete this`합니다. 이 문은 c + + 개체와 연결 된 모든 메모리를 해제 합니다. 경우에 기본 `CWnd` 소멸자 호출 `DestroyWindow` 경우 `m_hWnd` 가 NULL이 아닌 경우이를 초래 하지 않습니다 무한 재귀가 핸들 정리 단계에서 분리 하 고 NULL 하 게 되므로 합니다.  
  
> [!NOTE]
>  시스템에서 일반적으로 호출할 `CWnd::PostNcDestroy` Windows 처리 한 후 `WM_NCDESTROY` 메시지 및 `HWND` 및 c + + 창 개체에 연결 되어 있지 않습니다. 시스템은 호출 또한 `CWnd::PostNcDestroy` 대부분의 구현에서 [CWnd::Create](../mfc/reference/cwnd-class.md#create) 오류가 발생 하면 호출 됩니다. 자동 정리 규칙은이 항목의 뒷부분에 설명 되어 있습니다.  
  
## <a name="auto-cleanup-classes"></a>자동 정리 클래스  
 다음 클래스는 자동 정리를 위해 설계 되지 않습니다. 값 형식은 일반적으로 스택 또는 다른 c + + 개체에 포함 됩니다.  
  
-   모든 표준 Windows 컨트롤 (`CStatic`, `CEdit`, `CListBox`등).  
  
-   모든 자식 창에서 직접 파생 `CWnd` (예를 들어 사용자 지정 컨트롤).  
  
-   분할 창 (`CSplitterWnd`).  
  
-   기본 컨트롤 막대 (클래스에서 파생 된 `CControlBar`, 참조 [Technical Note 31](../mfc/tn031-control-bars.md) 컨트롤 막대 개체 자동 삭제를 사용 하기 위한)입니다.  
  
-   대화 상자 (`CDialog`) 스택 프레임에 모달 대화 상자를 위한 것입니다.  
  
-   모든 표준 제외 하 고 대화 상자의 `CFindReplaceDialog`합니다.  
  
-   클래스 마법사에서 만든 기본 대화 상자입니다.  
  
 다음 클래스는 자동 정리를 위해 설계 되었습니다. 일반적으로 힙에 직접 할당 되기:  
  
-   주 프레임 창 (에서 직접 또는 간접적으로 파생 `CFrameWnd`).  
  
-   보기 창 (에서 직접 또는 간접적으로 파생 `CView`).  
  
 이러한 규칙을 중단 하려는 경우 재정의 해야는 `PostNcDestroy` 파생된 클래스에서 메서드. 자동 정리를 클래스를 추가 하려면 기본 클래스를 호출 하 고 다음 실행 한 `delete this`합니다. 클래스에서 자동 정리를 제거 하려면 호출 `CWnd::PostNcDestroy` 직접 대신의 `PostNcDestroy` 직접 기본 클래스의 메서드로 합니다.  
  
 자동 정리 동작 변경의 가장 일반적인 용도 힙에 할당 될 수 있는 모덜리스 대화 상자를 만드는 것입니다.  
  
## <a name="when-to-call-delete"></a>호출 삭제 해야 하는 경우  
 호출 하는 것이 좋습니다 `DestroyWindow` c + + 메서드 또는 전역 Windows 개체를 소멸 시킬 `DestroyWindow` API입니다.  
  
 전역 호출 하지 마십시오 `DestroyWindow` MDI 자식 창을 삭제 하는 API입니다. 가상 메서드를 사용 해야 `CWnd::DestroyWindow` 대신 합니다.  
  
 C + + 창 자동 정리를 수행 하지 않는 개체를 사용 하 여는 `delete` 연산자 수를 호출 하려고 할 때 메모리 누수를 발생 `DestroyWindow` 에 `CWnd::~CWnd` 소멸자는 VTBL 올바르게 파생된 클래스를 가리키지 않는 경우. 이 시스템이 적절 한 destroy 호출할 메서드를 찾을 수 때문에 발생 합니다. 사용 하 여 `DestroyWindow` 대신 `delete` 이러한 문제를 방지 합니다. 미묘한 오류일 수 있습니다, 때문에 디버그 모드에서 컴파일하면 생성 합니다 다음과 같은 경고가 위험이 있습니다.  
  
```  
Warning: calling DestroyWindow in CWnd::~CWnd  
    OnDestroy or PostNcDestroy in derived class will not be called  
```  
  
 자동 정리를 수행 하는 c + + 창 개체의 경우 호출 해야 `DestroyWindow`합니다. 사용 하는 경우는 `delete` 연산자를 직접 MFC 진단 메모리 할당자에서 알려는 하는 메모리를 해제 두 번입니다. 두 개의 각 항목은 첫 번째 명시적 통화 및 간접 호출 `delete this` 의 자동 정리 구현에서 `PostNcDestroy`합니다.  
  
 호출한 후 `DestroyWindow` 자동 정리가 아닌 개체에 c + + 개체 됩니다, 있지만 `m_hWnd` NULL이 됩니다. 호출한 후 `DestroyWindow` 에 자동 정리 되는 개체로, c + + 개체 됩니다 사라지지만의 자동 정리 구현에서 c + + delete 연산자에 의해 해제 `PostNcDestroy`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

