---
title: "CWindowImpl 포함 된 창을 구현 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CWindowImpl
dev_langs:
- C++
helpviewer_keywords:
- ATL, windows
- windows [C++], subclassing
- windows [C++], superclassing
- windows [C++], ATL
- subclassing ATL window classes
- superclassing, ATL
ms.assetid: 3fc40550-f1d6-4702-8b7c-4cf682b6a855
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 80aca6af847a33fd7217d0ad710c928f6d2ca32e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-a-window-with-cwindowimpl"></a>CWindowImpl 포함 된 창을 구현합니다.
클래스를 파생 창을 구현 하려면 `CWindowImpl`합니다. 파생된 클래스에서 메시지 맵 및 메시지 처리기 함수를 선언 합니다. 세 가지 방법으로 이제 클래스를 사용할 수 있습니다.  
  
-   [새 Windows 클래스를 기반으로 창을 만듭니다.](#_atl_creating_a_window_based_on_a_new_windows_class)  
  
-   [Superclass 기존 Windows 클래스](#_atl_superclassing_an_existing_windows_class)  
  
-   [기존 창 서브 클래스](#_atl_subclassing_an_existing_window)  
  
##  <a name="_atl_creating_a_window_based_on_a_new_windows_class"></a>새 Windows 클래스를 기반으로 하는 창 만들기  
 `CWindowImpl`포함 된 [DECLARE_WND_CLASS](reference/window-class-macros.md#declare_wnd_class) Windows 클래스 정보를 선언 하는 매크로입니다. 이 매크로 구현 하는 `GetWndClassInfo` 함수를 사용 하 여 [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) 새 Windows 클래스 정보를 정의할 수 있습니다. 때 `CWindowImpl::Create` 라고,이 Windows 클래스 등록 되 고 새 창이 만들어집니다.  
  
> [!NOTE]
>  `CWindowImpl`전달 **NULL** 에 `DECLARE_WND_CLASS` 매크로 ATL Windows 클래스 이름이 생성 됩니다. 고유한 이름을 지정 하려면 문자열을 전달 `DECLARE_WND_CLASS` 에 프로그램 `CWindowImpl`-클래스를 파생 합니다.  
  
## <a name="example"></a>예  
 다음은 새 Windows 클래스를 기반으로 하는 창을 구현 하는 클래스의 예입니다.  
  
 [!code-cpp[NVC_ATL_Windowing#64](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_1.h)]  
  
 창을 만들려면의 인스턴스를 만들고 `CMyWindow` 다음 호출에서 **만들기** 메서드.  
  
> [!NOTE]
>  기본 Windows 클래스 정보를 재정의 하려면 구현는 `GetWndClassInfo` 설정 하 여 파생된 클래스에서 메서드는 `CWndClassInfo` 멤버를 적절 한 값입니다.  
  
##  <a name="_atl_superclassing_an_existing_windows_class"></a>슈퍼 클 래 싱 기존 Windows 클래스  
 [DECLARE_WND_SUPERCLASS](reference/window-class-macros.md#declare_wnd_superclass) 매크로 슈퍼 기존 Windows 창을 만들 수 있습니다. 클래스입니다. 이 매크로 지정 하면 `CWindowImpl`-클래스를 파생 합니다. 다른 ATL 창과 마찬가지로 메시지는 메시지 맵을 처리 합니다.  
  
 사용 하는 경우 `DECLARE_WND_SUPERCLASS`, 새 Windows 클래스 등록 됩니다. 이 새 클래스를 지정 하지만 창 프로시저 바뀝니다 기존 클래스와 동일 됩니다 `CWindowImpl::WindowProc` (또는이 메서드를 재정의 하 여 함수).  
  
## <a name="example"></a>예  
 다음은 예제 클래스의 표준 편집을 슈퍼 클래스:  
  
 [!code-cpp[NVC_ATL_Windowing#65](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_2.h)]  
  
 인스턴스를 만들고 슈퍼 클래스로 지정 된 편집 창을 만들기 위해 `CMyEdit` 호출는 **만들기** 메서드.  
  
##  <a name="_atl_subclassing_an_existing_window"></a>기존 창 서브클래싱  
 기존 창 서브 클래스에서 파생 `CWindowImpl` 메시지 맵이 두 경우에서와 같이 선언 합니다. 단, 하는 것 이므로 하위 클래스는 이미 기존 창을 Windows 클래스 정보를 지정 하지 않으면 합니다.  
  
 호출 하는 대신 **만들기**, 호출 `SubclassWindow` 하위 클래스를 기존 창에 핸들을 전달 합니다. 사용, 서브클래싱된 되 면 `CWindowImpl::WindowProc` (또는이 메서드를 재정의 하 여 함수)을 메시지 맵에 대 한 메시지를 보내도록 합니다. 개체에서 서브클래싱된 창을 분리 하려면 호출 `UnsubclassWindow`합니다. 그런 다음 창의 원본 창 프로시저를 복원 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [창 구현](../atl/implementing-a-window.md)

