---
title: CSocketAddr 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSocketAddr
- ATLSOCKET/ATL::CSocketAddr
- ATLSOCKET/ATL::CSocketAddr::CSocketAddr
- ATLSOCKET/ATL::CSocketAddr::FindAddr
- ATLSOCKET/ATL::CSocketAddr::FindINET4Addr
- ATLSOCKET/ATL::CSocketAddr::FindINET6Addr
- ATLSOCKET/ATL::CSocketAddr::GetAddrInfo
- ATLSOCKET/ATL::CSocketAddr::GetAddrInfoList
dev_langs:
- C++
helpviewer_keywords:
- CSocketAddr class
ms.assetid: 2fb2d8a7-899e-4a36-a342-cc9f4fcdd68c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 830b1087d0a4792b449c516ed12ad7e8a84b2a51
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363398"
---
# <a name="csocketaddr-class"></a>CSocketAddr 클래스
이 클래스는 호스트 이름을 호스트 주소에 IPv4 및 IPV6 모두 형식을 지 원하는 변환 하기 위한 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
class CSocketAddr
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSocketAddr::CSocketAddr](#csocketaddr)|생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSocketAddr::FindAddr](#findaddr)|제공 된 호스트 이름을 호스트 주소를 변환 하려면이 메서드를 호출 합니다.|  
|[CSocketAddr::FindINET4Addr](#findinet4addr)|호스트 주소를 IPv4 호스트 이름으로 변환 하려면이 메서드를 호출 합니다.|  
|[CSocketAddr::FindINET6Addr](#findinet6addr)|IPv6 호스트 이름을 호스트 주소를 변환 하려면이 메서드를 호출 합니다.|  
|[CSocketAddr::GetAddrInfo](#getaddrinfo)|호출의 특정 요소에 대 한 포인터를 반환 하려면이 메서드는 **addrinfo** 목록입니다.|  
|[CSocketAddr::GetAddrInfoList](#getaddrinfolist)|호출에 대 한 포인터를 반환 하려면이 메서드는 **addrinfo** 목록입니다.|  
  
## <a name="remarks"></a>설명  
 이 클래스는 IP 버전 Windows와 함께 사용 하기 위해 네트워크 주소를 찾기 위한 중립적인 방식을 소켓 API 함수 및 라이브러리의 소켓 래퍼를 제공 합니다.  
  
 Win32 API 함수를 사용 하는 네트워크 주소를 조회 하는 데 사용 되는이 클래스의 멤버 [getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520)합니다.  
  
 이 클래스는 두 IPv4 andIPv6 네트워크 주소를 지원합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsocket.h  
  
##  <a name="csocketaddr"></a>  CSocketAddr::CSocketAddr  
 생성자입니다.  
  
```
CSocketAddr();
```  
  
### <a name="remarks"></a>설명  
 새 `CSocketAddr` 개체를 호스트 하는 방법에 대 한 응답 정보를 포함 하는 링크 된 목록의 초기화 합니다.  
  
##  <a name="findaddr"></a>  CSocketAddr::FindAddr  
 제공 된 호스트 이름을 호스트 주소를 변환 하려면이 메서드를 호출 합니다.  
  
```
int FindAddr(
    const char *szHost,
    const char *szPortOrServiceName,
    int flags,
    int addr_family,
    int sock_type,
    int ai_proto);

int FindAddr(
    const char *szHost,
    int nPortNo,
    int flags,
    int addr_family,
    int sock_type,
    int ai_proto);
```  
  
### <a name="parameters"></a>매개 변수  
 `szHost`  
 호스트 이름 또는 점으로 구분 된 IP 주소입니다.  
  
 *szPortOrServiceName*  
 포트 번호 또는 호스트에서 서비스의 이름입니다.  
  
 `nPortNo`  
 포트 번호입니다.  
  
 `flags`  
 0 또는 AI_PASSIVE, AI_CANONNAME 또는 AI_NUMERICHOST의 조합입니다.  
  
 *addr_family*  
 주소 집합 (예: PF_INET).  
  
 `sock_type`  
 (예: SOCK_STREAM) 소켓 유형입니다.  
  
 *ai_proto*  
 프로토콜 (예: IPPROTO_IP 또는 IPPROTO_IPV6)입니다.  
  
### <a name="return-value"></a>반환 값  
 주소는 성공적으로 계산 되는 경우 0을 반환 합니다. 실패 한 경우 0이 아닌 Windows 소켓 오류 코드를 반환합니다. 성공적으로 사용 하 여 참조 될 수 있는 연결 된 목록의 계산 된 주소를 저장 됩니다 `CSocketAddr::GetAddrInfoList` 및 `CSocketAddr::GetAddrInfo`합니다.  
  
### <a name="remarks"></a>설명  
 호스트 이름 매개 변수는 IPv4 또는 IPv6 형식 수 있습니다. 이 메서드는 Win32 API 함수를 호출 [getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520) 변환을 수행 하려고 합니다.  
  
##  <a name="findinet4addr"></a>  CSocketAddr::FindINET4Addr  
 호스트 주소를 IPv4 호스트 이름으로 변환 하려면이 메서드를 호출 합니다.  
  
```
int FindINET4Addr(
    const char *szHost,
    int nPortNo,
    int flags,
    int sock_type,);
```  
  
### <a name="parameters"></a>매개 변수  
 `szHost`  
 호스트 이름 또는 점으로 구분 된 IP 주소입니다.  
  
 `nPortNo`  
 포트 번호입니다.  
  
 `flags`  
 0 또는 AI_PASSIVE, AI_CANONNAME 또는 AI_NUMERICHOST의 조합입니다.  
  
 `sock_type`  
 (예: SOCK_STREAM) 소켓 유형입니다.  
  
### <a name="return-value"></a>반환 값  
 주소는 성공적으로 계산 되는 경우 0을 반환 합니다. 실패 한 경우 0이 아닌 Windows 소켓 오류 코드를 반환합니다. 성공적으로 사용 하 여 참조 될 수 있는 연결 된 목록의 계산 된 주소를 저장 됩니다 `CSocketAddr::GetAddrInfoList` 및 `CSocketAddr::GetAddrInfo`합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 Win32 API 함수를 호출 [getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520) 변환을 수행 하려고 합니다.  
  
##  <a name="findinet6addr"></a>  CSocketAddr::FindINET6Addr  
 IPv6 호스트 이름을 호스트 주소를 변환 하려면이 메서드를 호출 합니다.  
  
```
int FindINET6Addr(
    const char *szHost,
    int nPortNo,
    int flags,
    int sock_type,);
```  
  
### <a name="parameters"></a>매개 변수  
 `szHost`  
 호스트 이름 또는 점으로 구분 된 IP 주소입니다.  
  
 `nPortNo`  
 포트 번호입니다.  
  
 `flags`  
 0 또는 AI_PASSIVE, AI_CANONNAME 또는 AI_NUMERICHOST의 조합입니다.  
  
 `sock_type`  
 (예: SOCK_STREAM) 소켓 유형입니다.  
  
### <a name="return-value"></a>반환 값  
 주소는 성공적으로 계산 되는 경우 0을 반환 합니다. 실패 한 경우 0이 아닌 Windows 소켓 오류 코드를 반환합니다. 성공적으로 사용 하 여 참조 될 수 있는 연결 된 목록의 계산 된 주소를 저장 됩니다 `CSocketAddr::GetAddrInfoList` 및 `CSocketAddr::GetAddrInfo`합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 Win32 API 함수를 호출 [getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520) 변환을 수행 하려고 합니다.  
  
##  <a name="getaddrinfo"></a>  CSocketAddr::GetAddrInfo  
 호출의 특정 요소에 대 한 포인터를 반환 하려면이 메서드는 **addrinfo** 목록입니다.  
  
```
addrinfo* const GetAddrInfoint nIndex = 0) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 특정 요소에 대 한 참조는 [addrinfo](http://msdn.microsoft.com/library/windows/desktop/ms737530) 목록입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터를 반환 합니다.는 **addrinfo** 에서 참조 하는 구조 `nIndex` 호스트에 대 한 응답 정보를 포함 하는 연결 된 목록의 합니다.  
  
##  <a name="getaddrinfolist"></a>  CSocketAddr::GetAddrInfoList  
 호출에 대 한 포인터를 반환 하려면이 메서드는 **addrinfo** 목록입니다.  
  
```
addrinfo* const GetAddrInfoList() const;
```  
  
### <a name="return-value"></a>반환 값  
 하나 이상의 연결 된 목록에 대 한 포인터 `addrinfo` 호스트에 대 한 응답 정보를 포함 하는 구조체입니다. 자세한 내용은 참조 [addrinfo 구조](https://msdn.microsoft.com/library/windows/desktop/ms737530)합니다.
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)
