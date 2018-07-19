---
title: _U_MENUorID 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0f945766283fa6e58b1eb3430cc780b1ae136e9f
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884739"
---
# <a name="umenuorid-class"></a>_U_MENUorID 클래스
이 클래스에 대 한 래퍼를 제공 `CreateWindow` 고 `CreateWindowEx`입니다.  
  
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
|[_U_MENUorID::m_hMenu](#_u_menuorid__m_hmenu)|메뉴 핸들입니다.|  
  
## <a name="remarks"></a>설명  
 이 인수 어댑터 클래스 부분 호출자 Id (UINTs) 또는 메뉴 핸들의 명시적 캐스트가 필요 없이 함수에 전달할 (HMENUs)를 허용 합니다.  
  
 이 클래스는 Windows API에 대 한 래퍼를 구현 하는 것에 대 한 설계 되었습니다 특히 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) 하 고 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) 자식 창이 될 수 있는 HMENU 인수를 사용할 모두 함수 식별자 (단위) 대신 메뉴 핸들입니다. 매개 변수로 사용 하 여가이 클래스를 볼 수는 예를 들어 [CWindowImpl::Create](cwindowimpl-class.md#create)합니다.  

  
 클래스는 두 개의 생성자 오버 로드를 정의 합니다: 하나 UINT 인수를 받아서 다른 HMENU 인수를 허용 합니다. UINT 인수 생성자 및 클래스의 단일 데이터 멤버에 저장 된 결과 HMENU 캐스팅할 방금 [m_hMenu](#_u_menuorid__m_hmenu)합니다. HMENU 생성자의 인수는 변환 없이 직접 저장 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  
  
##  <a name="_u_menuorid__m_hmenu"></a>  _U_MENUorID::m_hMenu  
 클래스는 공용 HMENU 데이터 멤버와 해당 생성자 중 하나에 전달 된 값을 보유 합니다.  
  
```
HMENU m_hMenu;
```  
  
##  <a name="_u_menuorid___u_menuorid"></a>  _U_MENUorID::_U_MENUorID  
 UINT 인수 생성자 및 클래스의 단일 데이터 멤버에 저장 된 결과 HMENU 캐스팅할 방금 [m_hMenu](#_u_menuorid__m_hmenu)합니다.  
  
```
_U_MENUorID(UINT nID);  
_U_MENUorID(HMENU hMenu);
```  
  
### <a name="parameters"></a>매개 변수  
 *nID*  
 자식 창 식별자입니다.  
  
 *hMenu*  
 메뉴 핸들입니다.  
  
### <a name="remarks"></a>설명  
 HMENU 생성자의 인수는 변환 없이 직접 저장 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)
