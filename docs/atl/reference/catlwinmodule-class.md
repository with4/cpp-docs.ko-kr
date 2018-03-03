---
title: "CAtlWinModule 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dcaf3d6573432b7f6f16826b2551a7e9330abed9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="catlwinmodule-class"></a>CAtlWinModule 클래스
이 클래스는 ATL windowing 구성 요소에 대 한 지원을 제공합니다.  
  
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
|[CAtlWinModule::ExtractCreateWndData](#extractcreatewnddata)|Window 모듈 데이터 개체에 대 한 포인터를 반환합니다.|  
  
## <a name="remarks"></a>설명  
 이 클래스는 창 작업 기능을 필요로 하는 모든 ATL 클래스에 대 한 지원을 제공 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)  
  
 `CAtlWinModule`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="addcreatewnddata"></a>CAtlWinModule::AddCreateWndData  
 이 메서드를 초기화 하 고 추가 `_AtlCreateWndData` 구조입니다.  
  
```
void AddCreateWndData(_AtlCreateWndData* pData, void* pObject);
```  
  
### <a name="parameters"></a>매개 변수  
 `pData`  
 에 대 한 포인터는 `_AtlCreateWndData` 구조를 초기화 하 고 현재 모듈에 추가 합니다.  
  
 `pObject`  
 개체의에 대 한 포인터 **이** 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 호출 [AtlWinModuleAddCreateWndData](winmodule-global-functions.md#atlwinmoduleaddcreatewnddata) 어떤 초기화는 [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) 구조입니다. 이 구조는 저장 된 **이** 창 프로시저의 클래스 인스턴스를 가져오는 데 포인터입니다.  
  
##  <a name="catlwinmodule"></a>CAtlWinModule::CAtlWinModule  
 생성자입니다.  
  
```
CAtlWinModule();
```  
  
### <a name="remarks"></a>설명  
 초기화에 실패 하면는 **EXCEPTION_NONCONTINUABLE** 예외가 발생 합니다.  
  
##  <a name="dtor"></a>CAtlWinModule:: ~ CAtlWinModule  
 소멸자입니다.  
  
```
~CAtlWinModule();
```  
  
### <a name="remarks"></a>설명  
 할당 된 모든 리소스를 해제합니다.  
  
##  <a name="extractcreatewnddata"></a>CAtlWinModule::ExtractCreateWndData  
 이 메서드가 반환에 대 한 포인터는 `_AtlCreateWndData` 구조입니다.  
  
```
void* ExtractCreateWndData();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터를 반환 합니다.는 `_AtlCreateWndData` 구조와 이전에 추가한 [CAtlWinModule::AddCreateWndData](#addcreatewnddata), 또는 개체가 사용할 수 없으면 NULL입니다.  
  
## <a name="see-also"></a>참고 항목  
 [_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)   
 [클래스 개요](../../atl/atl-class-overview.md)   
 [모듈 클래스](../../atl/atl-module-classes.md)
