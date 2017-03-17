---
title: "CW2CWEX 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CW2CWEX
- ATLCONV/ATL::CW2CWEX
- ATLCONV/ATL::CW2CWEX::CW2CWEX
- ATLCONV/ATL::CW2CWEX::m_psz
dev_langs:
- C++
helpviewer_keywords:
- CW2CWEX class
ms.assetid: d654b22b-05a6-410f-a0ec-9a2cbbb4cca7
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: a85b67a58553dada36f4472ea0683e18bc775493
ms.lasthandoff: 02/24/2017

---
# <a name="cw2cwex-class"></a>CW2CWEX 클래스
이 클래스는 문자열 변환 매크로에서 사용 됩니다 `CW2CTEX` 및 `CT2CWEX`, 및 typedef `CW2W`합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<int t_nBufferLength = 128>  
class CW2CWEX
```  
  
#### <a name="parameters"></a>매개 변수  
 `t_nBufferLength`  
 변환 프로세스에서 사용 되는 버퍼의 크기입니다. 기본 길이 128 바이트입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CW2CWEX::CW2CWEX](#cw2cwex)|생성자입니다.|  
|[CW2CWEX:: ~ CW2CWEX](#dtor)|소멸자입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CW2CWEX::operator LPCWSTR](#operator_lpcwstr)|변환 연산자입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CW2CWEX::m_psz](#m_psz)|소스 문자열을 저장 하는 데이터 멤버입니다.|  
  
## <a name="remarks"></a>주의  
 추가 기능은 필요 하지 않으면 사용 `CW2CTEX`, `CT2CWEX`, 또는 `CW2W` 코드에 있습니다.  
  
 이 클래스는 루프에서 사용 하 여 안전 하며 스택이 오버플로되지 않습니다. 기본적으로 ATL 변환 클래스와 매크로 변환에 대 한 현재 스레드의 ANSI 코드 페이지 사용.  
  
 다음 매크로이 클래스를 기반으로 합니다.  
  
- `CW2CTEX`  
  
- `CT2CWEX`  
  
 다음 형식 정의이 클래스를 기반으로 합니다.  
  
- `CW2W`  
  
 이러한 텍스트 변환 매크로의 논의 참조 하십시오. [ATL 및 MFC 문자열 변환 매크로](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863)합니다.  
  
## <a name="example"></a>예제  
 참조 [ATL 및 MFC 문자열 변환 매크로](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863) 이러한 문자열 변환 매크로 사용의 예입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlconv.h  
  
##  <a name="cw2cwex"></a>CW2CWEX::CW2CWEX  
 생성자입니다.  
  
```
CW2CWEX(LPCWSTR psz, UINT nCodePage) throw(...);  
CW2CWEX(LPCWSTR psz) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `psz`  
 변환할 텍스트 문자열입니다.  
  
 `nCodePage`  
 코드 페이지입니다. 이 클래스에서 사용 되지 않습니다.  
  
### <a name="remarks"></a>주의  
 변환 프로세스에서 사용 되는 버퍼를 할당 합니다.  
  
##  <a name="dtor"></a>CW2CWEX:: ~ CW2CWEX  
 소멸자입니다.  
  
```
~CW2CWEX() throw();
```  
  
### <a name="remarks"></a>주의  
 할당된 된 버퍼를 해제합니다.  
  
##  <a name="m_psz"></a>CW2CWEX::m_psz  
 소스 문자열을 저장 하는 데이터 멤버입니다.  
  
```
LPCWSTR m_psz;
```  
  
##  <a name="operator_lpcwstr"></a>CW2CWEX::operator LPCWSTR  
 변환 연산자입니다.  
  
```  
operator LPCWSTR() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 텍스트 문자열 형식으로 반환 **LPCWSTR 합니다.**  
  
## <a name="see-also"></a>참고 항목  
 [CA2AEX 클래스](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX 클래스](../../atl/reference/ca2caex-class.md)   
 [CA2WEX 클래스](../../atl/reference/ca2wex-class.md)   
 [CW2AEX 클래스](../../atl/reference/cw2aex-class.md)   
 [CW2WEX 클래스](../../atl/reference/cw2wex-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

