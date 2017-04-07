---
title: "CInternetException 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInternetException
- AFXINET/CInternetException
- AFXINET/CInternetException::CInternetException
- AFXINET/CInternetException::m_dwContext
- AFXINET/CInternetException::m_dwError
dev_langs:
- C++
helpviewer_keywords:
- exception handling, Internet operations
- exceptions, Internet
- CInternetException class
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
caps.latest.revision: 22
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: a128095cfc443f0ea8de4cb4028b903929a83f47
ms.lasthandoff: 02/24/2017

---
# <a name="cinternetexception-class"></a>CInternetException 클래스
인터넷 작업과 관련된 예외 상태를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CInternetException : public CException  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CInternetException::CInternetException](#cinternetexception)|`CInternetException` 개체를 생성합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CInternetException::m_dwContext](#m_dwcontext)|예외를 발생 시킨 작업과 연결 된 컨텍스트 값입니다.|  
|[CInternetException::m_dwError](#m_dwerror)|예외를 발생 시킨 오류입니다.|  
  
## <a name="remarks"></a>주의  
 `CInternetException` 클래스는 두 명의 공용 데이터 멤버를 포함 합니다: 하나는 예외와 관련 된 오류 코드를 보유 하 고 다른 식이 오류와 연결 된 인터넷 응용 프로그램의 컨텍스트 식별자입니다.  
  
 인터넷 응용 프로그램에 대 한 컨텍스트 식별자에 대 한 자세한 내용은 문서를 참조 하십시오. [인터넷 WinInet를 사용한 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CInternetException`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxinet.h  
  
##  <a name="cinternetexception"></a>CInternetException::CInternetException  
 이 멤버 함수를 호출 하는 경우는 `CInternetException` 개체가 만들어집니다.  
  
```  
CInternetException(DWORD dwError);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwError`  
 예외를 발생 시킨 오류입니다.  
  
### <a name="remarks"></a>주의  
 CInternetException를 throw 하려면 MFC 전역 함수를 호출 [AfxThrowInternetException](http://msdn.microsoft.com/library/c9645b10-9541-48b2-8b0c-94ca33fed3cb)합니다.  
  
##  <a name="m_dwcontext"></a>CInternetException::m_dwContext  
 인터넷 작업과 관련 된 연결 된 컨텍스트 값입니다.  
  
```  
DWORD_PTR m_dwContext;  
```  
  
### <a name="remarks"></a>주의  
 컨텍스트 식별자에 원래 지정 된 [CInternetSession](../../mfc/reference/cinternetsession-class.md) MFC로 전달 하 고 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)-및 [CInternetFile](../../mfc/reference/cinternetfile-class.md)-클래스를 파생 합니다. 이 기본값을 재정의 하 고 할당 `dwContext` 매개 변수 값을 선택 합니다. `dwContext`지정된 된 개체의 모든 작업과 연결 됩니다. `dwContext`반환 된 작업의 상태 정보를 식별 [cinternetsession:: Onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)합니다.  
  
##  <a name="m_dwerror"></a>CInternetException::m_dwError  
 예외를 발생 시킨 오류입니다.  
  
```  
DWORD m_dwError;  
```  
  
### <a name="remarks"></a>주의  
 오류 값이는 시스템 수 WINERROR에서 발견 되는 오류 코드입니다. H 또는 WININET에서 오류 값입니다.&8;.  
  
 Win32 오류 코드 목록은 참조 하십시오. [오류 코드](http://msdn.microsoft.com/library/windows/desktop/ms681381)합니다. 인터넷 관련 오류 메시지 목록은 다음을 참조 합니다. 에 있는 두 항목에는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CException 클래스](../../mfc/reference/cexception-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CException 클래스](../../mfc/reference/cexception-class.md)

