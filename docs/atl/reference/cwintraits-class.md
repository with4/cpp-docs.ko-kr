---
title: "용으로 CWinTraits 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinTraits
- ATLWIN/ATL::CWinTraits
- ATLWIN/ATL::CWinTraits::GetWndExStyle
- ATLWIN/ATL::CWinTraits::GetWndStyle
dev_langs:
- C++
helpviewer_keywords:
- CMDIChildWinTraits class
- window styles, default values for ATL
- CWinTraits class
- CFrameWinTraits class
- CControlWinTraits class
ms.assetid: f78f486e-6d9c-42c6-8e86-371e05aa7e59
caps.latest.revision: 19
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: abd62b916f976721bf85fc4bb2a94ffaf5b217ea
ms.lasthandoff: 02/24/2017

---
# <a name="cwintraits-class"></a>용으로 CWinTraits 클래스
이 클래스는 창 개체를 만들 때 사용 하는 스타일을 표준화 하기 위한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <DWORD t_dwStyle = 0, DWORD t_dwExStyle = 0>  class CWinTraits
```  
  
#### <a name="parameters"></a>매개 변수  
 `t_dwStyle`  
 기본 표준 창 스타일입니다.  
  
 `t_dwExStyle`  
 기본 확장된 창 스타일입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CWinTraits::GetWndExStyle](#getwndexstyle)|(정적) 검색에 대 한 확장된 스타일은 `CWinTraits` 개체입니다.|  
|[CWinTraits::GetWndStyle](#getwndstyle)|(정적) 검색에 대 한 표준 스타일의 `CWinTraits` 개체입니다.|  
  
## <a name="remarks"></a>주의  
 이 [창 특성](../../atl/understanding-window-traits.md) 클래스는 ATL 창 개체의 생성에 사용 되는 스타일을 표준화 하기 위한 간단한 방법을 제공 합니다. 이 클래스의 특수화에 템플릿 매개 변수로 사용 하 여 [CWindowImpl](../../atl/reference/cwindowimpl-class.md) 또는 다른 ATL의 창 클래스에 사용 되는 기본 표준 및 확장 스타일을 지정 하려면 해당 창 클래스의 인스턴스.  
  
 창 스타일 없음 다른 스타일에 대 한 호출에 지정 된 경우에 사용 될 기본 제공 하려는 경우이 서식 파일을 사용 하 여 [CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create)합니다.  
  
 ATL 창 스타일의 자주 사용 되는 조합에 대 한이 서식 파일의 미리 정의 된 세 가지 특수화를 제공합니다.  
  
 `CControlWinTraits`  
 표준 제어 창을 위한 것입니다. 다음과 같은 표준 스타일을 사용: **WS_CHILD**, **WS_VISIBLE**, **WS_CLIPCHILDREN**, 및 **WS_CLIPSIBLINGS**합니다. 확장된 스타일 없음 있습니다.  
  
 `CFrameWinTraits`  
 표준 프레임 창을 위한 것입니다. 사용 하는 표준 스타일 포함: **WS_OVERLAPPEDWINDOW**, **WS_CLIPCHILDREN**, 및 **WS_CLIPSIBLINGS**합니다. 사용 하는 확장된 스타일 포함: **WS_EX_APPWINDOW** 및 **WS_EX_WINDOWEDGE**합니다.  
  
 `CMDIChildWinTraits`  
 표준 MDI 자식 창을 위한 것입니다. 사용 하는 표준 스타일 포함: **WS_OVERLAPPEDWINDOW**, **WS_CHILD**, **WS_VISIBLE**, **WS_CLIPCHILDREN**, 및 **WS_CLIPSIBLINGS**합니다. 사용 하는 확장된 스타일 포함: **WS_EX_MDICHILD**합니다.  
  
 다른 스타일을 인스턴스별 별로 설정할 수 있도록 허용 하면서 창 클래스의 모든 인스턴스 사용에 대 한 특정 스타일 설정 되어 있는지 확인 하려는 경우 [CWinTraitsOR](../../atl/reference/cwintraitsor-class.md) 대신 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  
  
##  <a name="getwndstyle"></a>CWinTraits::GetWndStyle  
 호출 하는 표준 스타일을 검색 하려면이 함수는 `CWinTraits` 개체입니다.  
  
```
static DWORD GetWndStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStyle`  
 창이 생성에 사용 되는 표준 스타일입니다. 경우 `dwStyle` 가 0 이면 템플릿 스타일 값 ( `t_dwStyle`)이 반환 됩니다. 경우 `dwStyle` 이 값은&0; `dwStyle` 반환 됩니다.  
  
### <a name="return-value"></a>반환 값  
 개체의 표준 창 스타일입니다.  
  
##  <a name="getwndexstyle"></a>CWinTraits::GetWndExStyle  
 호출의 확장된 스타일을 검색 하려면이 함수는 `CWinTraits` 개체입니다.  
  
```
static DWORD GetWndExStyle(DWORD dwExStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwExStyle`  
 확장된 스타일 창 만들기에 사용 합니다. 경우 `dwExStyle` 가 0 이면 템플릿 스타일 값 ( `t_dwExStyle`)이 반환 됩니다. 경우 `dwExStyle` 이 값은&0; `dwExStyle` 반환 됩니다.  
  
### <a name="return-value"></a>반환 값  
 개체의 확장된 창 스타일입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 멤버](http://msdn.microsoft.com/en-us/dbe6a147-3f01-4aea-a3fb-fe6ebadc31f8)   
 [클래스 개요](../../atl/atl-class-overview.md)   
 [창 특성 이해](../../atl/understanding-window-traits.md)

