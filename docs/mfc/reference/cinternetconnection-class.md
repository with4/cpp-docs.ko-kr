---
title: "CInternetConnection 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInternetConnection
- AFXINET/CInternetConnection
- AFXINET/CInternetConnection::CInternetConnection
- AFXINET/CInternetConnection::GetContext
- AFXINET/CInternetConnection::GetServerName
- AFXINET/CInternetConnection::GetSession
dev_langs:
- C++
helpviewer_keywords:
- asynchronous connections
- CInternetConnection class
- Internet connections
ms.assetid: 62a5d1c3-8471-4e36-a064-48831829b2a7
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 7f99562e0c6103fc3f46a7fe28f9d2f2efff0a01
ms.lasthandoff: 02/24/2017

---
# <a name="cinternetconnection-class"></a>CInternetConnection 클래스
인터넷 서버와의 연결을 관리합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CInternetConnection : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CInternetConnection::CInternetConnection](#cinternetconnection)|`CInternetConnection` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CInternetConnection::GetContext](#getcontext)|이 연결 개체에 대 한 컨텍스트 ID를 가져옵니다.|  
|[CInternetConnection::GetServerName](#getservername)|연결과 관련 된 서버의 이름을 가져옵니다.|  
|[CInternetConnection::GetSession](#getsession)|에 대 한 포인터를 가져옵니다는 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 연결과 관련 된 개체입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CInternetConnection::operator HINTERNET](#operator_hinternet)|인터넷 세션에 대 한 핸들입니다.|  
  
## <a name="remarks"></a>주의  
 MFC 클래스에 대 한 기본 클래스 [CFtpConnection](../../mfc/reference/cftpconnection-class.md), [CHttpConnection](../../mfc/reference/chttpconnection-class.md), 및 [CGopherConnection](../../mfc/reference/cgopherconnection-class.md)합니다. 이러한 각 클래스는 각 FTP, HTTP 또는 gopher 서버와 통신 하기 위한 추가 기능을 제공 합니다.  
  
 인터넷 서버와 직접 통신할 있어야는 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체 및 `CInternetConnection` 개체입니다.  
  
 WinInet 클래스가 작동 하는 방법에 대 한 자세한 내용은 문서를 참조 하십시오. [인터넷 WinInet를 사용한 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CInternetConnection`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxinet.h  
  
##  <a name="cinternetconnection"></a>CInternetConnection::CInternetConnection  
 이 멤버 함수를 호출 하는 경우는 `CInternetConnection` 개체가 만들어집니다.  
  
```  
CInternetConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>매개 변수  
 `pSession`  
 에 대 한 포인터는 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체입니다.  
  
 `pstrServer`  
 서버 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `nPort`  
 인터넷이이 연결의 포트를 식별 하는 번호입니다.  
  
 `dwContext`  
 에 대 한 컨텍스트 식별자는 `CInternetConnection` 개체입니다. 참조 **주의** 에 대 한 자세한 내용은 `dwContext`합니다.  
  
### <a name="remarks"></a>주의  
 절대로 호출 하지 않는 `CInternetConnection` 직접; 대신, 호출의 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 설정 하려는 연결 유형에 대 한 멤버 함수:  
  
- [Cinternetsession:: Getftpconnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)  
  
- [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)  
  
- [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection)  
  
 기본값 `dwContext` MFC를 통해 보내집니다는 `CInternetConnection`-파생 개체를는 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 만든 개체는 **InternetConnection**-파생 개체입니다. 기본값은 1;로 설정 하지만에 특정 컨텍스트 식별자가 명시적으로 지정할 수는 [CInternetSession](../../mfc/reference/cinternetsession-class.md#cinternetsession) 연결에 대 한 생성자입니다. 개체와는 모든 작업 해당 컨텍스트 ID와 가진 연결 됩니다. 컨텍스트 식별자에 반환 됩니다 [cinternetsession:: Onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 식별 되는 개체에 대 한 상태에 있습니다. 문서를 참조 하십시오 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 컨텍스트 식별자에 대 한 자세한 내용은 합니다.  
  
##  <a name="getcontext"></a>CInternetConnection::GetContext  
 이 세션에 대 한 컨텍스트 ID를 가져오려면이 함수를 호출 합니다.  
  
```  
DWORD_PTR GetContext() const;  
```  
  
### <a name="return-value"></a>반환 값  
 응용 프로그램에 할당 된 컨텍스트 id입니다.  
  
### <a name="remarks"></a>주의  
 에 컨텍스트 ID가 지정 된 원래 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 전파 `CInternetConnection`-및 [CInternetFile](../../mfc/reference/cinternetfile-class.md)-연결을 여는 함수에 대 한 호출에 다르게 지정 하지 않은 경우에 파생 클래스입니다. 컨텍스트 ID 장치와 연결 된 지정된 된 개체의 모든 작업에서 반환 된 작업의 상태 정보를 식별 [cinternetsession:: Onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)합니다.  
  
 방법에 대 한 자세한 내용은 **GetContext** 다른 WinInet 클래스에서 사용자 상태 정보를 제공 하는 문서를 참조 하십시오. [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 컨텍스트 식별자에 대 한 자세한 내용은 합니다.  
  
##  <a name="getservername"></a>CInternetConnection::GetServerName  
 이 인터넷 연결과 관련 된 서버 이름을 가져오려면이 함수를 호출 합니다.  
  
```  
CString GetServerName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 연결 개체는 작업할 서버의 이름입니다.  
  
##  <a name="getsession"></a>CInternetConnection::GetSession  
 이 멤버 함수에 대 한 단서를 호출 하는 `CInternetSession` 이 연결에 연관 된 개체입니다.  
  
```  
CInternetSession* GetSession() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 이 인터넷 연결 개체와 연결 된 개체입니다.  
  
##  <a name="operator_hinternet"></a>CInternetConnection::operator HINTERNET  
 이 연산자를 사용 하 여 현재 인터넷 세션에 대 한 API 수준 핸들을 가져올 수 있습니다.  
  
```  
operator HINTERNET() const;  
```  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)




