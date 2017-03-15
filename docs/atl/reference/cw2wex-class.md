---
title: "CW2WEX 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CW2WEX
- ATL.CW2WEX<t_nBufferLength>
- ATL::CW2WEX
- ATL.CW2WEX
- ATL::CW2WEX<t_nBufferLength>
dev_langs:
- C++
helpviewer_keywords:
- CW2WEX class
ms.assetid: 46262e56-e0d2-41fe-855b-0b67ecc8fcd7
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
ms.openlocfilehash: 9382f8404c1469b3f847500f35ab26499b6579bc
ms.lasthandoff: 02/24/2017

---
# <a name="cw2wex-class"></a>CW2WEX 클래스
이 클래스는 문자열 변환 매크로에서 사용 됩니다 `CW2TEX` 및 `CT2WEX`, 및 typedef `CW2W`합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <int t_nBufferLength = 128>  
class CW2WEX
```  
  
#### <a name="parameters"></a>매개 변수  
 `t_nBufferLength`  
 변환 프로세스에서 사용 되는 버퍼의 크기입니다. 기본 길이 128 바이트입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CW2WEX::CW2WEX](#cw2wex)|생성자입니다.|  
|[CW2WEX:: ~ CW2WEX](#dtor)|소멸자입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CW2WEX::operator LPWSTR](#operator_lpwstr)|변환 연산자입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CW2WEX::m_psz](#m_psz)|소스 문자열을 저장 하는 데이터 멤버입니다.|  
|[CW2WEX::m_szBuffer](#m_szbuffer)|변환된 된 문자열을 저장 하는 데 정적 버퍼입니다.|  
  
## <a name="remarks"></a>주의  
 추가 기능은 필요 하지 않으면 사용 `CW2TEX`, `CT2WEX`, 또는 `CW2W` 코드에 있습니다.  
  
 이 클래스는 변환의 결과 저장 하는 데 사용 되는 고정 크기 정적 버퍼를 포함 합니다. 결과가 너무 커서 정적 버퍼에 포함할 수 없는 경우 클래스는 `malloc`를 사용하여 메모리를 할당함으로써 개체가 범위를 벗어나면 메모리를 해제합니다. 이렇게 하면, 텍스트와 달리이 클래스는 루프에서 사용 하기에 안전 하 고 스택에 오버플로가 발생 하지 않습니다 ATL의 이전 버전에서 사용할 수 있는 변환 매크로입니다.  
  
 호출을 클래스 힙 및 실패에 대 한 메모리를 할당 하려고 하면 `AtlThrow` 의 인수와 함께 **E_OUTOFMEMORY**합니다.  
  
 기본적으로 ATL 변환 클래스와 매크로 변환에 대 한 현재 스레드의 ANSI 코드 페이지 사용.  
  
 다음 매크로이 클래스를 기반으로 합니다.  
  
- `CW2TEX`  
  
- `CT2WEX`  
  
 다음 형식 정의이 클래스를 기반으로 합니다.  
  
- `CW2W`  
  
 이러한 텍스트 변환 매크로의 논의 참조 하십시오. [ATL 및 MFC 문자열 변환 매크로](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863)합니다.  
  
## <a name="example"></a>예제  
 참조 [ATL 및 MFC 문자열 변환 매크로](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863) 이러한 문자열 변환 매크로 사용의 예입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlconv.h  
  
##  <a name="a-namecw2wexa--cw2wexcw2wex"></a><a name="cw2wex"></a>CW2WEX::CW2WEX  
 생성자입니다.  
  
```
CW2WEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2WEX( LPCWSTR  psz) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `psz`  
 변환할 텍스트 문자열입니다.  
  
 `nCodePage`  
 코드 페이지입니다. 이 클래스에서 사용 되지 않습니다.  
  
### <a name="remarks"></a>주의  
 번역에 필요한 버퍼를 만듭니다.  
  
##  <a name="a-namedtora--cw2wexcw2wex"></a><a name="dtor"></a>CW2WEX:: ~ CW2WEX  
 소멸자가...  
  
```
~CW2WEX() throw();
```  
  
### <a name="remarks"></a>주의  
 할당된 된 버퍼를 해제합니다.  
  
##  <a name="a-namempsza--cw2wexmpsz"></a><a name="m_psz"></a>CW2WEX::m_psz  
 소스 문자열을 저장 하는 데이터 멤버입니다.  
  
```
LPWSTR m_psz;
```  
  
##  <a name="a-namemszbuffera--cw2wexmszbuffer"></a><a name="m_szbuffer"></a>CW2WEX::m_szBuffer  
 변환된 된 문자열을 저장 하는 데 정적 버퍼입니다.  
  
```
wchar_t m_szBuffer[t_nBufferLength];
```  
  
##  <a name="a-nameoperatorlpwstra--cw2wexoperator-lpwstr"></a><a name="operator_lpwstr"></a>CW2WEX::operator LPWSTR  
 캐스트 연산자입니다.  
  
```  
operator LPWSTR() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 텍스트 문자열 형식으로 반환 `LPWSTR`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CA2AEX 클래스](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX 클래스](../../atl/reference/ca2caex-class.md)   
 [CA2WEX 클래스](../../atl/reference/ca2wex-class.md)   
 [CW2AEX 클래스](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX 클래스](../../atl/reference/cw2cwex-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

