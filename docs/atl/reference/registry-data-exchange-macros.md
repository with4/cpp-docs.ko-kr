---
title: "레지스트리 데이터 교환 매크로 | Microsoft 문서"
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
helpviewer_keywords:
- RegistryDataExchange function, macros
ms.assetid: c1bc5e79-2307-43d2-9d10-3a62ffadf473
caps.latest.revision: 16
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: ee3c1d639ee4a6c6bd6cf26a8c59bb1a37a4fa02
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="registry-data-exchange-macros"></a>레지스트리 데이터 교환 매크로
이러한 매크로 레지스트리 데이터 교환 작업을 수행 합니다.  
  
|||  
|-|-|  
|[BEGIN_RDX_MAP](#begin_rdx_map)|레지스트리 데이터 교환 구조의 시작 부분을 표시 합니다.|  
|[END_RDX_MAP](#end_rdx_map)|레지스트리 데이터 교환 맵의 끝을 표시 합니다.|  
|[RDX_BINARY](#rdx_binary)|바이트 형식의 지정 된 멤버 변수를 지정 된 레지스트리 항목을 연결합니다.|  
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|CString 형식의 지정 된 멤버 변수를 지정 된 레지스트리 항목을 연결합니다.|  
|[RDX_DWORD](#rdx_dword)|DWORD 형식의 지정 된 멤버 변수를 지정 된 레지스트리 항목을 연결합니다.|  
|[RDX_TEXT](#rdx_text)|TCHAR 형식의 지정 된 멤버 변수를 지정 된 레지스트리 항목을 연결합니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlplus.h  
   
##  <a name="begin_rdx_map"></a>BEGIN_RDX_MAP  
 레지스트리 데이터 교환 구조의 시작 부분을 표시 합니다.  
  
```
BEGIN_RDX_MAP
```  
  
### <a name="remarks"></a>주의  
 다음 매크로를 읽고 시스템 레지스트리에 있는 항목을 쓸 레지스트리 데이터 교환 구조 내에서 사용 됩니다.  
  
|매크로|설명|  
|-----------|-----------------|  
|[RDX_BINARY](#rdx_binary)|바이트 형식의 지정 된 멤버 변수를 지정 된 레지스트리 항목을 연결합니다.|  
|[RDX_DWORD](#rdx_dword)|DWORD 형식의 지정 된 멤버 변수를 지정 된 레지스트리 항목을 연결합니다.|  
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|CString 형식의 지정 된 멤버 변수를 지정 된 레지스트리 항목을 연결합니다.|  
|[RDX_TEXT](#rdx_text)|TCHAR 형식의 지정 된 멤버 변수를 지정 된 레지스트리 항목을 연결합니다.|  
  
 전역 함수 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), 또는에서 만든 동일한 이름의 멤버 함수는 `BEGIN_RDX_MAP` 및 `END_RDX_MAP` 코드는 시스템 레지스트리와 RDX 맵에 지정 된 변수는 데이터를 교환 해야 할 때마다 매크로 사용 해야 합니다.  
  
##  <a name="end_rdx_map"></a>END_RDX_MAP  
 레지스트리 데이터 교환 맵의 끝을 표시 합니다.  
  
```
END_RDX_MAP
```  
  
##  <a name="rdx_binary"></a>RDX_BINARY  
 바이트 형식의 지정 된 멤버 변수를 지정 된 레지스트리 항목을 연결합니다.  
  
```
RDX_BINARY(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>매개 변수  
 `rootkey`  
 레지스트리 키 루트입니다.  
  
 `subkey`  
 레지스트리 하위 키입니다.  
  
 `valuename`  
 레지스트리 키입니다.  
  
 `member`  
 멤버 변수를 지정 된 레지스트리 항목 연결입니다.  
  
 `member_size`  
 멤버 변수를 바이트 단위로 크기입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로와 함께 사용 되는 `BEGIN_RDX_MAP` 및 `END_RDX_MAP` 멤버 변수는 지정 된 레지스트리 항목에 연결 하는 매크로입니다. 전역 함수 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), 또는에서 만든 동일한 이름의 멤버 함수는 `BEGIN_RDX_MAP` 및 `END_RDX_MAP` RDX 맵에서 시스템 레지스트리와 멤버 변수 간의 데이터 교환을 수행 하 매크로 사용 해야 합니다.  
  
##  <a name="rdx_cstring_text"></a>RDX_CSTRING_TEXT  
 CString 형식의 지정 된 멤버 변수를 지정 된 레지스트리 항목을 연결합니다.  
  
```
RDX_CSTRING_TEXT(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>매개 변수  
 `rootkey`  
 레지스트리 키 루트입니다.  
  
 `subkey`  
 레지스트리 하위 키입니다.  
  
 `valuename`  
 레지스트리 키입니다.  
  
 `member`  
 멤버 변수를 지정 된 레지스트리 항목 연결입니다.  
  
 `member_size`  
 멤버 변수를 바이트 단위로 크기입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로와 함께 사용 되는 `BEGIN_RDX_MAP` 및 `END_RDX_MAP` 멤버 변수는 지정 된 레지스트리 항목에 연결 하는 매크로입니다. 전역 함수 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), 또는에서 만든 동일한 이름의 멤버 함수는 `BEGIN_RDX_MAP` 및 `END_RDX_MAP` RDX 맵에서 시스템 레지스트리와 멤버 변수 간의 데이터 교환을 수행 하 매크로 사용 해야 합니다.  
  
##  <a name="rdx_dword"></a>RDX_DWORD  
 DWORD 형식의 지정 된 멤버 변수를 지정 된 레지스트리 항목을 연결합니다.  
  
```
RDX_DWORD(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>매개 변수  
 `rootkey`  
 레지스트리 키 루트입니다.  
  
 `subkey`  
 레지스트리 하위 키입니다.  
  
 `valuename`  
 레지스트리 키입니다.  
  
 `member`  
 멤버 변수를 지정 된 레지스트리 항목 연결입니다.  
  
 `member_size`  
 멤버 변수를 바이트 단위로 크기입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로와 함께 사용 되는 `BEGIN_RDX_MAP` 및 `END_RDX_MAP` 멤버 변수는 지정 된 레지스트리 항목에 연결 하는 매크로입니다. 전역 함수 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), 또는에서 만든 동일한 이름의 멤버 함수는 `BEGIN_RDX_MAP` 및 `END_RDX_MAP` RDX 맵에서 시스템 레지스트리와 멤버 변수 간의 데이터 교환을 수행 하 매크로 사용 해야 합니다.  
  
##  <a name="rdx_text"></a>RDX_TEXT  
 TCHAR 형식의 지정 된 멤버 변수를 지정 된 레지스트리 항목을 연결합니다.  
  
```
RDX_TEXT(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>매개 변수  
 `rootkey`  
 레지스트리 키 루트입니다.  
  
 `subkey`  
 레지스트리 하위 키입니다.  
  
 `valuename`  
 레지스트리 키입니다.  
  
 `member`  
 멤버 변수를 지정 된 레지스트리 항목 연결입니다.  
  
 `member_size`  
 멤버 변수를 바이트 단위로 크기입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로와 함께 사용 되는 `BEGIN_RDX_MAP` 및 `END_RDX_MAP` 멤버 변수는 지정 된 레지스트리 항목에 연결 하는 매크로입니다. 전역 함수 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), 또는에서 만든 동일한 이름의 멤버 함수는 `BEGIN_RDX_MAP` 및 `END_RDX_MAP` RDX 맵에서 시스템 레지스트리와 멤버 변수 간의 데이터 교환을 수행 하 매크로 사용 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [매크로](../../atl/reference/atl-macros.md)   
 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)








