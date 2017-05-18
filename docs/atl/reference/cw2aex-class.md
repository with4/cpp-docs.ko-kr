---
title: "CW2AEX 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CW2AEX
- ATLCONV/ATL::CW2AEX
- ATLCONV/ATL::CW2AEX::CW2AEX
- ATLCONV/ATL::CW2AEX::m_psz
- ATLCONV/ATL::CW2AEX::m_szBuffer
dev_langs:
- C++
helpviewer_keywords:
- CW2AEX class
ms.assetid: 44dc2cf5-dd30-440b-a9b9-b21b43f49843
caps.latest.revision: 21
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 007dc4a40f0784984981c9b2741ec79ce6f12d9b
ms.contentlocale: ko-kr
ms.lasthandoff: 03/31/2017

---
# <a name="cw2aex-class"></a>CW2AEX 클래스
이 클래스는 문자열 변환 매크로 사용 `CT2AEX`, `CW2TEX`, `CW2CTEX`, 및 `CT2CAEX`, 및 typedef **CW2A**합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<int t_nBufferLength = 128>  
class CW2AEX
```  
  
#### <a name="parameters"></a>매개 변수  
 `t_nBufferLength`  
 변환 프로세스에서 사용 되는 버퍼의 크기입니다. 기본 길이 128 바이트입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CW2AEX::CW2AEX](#cw2aex)|생성자입니다.|  
|[CW2AEX:: ~ CW2AEX](#dtor)|소멸자입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[LPSTR CW2AEX::operator](#operator_lpstr)|변환 연산자입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CW2AEX::m_psz](#m_psz)|소스 문자열을 저장 하는 데이터 멤버입니다.|  
|[CW2AEX::m_szBuffer](#m_szbuffer)|변환된 된 문자열을 저장 하는 데 정적 버퍼입니다.|  
  
## <a name="remarks"></a>주의  
 추가 기능은 필요 하지 않는 한 사용할 `CT2AEX`, `CW2TEX`, `CW2CTEX`, `CT2CAEX`, 또는 **CW2A** 코드에서입니다.  
  
 이 클래스는 변환의 결과 저장 하는 데 사용 되는 고정 크기 정적 버퍼를 포함 합니다. 결과가 너무 커서 정적 버퍼에 포함할 수 없는 경우 클래스는 `malloc`를 사용하여 메모리를 할당함으로써 개체가 범위를 벗어나면 메모리를 해제합니다. 이렇게 하면, 텍스트와 달리이 클래스는 루프에서 사용 하기에 안전 하 고 있는지 스택이 오버플로되지 않습니다 것 ATL의 이전 버전에서 사용할 수 있는 변환 매크로입니다.  
  
 클래스를 힙 및 실패에 대 한 메모리를 할당 하려고 하는 경우 호출 됩니다 `AtlThrow` 의 인수와 함께 **E_OUTOFMEMORY**합니다.  
  
 기본적으로 ATL 변환 클래스와 매크로 현재 스레드의 ANSI 코드 페이지로 변환 하는 데 사용 합니다. 특정 변환에 대 한 해당 동작을 재정의 하려는 경우 클래스에 대 한 생성자에 대 한 두 번째 매개 변수로 코드 페이지를 지정 합니다.  
  
 다음 매크로이 클래스에 따라 결정 됩니다.  
  
- `CT2AEX`  
  
- `CW2TEX`  
  
- `CW2CTEX`  
  
- `CT2CAEX`  
  
 다음 typedef에는이 클래스를 기반으로 합니다.  
  
- **CW2A**  
  
 이러한 텍스트 변환 매크로의 논의 알려면 [ATL 및 MFC 문자열 변환 매크로](string-conversion-macros.md)합니다.  
  
## <a name="example"></a>예제  
 참조 [ATL 및 MFC 문자열 변환 매크로](string-conversion-macros.md) 이러한 문자열 변환 매크로 사용의 예입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlconv.h  
  
##  <a name="cw2aex"></a>CW2AEX::CW2AEX  
 생성자입니다.  
  
```
CW2AEX(LPCWSTR psz, UINT nCodePage) throw(...);  
CW2AEX(LPCWSTR psz) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `psz`  
 변환할 텍스트 문자열입니다.  
  
 `nCodePage`  
 코드 페이지 변환을 수행 하는 데 사용 합니다. 코드 페이지 매개 변수 설명에 대 한 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 함수 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072) 자세한 세부 정보에 대 한 합니다.  
  
### <a name="remarks"></a>주의  
 변환 프로세스에서 사용 되는 버퍼를 할당 합니다.  
  
##  <a name="dtor"></a>CW2AEX:: ~ CW2AEX  
 소멸자입니다.  
  
```
~CW2AEX() throw();
```  
  
### <a name="remarks"></a>주의  
 할당된 된 버퍼를 해제합니다.  
  
##  <a name="m_psz"></a>CW2AEX::m_psz  
 소스 문자열을 저장 하는 데이터 멤버입니다.  
  
```
LPSTR m_psz;
```  
  
##  <a name="m_szbuffer"></a>CW2AEX::m_szBuffer  
 변환된 된 문자열을 저장 하는 데 정적 버퍼입니다.  
  
```
char m_szBuffer[t_nBufferLength];
```  
  
##  <a name="operator_lpstr"></a>LPSTR CW2AEX::operator  
 변환 연산자입니다.  
  
```  
operator LPSTR() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 텍스트 문자열 형식으로 반환 **LPSTR 합니다.**  
  
## <a name="see-also"></a>참고 항목  
 [CA2AEX 클래스](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX 클래스](../../atl/reference/ca2caex-class.md)   
 [CA2WEX 클래스](../../atl/reference/ca2wex-class.md)   
 [CW2CWEX 클래스](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX 클래스](../../atl/reference/cw2wex-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

