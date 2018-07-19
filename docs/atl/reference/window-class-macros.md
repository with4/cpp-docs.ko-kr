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
ms.openlocfilehash: 470c1c8e3facbeba909e182b97a8b027dc9e8ca8
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879683"
---
# <a name="window-class-macros"></a>창 클래스 매크로
이러한 매크로 창 클래스 유틸리티를 정의 합니다.  
  
|||  
|-|-|  
|[DECLARE_WND_CLASS](#declare_wnd_class)|새 창 클래스의 이름을 지정할 수 있습니다.| 
|[DECLARE_WND_CLASS2](#declare_wnd_class2)|(Visual Studio 2017) 새 창 클래스와 새 클래스를 사용 하 여 창 프로시저는 바깥쪽 클래스의 이름을 지정할 수 있습니다.| 
|[DECLARE_WND_SUPERCLASS](#declare_wnd_superclass)|새 창 클래스를 기반으로 하는 기존 창 클래스의 이름을 지정할 수 있습니다.|  
|[DECLARE_WND_CLASS_EX](#declare_wnd_class_ex)|클래스의 매개 변수를 지정할 수 있습니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  
   
##  <a name="declare_wnd_class"></a>  DECLARE_WND_CLASS  
 새 창 클래스의 이름을 지정할 수 있습니다. 이 매크로 ATL ActiveX 컨트롤의 컨트롤 클래스에 놓습니다.  
  
```
DECLARE_WND_CLASS( WndClassName )
```  
  
### <a name="parameters"></a>매개 변수  
 *WndClassName*  
 [in] 새 창 클래스의 이름입니다. NULL 인 경우 ATL 창 클래스 이름이 생성 됩니다.  
  
### <a name="remarks"></a>설명  
 /Permissive-compiler 옵션을 사용 하는 경우 다음 DECLARE_WND_CLASS 하면 컴파일러 오류가 발생 합니다. DECLARE_WND_CLASS2를 대신 사용 합니다.
 
 DECLARE_WND_CLASS을 사용 하면 정보를 가져올에서 관리할 새 창 클래스의 이름을 지정할 수 있습니다 [CWndClassInfo](cwndclassinfo-class.md)합니다. DECLARE_WND_CLASS 다음 정적 함수를 구현 하 여 새 창 클래스를 정의 합니다.  
  
 [!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 DECLARE_WND_CLASS 새 창에 대 한 다음과 같은 스타일을 지정합니다.  
  
-   CS_HREDRAW  
  
-   CS_VREDRAW  
  
-   CS_DBLCLKS  
  
 또한 DECLARE_WND_CLASS 기본 창의 배경색을 지정합니다. 사용 된 [DECLARE_WND_CLASS_EX](#declare_wnd_class_ex) 매크로를 사용자 고유의 스타일을 제공 하 고 배경색입니다.  
  
 [CWindowImpl](cwindowimpl-class.md) DECLARE_WND_CLASS 매크로 사용 하 여 새 창 클래스를 기반으로 창을 만듭니다. 사용 하 여이 동작을 재정의 하려면 합니다 [DECLARE_WND_SUPERCLASS](#declare_wnd_superclass) 매크로의 고유한 구현을 제공 합니다 [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) 함수.  

  
 ATL에서 창 사용 하는 방법에 대 한 자세한 내용은 문서 참조 [ATL 창 클래스](../../atl/atl-window-classes.md)합니다.  

##  <a name="declare_wnd_class2"></a>  DECLARE_WND_CLASS2  
 (Visual Studio 2017) 비슷하지만 DECLARE_WND_CLASS는 /permissive-option으로 컴파일하는 경우 종속 이름 오류를 방지 하는 추가 매개 변수를 사용 합니다.
  
```
DECLARE_WND_CLASS2( WndClassName, EnclosingClass )
```  
  
### <a name="parameters"></a>매개 변수  
 *WndClassName*  
 [in] 새 창 클래스의 이름입니다. NULL 인 경우 ATL 창 클래스 이름이 생성 됩니다. 

 *EnclosingClass*  
 [in] 새 창 클래스를 포함 하는 창 클래스의 이름입니다. NULL일 수 없습니다.  
  
### <a name="remarks"></a>설명 
다음을 /permissive-option을 사용 하는 종속 이름이 포함 되어 있으므로 DECLARE_WND_CLASS 컴파일 오류가 발생 합니다. DECLARE_WND_CLASS2이이 매크로 하 고는 /permissive-flag에서 오류가 발생 하지 않습니다 클래스 이름을 명시적으로 지정 해야 합니다.
그렇지 않은 경우이 매크로 동일 [DECLARE_WND_CLASS](#declare_wnd_class)합니다.
   
##  <a name="declare_wnd_superclass"></a>  DECLARE_WND_SUPERCLASS  
 클래스의 매개 변수를 지정할 수 있습니다. 이 매크로 ATL ActiveX 컨트롤의 컨트롤 클래스에 놓습니다.  
  
```
DECLARE_WND_SUPERCLASS( WndClassName, OrigWndClassName )
```  
  
### <a name="parameters"></a>매개 변수  
 *WndClassName*  
 [in] 창의 이름을 해당는 슈퍼 클래스 *OrigWndClassName*합니다. NULL 인 경우 ATL 창 클래스 이름이 생성 됩니다.  
  
 *OrigWndClassName*  
 [in] 기존 창 클래스의 이름입니다.  
  
### <a name="remarks"></a>설명  
 이 매크로 사용 하면 기존 창 클래스를 슈퍼 클래스에는 창 클래스의 이름을 지정할 수 있습니다. [CWndClassInfo](cwndclassinfo-class.md) 슈퍼 클래스의 정보를 관리 합니다.  
  
 DECLARE_WND_SUPERCLASS 다음 정적 함수를 구현합니다.  
  
 [!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 기본적으로 [CWindowImpl](cwindowimpl-class.md) 사용 하는 [DECLARE_WND_CLASS](#declare_wnd_class) 새 창 클래스를 기반으로 창을 만들려면 매크로입니다. DECLARE_WND_SUPERCLASS 매크로 지정 하 여를 `CWindowImpl`-클래스를 파생 된 창 클래스를 사용 하는 기존 클래스에 따라 달라 집니다 하지만 창 프로시저를 사용 합니다. 이 기술은 슈퍼 클 래 싱을 라고 합니다.  
  
 DECLARE_WND_CLASS 및 DECLARE_WND_SUPERCLASS 매크로 사용 하는 것 외에도 재정의할 수 있습니다 합니다 [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) 고유한 구현 사용 하 여 함수입니다.  

  
 ATL에서 창 사용 하는 방법에 대 한 자세한 내용은 문서 참조 [ATL 창 클래스](../../atl/atl-window-classes.md)합니다.  
  
##  <a name="declare_wnd_class_ex"></a>  DECLARE_WND_CLASS_EX  
 새 창 클래스를 기반으로 하는 기존 창 클래스의 이름을 지정할 수 있습니다. 이 매크로 ATL ActiveX 컨트롤의 컨트롤 클래스에 놓습니다.  
  
```
DECLARE_WND_CLASS_EX( WndClassName, style, bkgnd )
```  
  
### <a name="parameters"></a>매개 변수  
 *WndClassName*  
 [in] 새 창 클래스의 이름입니다. NULL 인 경우 ATL 창 클래스 이름이 생성 됩니다.  
  
 *style*  
 [in] 창 스타일입니다.  
  
 *배경*  
 [in] 창의 배경색입니다.  
  
### <a name="remarks"></a>설명  
 이 매크로 사용 하면 정보를 가져올에서 관리할 새 창 클래스의 클래스 매개 변수를 지정할 수 있습니다 [CWndClassInfo](cwndclassinfo-class.md)합니다. DECLARE_WND_CLASS_EX 다음 정적 함수를 구현 하 여 새 창 클래스를 정의 합니다.  
  
 [!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 기본 스타일 및 배경색을 사용 하려는 경우 사용 합니다 [DECLARE_WND_CLASS](#declare_wnd_class) 매크로입니다. ATL에서 창 사용 하는 방법에 대 한 자세한 내용은 문서 참조 [ATL 창 클래스](../../atl/atl-window-classes.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [매크로](atl-macros.md)









