---
title: 창 클래스 매크로 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlwin/ATL::DECLARE_WND_CLASS
- atlwin/ATL::DECLARE_WND_SUPERCLASS
- atlwin/ATL::DECLARE_WND_CLASS_EX
dev_langs:
- C++
ms.assetid: ce18681a-2bab-4453-9895-0f3ea47c2b24
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f0490eedb412e43f2ae99c4034648880be5f32a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364234"
---
# <a name="window-class-macros"></a>창 클래스 매크로
이러한 매크로 창 클래스 유틸리티를 정의 합니다.  
  
|||  
|-|-|  
|[DECLARE_WND_CLASS](#declare_wnd_class)|새 창 클래스의 이름을 지정할 수 있습니다.| 
|[DECLARE_WND_CLASS2](#declare_wnd_class2)|(Visual Studio 2017) 새 창 클래스 및 해당 창 프로시저 새 클래스 ´ ֲ 바깥쪽 클래스의 이름을 지정할 수 있습니다.| 
|[DECLARE_WND_SUPERCLASS](#declare_wnd_superclass)|새 창 클래스의 기반이 될 기존 창 클래스의 이름을 지정할 수 있습니다.|  
|[DECLARE_WND_CLASS_EX](#declare_wnd_class_ex)|클래스의 매개 변수를 지정할 수 있습니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  
   
##  <a name="declare_wnd_class"></a>  DECLARE_WND_CLASS  
 새 창 클래스의 이름을 지정할 수 있습니다. 이 매크로 ATL ActiveX 컨트롤의 컨트롤 클래스에 놓습니다.  
  
```
DECLARE_WND_CLASS( WndClassName )
```  
  
### <a name="parameters"></a>매개 변수  
 `WndClassName`  
 [in] 새 창 클래스의 이름입니다. 경우 **NULL**, ATL 창 클래스 이름이 생성 됩니다.  
  
### <a name="remarks"></a>설명  
 /Permissive-compiler 옵션을 사용 하는 경우 다음 DECLARE_WND_CLASS 됩니다 컴파일러 오류가 발생 합니다. DECLARE_WND_CLASS2를 대신 사용 합니다.
 
 DECLARE_WND_CLASS 관리 정보를 가져올 것입니다 새 창 클래스의 이름을 지정할 수 있습니다. [CWndClassInfo](cwndclassinfo-class.md)합니다. `DECLARE_WND_CLASS` 다음과 같은 정적 함수를 구현 하 여 새 창 클래스를 정의 합니다.  
  
 [!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 `DECLARE_WND_CLASS` 새 창에 대 한 다음과 같은 스타일을 지정합니다.  
  
-   CS_HREDRAW  
  
-   CS_VREDRAW  
  
-   CS_DBLCLKS  
  
 `DECLARE_WND_CLASS` 또한 기본 창 배경색을 지정합니다. 사용 하 여는 [DECLARE_WND_CLASS_EX](#declare_wnd_class_ex) 매크로를 사용자 고유의 스타일을 제공 하 고 배경색입니다.  
  
 [CWindowImpl](cwindowimpl-class.md) 사용 하 여는 `DECLARE_WND_CLASS` 매크로 창을 만들기 위해 새 창 클래스에 기반 합니다. 사용 하 여이 동작을 재정의 하려면는 [DECLARE_WND_SUPERCLASS](#declare_wnd_superclass) 매크로의 사용자 지정 구현을 제공 하거나는 [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) 함수입니다.  

  
 ATL에서 창 사용 하는 방법에 대 한 자세한 내용은 문서 참조 [ATL 창 클래스](../../atl/atl-window-classes.md)합니다.  

##  <a name="declare_wnd_class2"></a>  DECLARE_WND_CLASS2  
 (Visual Studio 2017) 요청과 비슷하지만 DECLARE_WND_CLASS는 /permissive-option으로 컴파일할 때 종속 이름이 오류를 방지 하는 추가 매개 변수를 사용 합니다.
  
```
DECLARE_WND_CLASS2( WndClassName, EnclosingClass )
```  
  
### <a name="parameters"></a>매개 변수  
 `WndClassName`  
 [in] 새 창 클래스의 이름입니다. 경우 **NULL**, ATL 창 클래스 이름이 생성 됩니다. 

 `EnclosingClass`  
 [in] 새 창 클래스를 포함 하는 창 클래스의 이름입니다. 일 수 없습니다 **NULL**합니다.  
  
### <a name="remarks"></a>설명 
다음은 /permissive-option을 사용 하는 종속 이름을 포함 하기 때문에 DECLARE_WND_CLASS 컴파일 오류가 발생 합니다. DECLARE_WND_CLASS2이이 매크로에서 사용 되 고는 /permissive-flag에서 오류가 발생 하지 클래스 이름을 명시적으로 지정 해야 합니다.
그렇지 않으면이 매크로 [DECLARE_WND_CLASS](#declare_wnd_class)합니다.
   
##  <a name="declare_wnd_superclass"></a>  DECLARE_WND_SUPERCLASS  
 클래스의 매개 변수를 지정할 수 있습니다. 이 매크로 ATL ActiveX 컨트롤의 컨트롤 클래스에 놓습니다.  
  
```
DECLARE_WND_SUPERCLASS( WndClassName, OrigWndClassName )
```  
  
### <a name="parameters"></a>매개 변수  
 `WndClassName`  
 [in] 창의 이름을 해당가 슈퍼 클래스 `OrigWndClassName`합니다. 경우 **NULL**, ATL 창 클래스 이름이 생성 됩니다.  
  
 `OrigWndClassName`  
 [in] 기존 창 클래스의 이름입니다.  
  
### <a name="remarks"></a>설명  
 이 매크로 사용 하면 기존 창 클래스 superclass 됩니다 하는 창 클래스의 이름을 지정할 수 있습니다. [CWndClassInfo](cwndclassinfo-class.md) 슈퍼 클래스의 정보를 관리 합니다.  
  
 `DECLARE_WND_SUPERCLASS` 다음과 같은 정적 함수를 구현합니다.  
  
 [!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 기본적으로 [CWindowImpl](cwindowimpl-class.md) 사용 하 여는 [DECLARE_WND_CLASS](#declare_wnd_class) 매크로 창을 만들기 위해 새 창 클래스에 기반 합니다. 지정 하 여는 `DECLARE_WND_SUPERCLASS` 에서 매크로 `CWindowImpl`-파생 클래스를 창 클래스를 사용 하는 기존 클래스에 따라 달라 집니다 하지만 창 프로시저를 사용 합니다. 이 기술은 슈퍼 클 래 싱을 라고 합니다.  
  
 사용 하 여 외에도 `DECLARE_WND_CLASS` 및 `DECLARE_WND_SUPERCLASS` 매크로 재정의할 수 있습니다는 [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) 사용자 구현으로 함수입니다.  

  
 ATL에서 창 사용 하는 방법에 대 한 자세한 내용은 문서 참조 [ATL 창 클래스](../../atl/atl-window-classes.md)합니다.  
  
##  <a name="declare_wnd_class_ex"></a>  DECLARE_WND_CLASS_EX  
 새 창 클래스의 기반이 될 기존 창 클래스의 이름을 지정할 수 있습니다. 이 매크로 ATL ActiveX 컨트롤의 컨트롤 클래스에 놓습니다.  
  
```
DECLARE_WND_CLASS_EX( WndClassName, style, bkgnd )
```  
  
### <a name="parameters"></a>매개 변수  
 `WndClassName`  
 [in] 새 창 클래스의 이름입니다. 경우 **NULL**, ATL 창 클래스 이름이 생성 됩니다.  
  
 `style`  
 [in] 창 스타일입니다.  
  
 *배경*  
 [in] 창의 배경색입니다.  
  
### <a name="remarks"></a>설명  
 이 매크로 사용 하면 정보를 가져올으로 관리 되는 새 창 클래스의 클래스 매개 변수를 지정할 수 있습니다 [CWndClassInfo](cwndclassinfo-class.md)합니다. `DECLARE_WND_CLASS_EX` 다음과 같은 정적 함수를 구현 하 여 새 창 클래스를 정의 합니다.  
  
 [!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 기본 스타일과 배경색을 사용 하려는 경우 사용 하 여는 [DECLARE_WND_CLASS](#declare_wnd_class) 매크로입니다. ATL에서 창 사용 하는 방법에 대 한 자세한 내용은 문서 참조 [ATL 창 클래스](../../atl/atl-window-classes.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [매크로](atl-macros.md)









