---
title: CAtlAutoThreadModuleT 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT::GetDefaultThreads
dev_langs:
- C++
helpviewer_keywords:
- CAtlAutoThreadModuleT class
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a54818b839f13ad9114274248cfdbfc74efa033a
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883075"
---
# <a name="catlautothreadmodulet-class"></a>CAtlAutoThreadModuleT 클래스
이 클래스는 스레드 풀링, 아파트 모델 COM 서버 구현에 대 한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T, 
         class ThreadAllocator = CComSimpleThreadAllocator,
         DWORD dwWait = INFINITE>  
class ATL_NO_VTABLE CAtlAutoThreadModuleT : public IAtlAutoThreadModule
```  
  
#### <a name="parameters"></a>매개 변수  
 *T*  
 COM 서버 구현 하는 클래스입니다.  
  
 *ThreadAllocator*  
 스레드 선택 영역을 관리 하는 클래스입니다. 기본값은 [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)합니다.  
  
 *dwWait*  
 시간 제한 간격을 밀리초 단위로 지정 합니다. 기본값은 메서드의 시간 제한 간격이 경과 없음을 의미 하는 무한 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlAutoThreadModuleT::GetDefaultThreads](#getdefaultthreads)|이 정적 함수는 동적으로 계산 하 고 프로세서의 수에 따라 EXE 모듈에 대 한 스레드의 최대 수를 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 클래스 [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) 에서 파생 `CAtlAutoThreadModuleT` 스레드 풀링, 아파트 모델 COM 서버를 구현 하기 위해. 사용 되지 않는 클래스 대체 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)합니다.  
  
> [!NOTE]
>  이 클래스 해서는 안 DLL에서 기본값으로 *dwWait* 무한 값 DLL을 언로드할 때 교착 상태가 발생 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IAtlAutoThreadModule`  
  
 `CAtlAutoThreadModuleT`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="getdefaultthreads"></a>  CAtlAutoThreadModuleT::GetDefaultThreads  
 이 정적 함수는 동적으로 계산 하 고 프로세서의 수에 따라 EXE 모듈에 대 한 스레드의 최대 수를 반환 합니다.  
  
```
static int GetDefaultThreads();
```  
  
### <a name="return-value"></a>반환 값  
 EXE 모듈에서 생성 될 스레드의 수입니다.  
  
### <a name="remarks"></a>설명  
 스레드 수를 계산 하기 위한 다른 메서드를 사용 하려는 경우이 메서드를 재정의 합니다. 기본적으로 스레드 수는 프로세서 수를 기반으로 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IAtlAutoThreadModule 클래스](../../atl/reference/iatlautothreadmodule-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)   
 [IAtlAutoThreadModule 클래스](../../atl/reference/iatlautothreadmodule-class.md)   
 [모듈 클래스](../../atl/atl-module-classes.md)
