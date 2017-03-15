---
title: "_U_MENUorID 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL._U_MENUorID
- ATL::_U_MENUorID
- _U_MENUorID
dev_langs:
- C++
helpviewer_keywords:
- U_MENUorID class
- _U_MENUorID class
ms.assetid: cfc8032b-61b4-4a68-ba3a-92b82500ccae
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: f7c0a5c34c4e103f830a029f58cdfa00dcb58a32
ms.lasthandoff: 02/24/2017

---
# <a name="umenuorid-class"></a>_U_MENUorID 클래스
이 클래스에 대 한 래퍼를 제공 합니다. **CreateWindow** 및 **CreateWindowEx**합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class _U_MENUorID
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[_U_MENUorID::_U_MENUorID](#_u_menuorid___u_menuorid)|생성자입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[_U_MENUorID::m_hMenu](#_u_menuorid__m_hmenu)|메뉴에 대 한 핸들입니다.|  
  
## <a name="remarks"></a>주의  
 이 인수 어댑터 클래스 Id 중 하나를 사용 하면 ( **UINT**s) 또는 메뉴 핸들 ( `HMENU`s)의 호출자에 명시적 캐스트가 필요 없이 함수를 전달 하도록 합니다.  
  
 이 클래스는 Windows API에 대 한 래퍼를 구현 하기 위한 설계 되었습니다 특히 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) 및 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) 함수를 허용 하는 `HMENU` 자식 창 식별자가 될 수 있는 인수 ( **UINT**) 메뉴 핸들 대신 합니다. 예를 들어,이 클래스를 사용에서 하는 매개 변수를 볼 수 있습니다 [CWindowImpl::Create](cwindowimpl-class.md#create)합니다.  

  
 이 클래스는 두 개의 생성자 오버 로드: 허용 하나는 **UINT** 수락 하 고 다른 인수는 `HMENU` 인수. **UINT** 인수는 방금 캐스팅는 `HMENU` 생성자는 클래스의 단일 데이터 멤버에 저장 된 결과에서 [m_hMenu](#_u_menuorid__m_hmenu)합니다. 에 대 한 인수는 `HMENU` 생성자 변환 하지 않고 직접 저장 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  
  
##  <a name="a-nameumenuoridmhmenua--umenuoridmhmenu"></a><a name="_u_menuorid__m_hmenu"></a>_U_MENUorID::m_hMenu  
 클래스는 공용으로 해당 생성자 중 하나에 전달 하는 값을 보유 `HMENU` 데이터 멤버입니다.  
  
```
HMENU m_hMenu;
```  
  
##  <a name="a-nameumenuoridumenuorida--umenuoridumenuorid"></a><a name="_u_menuorid___u_menuorid"></a>_U_MENUorID::_U_MENUorID  
 **UINT** 인수는 방금 캐스팅는 `HMENU` 생성자는 클래스의 단일 데이터 멤버에 저장 된 결과에서 [m_hMenu](#_u_menuorid__m_hmenu)합니다.  
  
```
_U_MENUorID(UINT nID);  
_U_MENUorID(HMENU hMenu);
```  
  
### <a name="parameters"></a>매개 변수  
 `nID`  
 자식 창 식별자입니다.  
  
 `hMenu`  
 메뉴 핸들입니다.  
  
### <a name="remarks"></a>주의  
 에 대 한 인수는 `HMENU` 생성자 변환 하지 않고 직접 저장 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)

