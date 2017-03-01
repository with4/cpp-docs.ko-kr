---
title: "IRegistrar 인터페이스 | Microsoft 문서"
ms.custom: 
ms.date: 2/1/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::IRegistrar
- IRegistrar
dev_langs:
- C++
helpviewer_keywords:
- Iregistrar Interface
ms.assetid: e88c04b7-0c93-4ae8-aeb9-ecd78f87421e
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
ms.sourcegitcommit: 199cdfd91a7d1b9882b57118c852352f6fdda43e
ms.openlocfilehash: e73e095d253d5ec5ca53e4e446019b2da79e5d39
ms.lasthandoff: 02/24/2017

---
# <a name="iregistrar-interface"></a>IRegistrar 인터페이스
이 인터페이스는 atliface.h에서 정의 되며 내부적으로 사용 됩니다 CAtlModule 멤버 함수에 의해 같은 [UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced)합니다.   
  
## <a name="syntax"></a>구문  
  
```
typedef interface IRegistrar IRegistrar;
```  
## <a name="remarks"></a>주의
항목을 참조 하십시오 [를 사용 하 여 대체 가능 매개 변수 (The 등록자 전처리기)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) 대 한 자세한 내용은 합니다.  

## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IRegistrar::ResourceRegisterSz](#resourceregistersz)|리소스를 등록합니다. |  
|[IRegistrar::ResourceUnregisterSz](#resourceunregistersz)| 리소스를 등록 취소합니다.|  
|[IRegistrar::FileRegister](#fileregister)|파일을 등록합니다.|  
|[IRegistrar::FileUnregister](#fileunregister)|파일을 등록 취소합니다.|  
|[IRegistrar::StringRegister](#stringregister)|문자열을 등록합니다.|  
|[IRegistrar::StringUnregister](#stringunregister)|문자열을 등록 취소|  
|[IRegistrar::ResourceRegister](#resourceregister)|리소스를 등록합니다.|  
|[IRegistrar::ResourceUnregister](#resourceunregister)|리소스를 등록 취소합니다.| 
  

 
## <a name="requirements"></a>요구 사항  
 **헤더:** atlifase.h  
  
##  <a name="a-nameresourceregistersza--iregistrarresourceregistersz"></a><a name="resourceregistersz"></a>IRegistrar::ResourceRegisterSz 
 리소스를 등록합니다.  
  
```
virtual HRESULT STDMETHODCALLTYPE ResourceRegisterSz( 
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```  
  
 
  
##  <a name="a-nameresourceunregistersza--iregistrarresourceunregistersz"></a><a name="resourceunregistersz"></a>IRegistrar::ResourceUnregisterSz  
 리소스를 등록 취소합니다.
  
```
virtual HRESULT STDMETHODCALLTYPE ResourceUnregisterSz( 
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```  
  
  
##  <a name="a-namefileregistera--iregistrarfileregister"></a><a name="fileregister"></a>IRegistrar::FileRegister  
파일을 등록합니다.
  
```
virtual HRESULT STDMETHODCALLTYPE FileRegister( 
    /* [in] */ _In_z_ LPCOLESTR fileName) = 0;
```  
  
  
##  <a name="a-namefileunregistera--iregistrarfileunregister"></a><a name="fileunregister"></a>IRegistrar::FileUnregister  
파일을 등록 취소합니다.

```
virtual HRESULT STDMETHODCALLTYPE FileUnregister( 
    */ _In_z_ LPCOLESTR fileName) = 0;
```  
  
 
##  <a name="a-namestringregistera--iregistrarstringregister"></a><a name="stringregister"></a>IRegistrar::StringRegister  
  지정 된 문자열 데이터를 등록합니다.
```
virtual HRESULT STDMETHODCALLTYPE StringRegister( 
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```  
  
##  <a name="a-namestringunregistera--iregistrarstringunregister"></a><a name="stringunregister"></a>IRegistrar::StringUnregister
 지정 된 문자열 데이터를 등록 취소합니다.  
  
```
virtualHRESULT STDMETHODCALLTYPE StringUnregister( 
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```  

  
##  <a name="a-nameresourceregistera--iregistrarresourceregister"></a><a name="resourceregister"></a>IRegistrar::ResourceRegister  
 리소스를 등록합니다.  
  
```
virtual HRESULT STDMETHODCALLTYPE ResourceRegister( 
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```  
   
  
##  <a name="a-nameresourceunregistera--iregistrarresourceunregister"></a><a name="resourceunregister"></a>IRegistrar::ResourceUnregister  
 리소스를 등록 취소합니다.  
  
```
virtualHRESULT STDMETHODCALLTYPE ResourceUnregister( 
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0; 
```  
 
## <a name="see-also"></a>참고 항목  
 [대체 가능 매개 변수 (등록자 전처리기)를 사용 하 여](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)  
 [클래스 개요](../../atl/atl-class-overview.md)   
 [모듈 클래스](../../atl/atl-module-classes.md)   
 [레지스트리 구성 요소 (등록자)](../../atl/atl-registry-component-registrar.md)  

