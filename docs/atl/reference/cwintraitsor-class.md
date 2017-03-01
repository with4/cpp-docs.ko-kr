---
title: "CWinTraitsOR 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CWinTraitsOR
- ATL::CWinTraitsOR
- CWinTraitsOR
dev_langs:
- C++
helpviewer_keywords:
- CWinTraitsOR class
- window styles, default values for ATL
ms.assetid: 1eb7b1e8-a9bd-411b-a30a-35a8a10af989
caps.latest.revision: 20
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
ms.openlocfilehash: cd077c7f79c3099d0e825a48233e7a8b269c0d04
ms.lasthandoff: 02/24/2017

---
# <a name="cwintraitsor-class"></a>CWinTraitsOR 클래스
이 클래스는 창 개체를 만들 때 사용 하는 스타일을 표준화 하기 위한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <DWORD t_dwStyle = 0,
          DWORD t_dwExStyle = 0, 
          class TWinTraits = CControlWinTraits>
class CWinTraitsOR
```  
  
#### <a name="parameters"></a>매개 변수  
 `t_dwStyle`  
 기본 창 스타일입니다.  
  
 `t_dwExStyle`  
 기본 확장된 창 스타일입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CWinTraitsOR::GetWndExStyle](#getwndexstyle)|검색에 대 한 확장된 스타일은 `CWinTraitsOR` 개체입니다.|  
|[CWinTraitsOR::GetWndStyle](#getwndstyle)|검색에 대 한 표준 스타일의 `CWinTraitsOR` 개체입니다.|  
  
## <a name="remarks"></a>주의  
 이 [창 특성](../../atl/understanding-window-traits.md) 클래스는 ATL 창 개체의 생성에 사용 되는 스타일을 표준화 하기 위한 간단한 방법을 제공 합니다. 이 클래스의 특수화에 템플릿 매개 변수로 사용 하 여 [CWindowImpl](../../atl/reference/cwindowimpl-class.md) 또는 다른 ATL의 창 클래스에 사용할 표준 및 확장 된 스타일의 최소 집합을 지정 하려면 해당 창 클래스의 인스턴스.  
  
 이 템플릿의 특수화를 사용 하 여 특정 스타일으로 설정 되어 있는지는 창 클래스의 모든 인스턴스에 대해 동시에 다른 스타일을 허용할 수에 대 한 호출에서 인스턴스별 단위로 설정할 수 있도록 하려는 경우 [CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create)합니다.  
  
 창 스타일 없음 다른 스타일에 대 한 호출에 지정 된 경우에 사용 될 기본 제공 하려는 경우 `CWindowImpl::Create`를 사용 하 여 [용으로 CWinTraits](../../atl/reference/cwintraits-class.md) 대신 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  
  
##  <a name="a-namegetwndstylea--cwintraitsorgetwndstyle"></a><a name="getwndstyle"></a>CWinTraitsOR::GetWndStyle  
 호출 하는 표준 스타일의 조합 (논리적 OR 연산자 사용)를 검색 하려면이 함수는 `CWinTraits` 개체와 지정 된 기본 스타일 `t_dwStyle`합니다.  
  
```
static DWORD GetWndStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStyle`  
 창이 생성에 사용 되는 스타일입니다.  
  
### <a name="return-value"></a>반환 값  
 에 전달 되는 스타일의 조합을 `dwStyle` 및 항목으로 지정 된 기본 `t_dwStyle`, 논리 OR 연산자를 사용 하 여 합니다.  
  
##  <a name="a-namegetwndexstylea--cwintraitsorgetwndexstyle"></a><a name="getwndexstyle"></a>CWinTraitsOR::GetWndExStyle  
 호출의 확장된 스타일의 조합 (논리적 OR 연산자 사용)를 검색 하려면이 함수는 `CWinTraits` 개체와 지정 된 기본 스타일 `t_dwStyle`합니다.  
  
```
static DWORD GetWndExStyle(DWORD dwExStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwExStyle`  
 확장된 스타일 창 만들기에 사용 합니다.  
  
### <a name="return-value"></a>반환 값  
 에 전달 되는 확장된 스타일의 조합을 `dwExStyle` 기본값으로 지정 하 여 지정 하 고 `t_dwExStyle`, 논리 OR 연산자를 사용 하 여  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)   
 [창 특성 이해](../../atl/understanding-window-traits.md)


