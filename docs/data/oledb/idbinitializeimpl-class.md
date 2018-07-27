---
title: IDBInitializeImpl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IDBInitializeImpl<T>
- ATL::IDBInitializeImpl<T>
- IDBInitializeImpl
- ATL::IDBInitializeImpl
- ATL.IDBInitializeImpl
- IDBInitializeImpl.IDBInitializeImpl
- IDBInitializeImpl
- IDBInitializeImpl::IDBInitializeImpl
- Initialize
- IDBInitializeImpl::Initialize
- IDBInitializeImpl.Initialize
- IDBInitializeImpl.Uninitialize
- Uninitialize
- IDBInitializeImpl::Uninitialize
- ATL::IDBInitializeImpl::m_dwStatus
- IDBInitializeImpl.m_dwStatus
- ATL.IDBInitializeImpl.m_dwStatus
- IDBInitializeImpl::m_dwStatus
- IDBInitializeImpl<T>::m_dwStatus
- ATL.IDBInitializeImpl<T>.m_dwStatus
- ATL::IDBInitializeImpl<T>::m_dwStatus
- m_dwStatus
- ATL::IDBInitializeImpl<T>::m_pCUtlPropInfo
- m_pCUtlPropInfo
- IDBInitializeImpl::m_pCUtlPropInfo
- ATL.IDBInitializeImpl.m_pCUtlPropInfo
- IDBInitializeImpl<T>::m_pCUtlPropInfo
- IDBInitializeImpl.m_pCUtlPropInfo
- ATL::IDBInitializeImpl::m_pCUtlPropInfo
dev_langs:
- C++
helpviewer_keywords:
- IDBInitializeImpl class
- IDBInitializeImpl constructor
- Initialize method
- Uninitialize method
- m_dwStatus
- m_pCUtlPropInfo
ms.assetid: e4182f81-0443-44f5-a0d3-e7e075d6f883
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 69c7f92110312d4ae8cff427d1081853290919e9
ms.sourcegitcommit: b0d6777cf4b580d093eaf6104d80a888706e7578
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2018
ms.locfileid: "39269926"
---
# <a name="idbinitializeimpl-class"></a>IDBInitializeImpl 클래스
에 대 한 구현을 제공 합니다 [IDBInitialize](https://msdn.microsoft.com/library/ms713706.aspx) 인터페이스입니다.  
  
## <a name="syntax"></a>구문

```cpp
template <class T>  
class ATL_NO_VTABLE IDBInitializeImpl : public IDBInitialize  
```  
  
### <a name="parameters"></a>매개 변수  
 *T*  
 클래스에서 파생 된 `IDBInitializeImpl`합니다.  

## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[IDBInitializeImpl](#idbinitializeimpl)|생성자입니다.|  
  
### <a name="interface-methods"></a>인터페이스 메서드  
  
|||  
|-|-|  
|[Initialize](#initialize)|공급자를 시작합니다.|  
|[초기화](#uninitialize)|공급자를 중지합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|||  
|-|-|  
|[m_dwStatus](#dwstatus)|데이터 원본 플래그입니다.|  
|[m_pCUtlPropInfo](#pcutlpropinfo)|DB 속성 정보는 구현에 대 한 포인터입니다.|  
  
## <a name="remarks"></a>설명  
 데이터 원본 개체에서 열거자의 선택적 인터페이스에는 필수 인터페이스입니다.  

## <a name="idbinitializeimpl"></a> Idbinitializeimpl:: Idbinitializeimpl
생성자입니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
IDBInitializeImpl();  
  
```  
  
### <a name="remarks"></a>설명  
 모든 데이터 멤버를 초기화합니다. 
  
## <a name="initialize"></a> Idbinitializeimpl:: Initialize
속성 지원을 준비하여 데이터 소스 개체를 초기화합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
      STDMETHOD(Initialize)(void);  
```  
  
### <a name="remarks"></a>설명  
 참조 [idbinitialize:: Initialize](https://msdn.microsoft.com/library/ms718026.aspx) 에 *OLE DB Programmer's Reference*합니다. 

## <a name="uninitialize"></a> Idbinitializeimpl:: Uninitialize
위치 데이터 원본 속성 지원과 같은 내부 리소스를 해제 하 여 초기화 되지 않은 상태로 개체입니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
      STDMETHOD(Uninitialize)(void);  
```  
  
### <a name="remarks"></a>설명  
 참조 [idbinitialize:: Uninitialize](https://msdn.microsoft.com/library/ms719648.aspx) 에 *OLE DB Programmer's Reference*합니다.

## <a name="dwstatus"></a> Idbinitializeimpl:: M_dwstatus
데이터 원본 플래그입니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
DWORD m_dwStatus;  
  
```  
  
### <a name="remarks"></a>설명  
 이러한 플래그를 지정 하거나 데이터 원본 개체에 대 한 다양 한 특성의 상태를 나타냅니다. 다음 중 하나 이상 포함 **enum** 값:  
  
```  
enum DATASOURCE_FLAGS {  
    DSF_MASK_INIT     = 0xFFFFF00F,  
    DSF_PERSIST_DIRTY = 0x00000001,  
    DSF_INITIALIZED   = 0x00000010,  
};  
```  
  
|||  
|-|-|  
|`DSF_MASK_INIT`|초기화 되지 않은 상태로의 복원을 사용할 수 있도록 하는 마스크입니다.|  
|`DSF_PERSIST_DIRTY`|데이터 원본 개체 (즉, 경우 변경 내용이 있었는지) 지 속성을 요구 하는 경우 설정 합니다.|  
|`DSF_INITIALIZED`|데이터 원본이 초기화 하는 경우 설정 합니다.|  

## <a name="pcutlpropinfo"></a> Idbinitializeimpl:: M_pcutlpropinfo
DB 속성 정보에 대 한 구현 개체에 대 한 포인터입니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
CUtlPropInfo<  
T  
>* m_pCUtlPropInfo;  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)
