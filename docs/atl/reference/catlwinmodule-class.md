---
title: "CAtlWinModule 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlWinModule
- ATLBASE/ATL::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::AddCreateWndData
- ATLBASE/ATL::CAtlWinModule::ExtractCreateWndData
dev_langs:
- C++
helpviewer_keywords:
- CAtlWinModule class
ms.assetid: 7ec844af-0f68-4a34-b0c8-9de50a025df0
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 6db3ae9e610605524683e984f2aba602b1daf0d4
ms.lasthandoff: 02/24/2017

---
# <a name="catlwinmodule-class"></a>CAtlWinModule 클래스
이 클래스는 ATL 기간 이동 구성 요소에 대 한 지원을 제공합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CAtlWinModule : public _ATL_WIN_MODULE
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlWinModule::CAtlWinModule](#catlwinmodule)|생성자입니다.|  
|[CAtlWinModule:: ~ CAtlWinModule](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlWinModule::AddCreateWndData](#addcreatewnddata)|데이터 개체를 추가합니다.|  
|[CAtlWinModule::ExtractCreateWndData](#extractcreatewnddata)|창 모듈 데이터 개체에 대 한 포인터를 반환합니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스는 창 작업 기능에 필요한 모든 ATL 클래스에 대 한 지원을 제공 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)  
  
 `CAtlWinModule`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="addcreatewnddata"></a>CAtlWinModule::AddCreateWndData  
 이 메서드를 초기화 하 고 추가 하는 `_AtlCreateWndData` 구조입니다.  
  
```
void AddCreateWndData(_AtlCreateWndData* pData, void* pObject);
```  
  
### <a name="parameters"></a>매개 변수  
 `pData`  
 에 대 한 포인터는 `_AtlCreateWndData` 구조를 초기화 하 고 현재 모듈에 추가 합니다.  
  
 `pObject`  
 개체의 포인터 **이** 포인터입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 호출 [AtlWinModuleAddCreateWndData](http://msdn.microsoft.com/library/8463a6ed-07ea-4aad-92ec-ded681601b32) 어떤 초기화는 [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) 구조입니다. 이 구조를 저장할는 **이** 포인터, 창 프로시저에서 클래스 인스턴스를 가져오는 데 사용 합니다.  
  
##  <a name="catlwinmodule"></a>CAtlWinModule::CAtlWinModule  
 생성자입니다.  
  
```
CAtlWinModule();
```  
  
### <a name="remarks"></a>주의  
 초기화에 실패 하면는 **EXCEPTION_NONCONTINUABLE** 예외가 발생 합니다.  
  
##  <a name="dtor"></a>CAtlWinModule:: ~ CAtlWinModule  
 소멸자입니다.  
  
```
~CAtlWinModule();
```  
  
### <a name="remarks"></a>주의  
 할당 된 모든 리소스를 해제합니다.  
  
##  <a name="extractcreatewnddata"></a>CAtlWinModule::ExtractCreateWndData  
 이 메서드가 반환에 대 한 포인터는 `_AtlCreateWndData` 구조입니다.  
  
```
void* ExtractCreateWndData();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터를 반환 합니다.는 `_AtlCreateWndData` 구조와 이전에 추가한 [CAtlWinModule::AddCreateWndData](#addcreatewnddata), 또는 개체가 없으면 NULL입니다.  
  
## <a name="see-also"></a>참고 항목  
 [_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)   
 [클래스 개요](../../atl/atl-class-overview.md)   
 [모듈 클래스](../../atl/atl-module-classes.md)

