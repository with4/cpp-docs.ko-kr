---
title: "_U_STRINGorID 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL._U_STRINGorID
- ATL::_U_STRINGorID
- _U_STRINGorID
dev_langs:
- C++
helpviewer_keywords:
- _U_STRINGorID class
- U_STRINGorID class
ms.assetid: 443cdc00-d265-4b27-8ef3-2feb95f3e5e3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ebc1b8f65f2a0841baf09b5c95528f571f97ce38
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ustringorid-class"></a>_U_STRINGorID 클래스
이 인수 어댑터 클래스 리소스 이름 중 하나를 사용 하면 ( `LPCTSTR`s) 또는 리소스 Id ( **UINT**s) 호출자 ID를 사용 하 여 문자열을 변환할 필요 없이 함수에 전달할는 **MAKEINTRESOURCE** 매크로입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class _U_STRINGorID
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[_U_STRINGorID::_U_STRINGorID](#_u_stringorid___u_stringorid)|생성자입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[_U_STRINGorID::m_lpstr](#_u_stringorid__m_lpstr)|리소스 식별자입니다.|  
  
## <a name="remarks"></a>설명  
 이 클래스와 같은 래퍼 Windows 리소스 관리 API 구현 용인지는 [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042), [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072), 및 [LoadMenu](http://msdn.microsoft.com/library/windows/desktop/ms647990) 수락 하는 함수 `LPCTSTR` 리소스의 이름 또는 ID 수 있는 인수  
  
 두 개의 생성자 오버 로드를 정의 하는 클래스: 허용 하나는 `LPCTSTR` 허용 되 고 다른 인수는 **UINT** 인수입니다. **UINT** 인수를 사용 하 여 리소스 관리 함수를 Windows와 호환 되는 리소스 종류에 변환 된 **MAKEINTRESOURCE** 매크로 해당 클래스의 단일 데이터 멤버에 저장 된 결과 [m_lpstr](#_u_stringorid__m_lpstr)합니다. 에 대 한 인수는 `LPCTSTR` 생성자는 변환 하지 않고 직접 저장 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  
  
##  <a name="_u_stringorid__m_lpstr"></a>_U_STRINGorID::m_lpstr  
 클래스를 공용 생성자 중 하나에 전달 된 값을 보유 `LPCTSTR` 데이터 멤버입니다.  
  
```
LPCTSTR m_lpstr;
```  
  
##  <a name="_u_stringorid___u_stringorid"></a>_U_STRINGorID::_U_STRINGorID  
 **UINT** 해당 인수를 사용 하 여 Windows 리소스 관리 기능와 호환 되는 리소스 종류를 변환 하는 생성자는 **MAKEINTRESOURCE** 클래스의 단일에 매크로 결과 저장 데이터 멤버 [m_lpstr](#_u_stringorid__m_lpstr)합니다.  
  
```
_U_STRINGorID(UINT nID);  
_U_STRINGorID(LPCTSTR lpString);
```  
  
### <a name="parameters"></a>매개 변수  
 `nID`  
 리소스 id입니다.  
  
 `lpString`  
 리소스 이름입니다.  
  
### <a name="remarks"></a>설명  
 에 대 한 인수는 `LPCTSTR` 생성자는 변환 하지 않고 직접 저장 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)
