---
title: "창 클래스 매크로 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: ce18681a-2bab-4453-9895-0f3ea47c2b24
caps.latest.revision: 16
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
translationtype: Machine Translation
ms.sourcegitcommit: 8cdedc5cfac9d49df812ae6fcfcc548201b1edb5
ms.openlocfilehash: f32926b6efd4ffb9c0541c0574a479c13dac01df
ms.lasthandoff: 02/24/2017

---
# <a name="window-class-macros"></a>창 클래스 매크로
이러한 매크로 창 클래스 유틸리티를 정의합니다.  
  
|||  
|-|-|  
|[DECLARE_WND_CLASS](#declare_wnd_class)|새 창 클래스의 이름을 지정할 수 있습니다.| 
|[DECLARE_WND_CLASS2](#declare_wnd_class2)|(Visual Studio 2017) 새 창 클래스와 새 클래스는 사용 하 여 해당 창 프로시저는 바깥쪽 클래스의 이름을 지정할 수 있습니다.| 
|[DECLARE_WND_SUPERCLASS](#declare_wnd_superclass)|새 창 클래스의 기반이 될 기존 창 클래스의 이름을 지정할 수 있습니다.|  
|[DECLARE_WND_CLASS_EX](#declare_wnd_class_ex)|클래스의 매개 변수를 지정할 수 있습니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  
   
##  <a name="a-namedeclarewndclassa--declarewndclass"></a><a name="declare_wnd_class"></a>DECLARE_WND_CLASS  
 새 창 클래스의 이름을 지정할 수 있습니다. 이 매크로 ATL ActiveX 컨트롤의 컨트롤 클래스에 놓습니다.  
  
```
DECLARE_WND_CLASS( WndClassName )
```  
  
### <a name="parameters"></a>매개 변수  
 `WndClassName`  
 [in] 새 창 클래스의 이름입니다. 경우 **NULL**, ATL 창 클래스 이름이 생성 됩니다.  
  
### <a name="remarks"></a>주의  
 /Permissive-compiler 옵션을 사용 하는 경우 다음 DECLARE_WND_CLASS 하면 컴파일러 오류가 발생 합니다. DECLARE_WND_CLASS2를 대신 사용 합니다.
 
 DECLARE_WND_CLASS 정보를 관리할 새 창 클래스의 이름을 지정할 수 있습니다. [CWndClassInfo](cwndclassinfo-class.md)합니다. `DECLARE_WND_CLASS`다음과 같은 정적 함수를 구현 하 여 새 창 클래스를 정의 합니다.  
  
 [!code-cpp[NVC_ATL_Windowing&127;](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 `DECLARE_WND_CLASS`새 창에 대 한 다음과 같은 스타일을 지정합니다.  
  
-   CS_HREDRAW  
  
-   CS_VREDRAW  
  
-   CS_DBLCLKS  
  
 `DECLARE_WND_CLASS`또한 기본 창의 배경색을 지정합니다. 사용 된 [DECLARE_WND_CLASS_EX](#declare_wnd_class_ex) 배경색 및 스타일을 직접 제공 하는 매크로입니다.  
  
 [CWindowImpl](cwindowimpl-class.md) 사용 하는 `DECLARE_WND_CLASS` 가 새 창 클래스를 기반으로 창을 만들 수는 매크로입니다. 사용 하 여이 동작을 재정의 하려면는 [DECLARE_WND_SUPERCLASS](#declare_wnd_superclass) 매크로의 고유한 구현을 제공 또는 [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) 함수입니다.  

  
 ATL에서 창 사용 하는 방법에 대 한 자세한 내용은 문서를 참조 하십시오. [ATL 창 클래스](../../atl/atl-window-classes.md)합니다.  

##  <a name="a-namedeclarewndclass2a--declarewndclass2"></a><a name="declare_wnd_class2"></a>DECLARE_WND_CLASS2  
 (Visual Studio 2017) 비슷하지만 DECLARE_WND_CLASS는 /permissive-option으로 컴파일할 때 종속 이름 오류를 방지 하는 추가 매개 변수를 사용 합니다.
  
```
DECLARE_WND_CLASS2( WndClassName, EnclosingClass )
```  
  
### <a name="parameters"></a>매개 변수  
 `WndClassName`  
 [in] 새 창 클래스의 이름입니다. 경우 **NULL**, ATL 창 클래스 이름이 생성 됩니다. 

 `EnclosingClass`  
 [in] 새 창 클래스를 포함 하는 창 클래스의 이름입니다. 안 **NULL**합니다.  
  
### <a name="remarks"></a>주의 
다음은 /permissive-option을 사용 하는 종속 이름을 포함 하기 때문에 DECLARE_WND_CLASS 컴파일 오류가 발생 합니다. DECLARE_WND_CLASS2이이 매크로에 사용 되 고는 /permissive-flag에서 오류가 발생 하지는 클래스 이름을 명시적으로 지정 해야 합니다.
그렇지 않으면이 매크로 [DECLARE_WND_CLASS](#declare_wnd_class)합니다.
   
##  <a name="a-namedeclarewndsuperclassa--declarewndsuperclass"></a><a name="declare_wnd_superclass"></a>DECLARE_WND_SUPERCLASS  
 클래스의 매개 변수를 지정할 수 있습니다. 이 매크로 ATL ActiveX 컨트롤의 컨트롤 클래스에 놓습니다.  
  
```
DECLARE_WND_SUPERCLASS( WndClassName, OrigWndClassName )
```  
  
### <a name="parameters"></a>매개 변수  
 `WndClassName`  
 [in] 창의 이름을 그는 슈퍼 클래스 `OrigWndClassName`합니다. 경우 **NULL**, ATL 창 클래스 이름이 생성 됩니다.  
  
 `OrigWndClassName`  
 [in] 기존 창 클래스의 이름입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하는 슈퍼 클래스 기존 창 클래스 하는 창 클래스의 이름을 지정할 수 있습니다. [CWndClassInfo](cwndclassinfo-class.md) 슈퍼 클래스의 정보를 관리 합니다.  
  
 `DECLARE_WND_SUPERCLASS`다음과 같은 정적 함수를 구현합니다.  
  
 [!code-cpp[NVC_ATL_Windowing&127;](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 기본적으로 [CWindowImpl](cwindowimpl-class.md) 사용 하는 [DECLARE_WND_CLASS](#declare_wnd_class) 가 새 창 클래스를 기반으로 창을 만들 수는 매크로입니다. 지정 하 여는 `DECLARE_WND_SUPERCLASS` 에서 매크로 `CWindowImpl`-파생 클래스인 창 클래스를 사용 하는 기존 클래스에 따라 달라 집니다 하지만 창 프로시저를 사용 합니다. 이 기술은 슈퍼 클 래 싱을 라고 합니다.  
  
 사용 하 여 외에도 `DECLARE_WND_CLASS` 및 `DECLARE_WND_SUPERCLASS` 매크로 재정의할 수 있습니다는 [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) 함수를 자체 구현으로 합니다.  

  
 ATL에서 창 사용 하는 방법에 대 한 자세한 내용은 문서를 참조 하십시오. [ATL 창 클래스](../../atl/atl-window-classes.md)합니다.  
  
##  <a name="a-namedeclarewndclassexa--declarewndclassex"></a><a name="declare_wnd_class_ex"></a>DECLARE_WND_CLASS_EX  
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
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하면 정보를 관리할 새 창 클래스의 클래스 매개 변수를 지정할 수 있습니다 [CWndClassInfo](cwndclassinfo-class.md)합니다. `DECLARE_WND_CLASS_EX`다음과 같은 정적 함수를 구현 하 여 새 창 클래스를 정의 합니다.  
  
 [!code-cpp[NVC_ATL_Windowing&127;](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 사용 하 여 기본 스타일 및 배경색을 사용 하려는 경우는 [DECLARE_WND_CLASS](#declare_wnd_class) 매크로입니다. ATL에서 창 사용 하는 방법에 대 한 자세한 내용은 문서를 참조 하십시오. [ATL 창 클래스](../../atl/atl-window-classes.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [매크로](atl-macros.md)










