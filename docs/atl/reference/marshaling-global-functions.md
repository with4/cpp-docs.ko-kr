---
title: "전역 함수 마샬링 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlFreeMarshalStream
- atlbase/ATL::AtlMarshalPtrInProc
- atlbase/ATL::AtlUnmarshalPtr
dev_langs:
- C++
ms.assetid: 877100b5-6ad9-44c5-a2e0-09414f1720d0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a12f719d2cb893a5d2989a80f5fe09a5b49aeca2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="marshaling-global-functions"></a>마샬링 전역 함수
이러한 함수는 마샬링 및 마샬링 데이터를 다른 인터페이스 포인터 변환에 대 한 지원을 제공 합니다.  
  
> [!IMPORTANT]
>  다음 표에 나열 된 함수는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
|||  
|-|-|  
|[AtlFreeMarshalStream](#atlfreemarshalstream)|마샬링 데이터를 해제 및 `IStream` 포인터입니다.|  
|[AtlMarshalPtrInProc](#atlmarshalptrinproc)|새 스트림 개체를 만들고 지정 된 인터페이스 포인터를 마샬링합니다.|  
|[AtlUnmarshalPtr](#atlunmarshalptr)|스트림의 마샬링 데이터를 인터페이스 포인터로 변환합니다.|  

## <a name="requirements"></a>요구 사항:
**헤더:** atlbase.h
  
##  <a name="atlfreemarshalstream"></a>AtlFreeMarshalStream  
 스트림에서 마샬링 데이터를 해제한 다음 스트림 포인터를 해제합니다.  

```
HRESULT AtlFreeMarshalStream(IStream* pStream);
```  
  
### <a name="parameters"></a>매개 변수  
 `pStream`  
 [in] 에 대 한 포인터는 `IStream` 마샬링하는 데 사용 되는 스트림 인터페이스입니다.  
  
### <a name="example"></a>예  
  예를 참조 [AtlMarshalPtrInProc](#atlmarshalptrinproc)합니다.  
  
##  <a name="atlmarshalptrinproc"></a>AtlMarshalPtrInProc  
 새 스트림 개체를 만들고, 프록시의 CLSID를 스트림에 쓰고, 프록시를 스트림으로 초기화하는 데 필요한 데이터를 작성하여 제공된 인터페이스 포인터를 마샬링합니다.  
  
```
HRESULT AtlMarshalPtrInProc(
    IUnknown* pUnk,
    const IID& iid,
    IStream** ppStream);
```  
  
### <a name="parameters"></a>매개 변수  
 *pUnk*  
 [in] 마샬링해야 하는 인터페이스에 대 한 포인터입니다.  
  
 `iid`  
 [in] 마샬링하 인터페이스의 GUID입니다.  
  
 `ppStream`  
 [out] 에 대 한 포인터는 `IStream` 마샬링에 사용 되는 새 스트림 개체에 대 한 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>설명  
 **MSHLFLAGS_TABLESTRONG** 플래그 설정 되므로 여러 스트림을에 포인터를 마샬링할 수 있습니다. 포인터 수 또한 마샬링해야 할 여러 번입니다.  
  
 실패 마샬링 스트림 포인터 해제 됩니다.  
  
 `AtlMarshalPtrInProc`처리 중인 개체에 대 한 포인터에만 사용할 수 있습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_COM#50](../../atl/codesnippet/cpp/marshaling-global-functions_1.cpp)]  
  
##  <a name="atlunmarshalptr"></a>AtlUnmarshalPtr  
 스트림의 마샬링 데이터를 클라이언트에서 사용할 수 있는 인터페이스 포인터로 변환합니다.  
   
```
HRESULT AtlUnmarshalPtr(
    IStream* pStream,
    const IID& iid,
    IUnknown** ppUnk);
```  
  
### <a name="parameters"></a>매개 변수  
 `pStream`  
 [in] 역마샬링 중인 스트림에 대 한 포인터입니다.  
  
 `iid`  
 [in] 역마샬링 되는 인터페이스의 GUID입니다.  
  
 `ppUnk`  
 [out] 마샬링할된 인터페이스에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="example"></a>예  
  예를 참조 [AtlMarshalPtrInProc](#atlmarshalptrinproc)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [함수](../../atl/reference/atl-functions.md)
