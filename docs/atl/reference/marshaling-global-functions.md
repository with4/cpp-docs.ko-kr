---
title: "전역 함수 마샬링 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 877100b5-6ad9-44c5-a2e0-09414f1720d0
caps.latest.revision: 19
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: dd4b8d50ec69974b7b2af29438b1657e1ce592b4
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="marshaling-global-functions"></a>마샬링 전역 함수
이러한 함수는 마샬링 및 마샬링 데이터를 다른 인터페이스 포인터 변환에 대 한 지원을 제공 합니다.  
  
> [!IMPORTANT]
>  다음 표에 나열 된 함수에서 실행 되는 응용 프로그램에서 사용할 수 없습니다는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]합니다.  
  
|||  
|-|-|  
|[AtlFreeMarshalStream](#atlfreemarshalstream)|마샬링 데이터 해제 및 `IStream` 포인터입니다.|  
|[AtlMarshalPtrInProc](#atlmarshalptrinproc)|새 스트림 개체를 만들고 지정 된 인터페이스 포인터를 마샬링합니다.|  
|[AtlUnmarshalPtr](#atlunmarshalptr)|에 대 한 인터페이스 포인터를 스트림의 마샬링 데이터를 변환합니다.|  
  
##  <a name="atlfreemarshalstream"></a>AtlFreeMarshalStream  
 스트림에서 마샬링 데이터를 해제한 다음 스트림 포인터를 해제합니다.  

```
HRESULT AtlFreeMarshalStream(IStream* pStream);
```  
  
### <a name="parameters"></a>매개 변수  
 `pStream`  
 [in] 에 대 한 포인터는 `IStream` 마샬링하는 데 사용 되는 스트림 인터페이스입니다.  
  
### <a name="example"></a>예제  
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
 [in] 마샬링할 인터페이스에 대 한 포인터입니다.  
  
 `iid`  
 [in] 마샬링되고 인터페이스의 GUID입니다.  
  
 `ppStream`  
 [out] 에 대 한 포인터는 `IStream` 마샬링에 사용 되는 새 스트림 개체에 대 한 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>주의  
 **MSHLFLAGS_TABLESTRONG** 여러 스트림으로 포인터를 마샬링할 수 있도록 플래그가 설정 되어 있습니다. 포인터 수도 마샬링해야 할 여러 번입니다.  
  
 실패 하면 마샬링, 스트림 포인터가 해제 됩니다.  
  
 `AtlMarshalPtrInProc`처리 중인 개체에 대 한 포인터에만 사용할 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_COM&#50;](../../atl/codesnippet/cpp/marshaling-global-functions_1.cpp)]  
  
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
 [out] 역마샬링된 인터페이스에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [AtlMarshalPtrInProc](#atlmarshalptrinproc)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [함수](../../atl/reference/atl-functions.md)

