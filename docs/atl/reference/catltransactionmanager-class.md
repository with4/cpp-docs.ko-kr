---
title: "CAtlTransactionManager 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlTransactionManager
- atltransactionmanager/ATL::CAtlTransactionManager
dev_langs:
- C++
helpviewer_keywords:
- CAtlTransactionManager class
ms.assetid: b01732dc-1d16-4b42-bfac-b137fca2b740
caps.latest.revision: 25
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
ms.openlocfilehash: bc6162eaf1a4c8c3848a32e861019ff50e4f850c
ms.lasthandoff: 02/24/2017

---
# <a name="catltransactionmanager-class"></a>CAtlTransactionManager 클래스
CAtlTransactionManager 클래스는 커널 트랜잭션 관리자 KTM () 함수에 대 한 래퍼를 제공합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CAtlTransactionManager;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[~ CAtlTransactionManager](#dtor)|CAtlTransactionManager 소멸자|  
|[CAtlTransactionManager](#catltransactionmanager)|CAtlTransactionManager 생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[닫기](#close)|하나는 트랜잭션 핸들을 닫습니다.|  
|[커밋](#commit)|트랜잭션이 커밋된 되도록 요청 합니다.|  
|[만들기](#create)|트랜잭션 핸들을 만듭니다.|  
|[CreateFile](#createfile)|만들거나 파일, 파일 스트림 또는 트랜잭션된 작업 디렉터리를 엽니다.|  
|[DeleteFile](#deletefile)|트랜잭션된 작업으로 기존 파일을 삭제합니다.|  
|[FindFirstFile](#findfirstfile)|트랜잭션된 작업으로 파일이 나 하위 디렉터리에 대 한 디렉터리를 검색합니다.|  
|[GetFileAttributes](#getfileattributes)|트랜잭션된 작업으로 지정 된 파일 또는 디렉터리에 대 한 파일 시스템 특성을 검색합니다.|  
|[GetFileAttributesEx](#getfileattributesex)|트랜잭션된 작업으로 지정 된 파일 또는 디렉터리에 대 한 파일 시스템 특성을 검색합니다.|  
|[GetHandle](#gethandle)|트랜잭션 핸들을 반환합니다.|  
|[IsFallback](#isfallback)|대체 (fallback) 호출을 사용할지 여부를 결정 합니다.|  
|[MoveFile](#movefile)|기존 파일 또는 디렉터리에 자식을 포함 하 여 트랜잭션된 작업으로 이동 합니다.|  
|[RegCreateKeyEx](#regcreatekeyex)|지정된 된 레지스트리 키를 만들고 트랜잭션과 연결 합니다. 키가 이미 있는 경우 함수를 엽니다.|  
|[RegDeleteKey](#regdeletekey)|트랜잭션된 작업으로 하는 레지스트리의 지정된 된 플랫폼 특정 보기에서 하위 키와 해당 값을 삭제합니다.|  
|[RegOpenKeyEx](#regopenkeyex)|지정된 된 레지스트리 키 열리고을 트랜잭션에 연결 됩니다.|  
|[롤백](#rollback)|트랜잭션을 롤백할 수 있는 요청 수입니다.|  
|[SetFileAttributes](#setfileattributes)|트랜잭션된 작업으로 파일이 나 디렉터리에 대 한 특성을 설정합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[m_bFallback](#m_bfallback)|`TRUE`지원 되는 대체 하는 경우 `FALSE` 그렇지 않은 경우.|  
|[m_hTransaction](#m_htransaction)|트랜잭션 핸들입니다.|  
  
## <a name="remarks"></a>주의  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [ATL::CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atltransactionmanager.h  
  
##  <a name="a-namedtora--catltransactionmanager"></a><a name="dtor"></a>~ CAtlTransactionManager  
 CAtlTransactionManager 소멸자  
  
```
virtual ~CAtlTransactionManager();
```  
  
### <a name="remarks"></a>주의  
 일반적인 처리에서 트랜잭션이 자동으로 적용 고 닫으십시오. 소멸자가 호출 되는 예외 해제 하는 동안, 트랜잭션이 롤백 되 고 닫힐 합니다.  
  
##  <a name="a-namecatltransactionmanagera--catltransactionmanager"></a><a name="catltransactionmanager"></a>CAtlTransactionManager  
 CAtlTransactionManager 생성자입니다.  
  
```
CAtlTransactionManager(BOOL bFallback = TRUE, BOOL bAutoCreateTransaction = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bFallback`  
 `TRUE`지원 대체 (fallback)를 나타냅니다. 트랜잭션 된 함수가 실패 하면 클래스는 자동으로 "비트랜잭션" 함수를 호출 합니다. `FALSE`"대체" 호출을 나타냅니다.  
  
 `bAutoCreateTransaction`  
 `TRUE`트랜잭션 처리기의 생성자에서 자동으로 생성 있음을 나타냅니다. `FALSE`하지 않음을 나타냅니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameclosea--close"></a><a name="close"></a>닫기  
 트랜잭션 핸들을 닫습니다.  
  
```
inline BOOL Close();
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 `TRUE`이고, 그렇지 않으면 `FALSE`입니다.  
  
### <a name="remarks"></a>주의  
 이 래퍼 호출의 `CloseHandle` 함수입니다. 메서드는 소멸자가 자동으로 호출 됩니다.  
  
##  <a name="a-namecommita--commit"></a><a name="commit"></a>커밋  
 트랜잭션이 커밋된 되도록 요청 합니다.  
  
```
inline BOOL Commit();
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 `TRUE`이고, 그렇지 않으면 `FALSE`입니다.  
  
### <a name="remarks"></a>주의  
 이 래퍼 호출의 `CommitTransaction` 함수입니다. 메서드는 소멸자가 자동으로 호출 됩니다.  
  
##  <a name="a-namecreatea--create"></a><a name="create"></a>만들기  
 트랜잭션 핸들을 만듭니다.  
  
```
inline BOOL Create();
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 `TRUE`이고, 그렇지 않으면 `FALSE`입니다.  
  
### <a name="remarks"></a>주의  
 이 래퍼 호출의 `CreateTransaction` 함수입니다. 인지 확인  
  
##  <a name="a-namecreatefilea--createfile"></a><a name="createfile"></a>CreateFile  
 만들거나 파일, 파일 스트림 또는 트랜잭션된 작업 디렉터리를 엽니다.  
  
```
inline HANDLE CreateFile(
  LPCTSTR lpFileName,
    DWORD dwDesiredAccess,
    DWORD dwShareMode,
    LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    DWORD dwCreationDisposition,
    DWORD dwFlagsAndAttributes,
    HANDLE hTemplateFile);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpFileName`  
 만들거나 열 수 있는 개체의 이름입니다.  
  
 `dwDesiredAccess`  
 읽기, 쓰기, 둘 다 또는 둘 다 (영)으로 요약할 수 있는 개체에 액세스 합니다. 가장 일반적으로 사용 되는 값은 GENERIC_READ, GENERIC_WRITE, 또는 둘 모두: GENERIC_READ | GENERIC_WRITE 합니다.  
  
 `dwShareMode`  
 읽기, 쓰기, 둘 다를 수, 삭제,이 중에서 모두 지정 하거나 수 있는 개체의 공유 모드: 0, FILE_SHARE_DELETE, FILE_SHARE_READ, FILE_SHARE_WRITE 합니다.  
  
 `lpSecurityAttributes`  
 선택적 보안 설명자를 포함 하 고 자식 프로세스에 의해 반환 된 핸들을 상속할 수 있는지 여부를 결정 하는 SECURITY_ATTRIBUTES 구조에 대 한 포인터입니다. 매개 변수가 `NULL`합니다.  
  
 `dwCreationDisposition`  
 수행할 작업을 하는 존재 하 고 존재 하지 않는 파일에 있습니다. 이 매개 변수는 사용할 수 없는 다음 값 중 하나 여야 합니다: CREATE_ALWAYS, CREATE_NEW, OPEN_ALWAYS, OPEN_EXISTING, 또는 TRUNCATE_EXISTING 합니다.  
  
 `dwFlagsAndAttributes`  
 파일 특성 및 플래그입니다. 이 매개 변수는 사용 가능한 파일 특성 (FILE_ATTRIBUTE_ *)의 조합을 포함할 수 있습니다. 다른 모든 파일 특성 FILE_ATTRIBUTE_NORMAL를 재정의합니다. 이 매개 변수 플래그의 조합을 포함 될 수도 있습니다 (FILE_FLAG_\*) 버퍼링 동작의 컨트롤에 대 한 액세스 모드 및 기타 특수 한 용도의 플래그입니다. 이러한 모든 FILE_ATTRIBUTE_ 결합\* 값입니다.  
  
 `hTemplateFile`  
 템플릿 사용 하 여 파일 GENERIC_READ 액세스 권한이 유효한 핸들입니다. 템플릿 파일 파일 특성 및 생성 중인 파일에 대 한 확장 된 특성을 제공 합니다. 이 매개 변수는 `NULL`일 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 개체에 액세스 하는 데 사용할 수 있는 핸들을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 이 래퍼 호출의 `CreateFileTransacted` 함수입니다.  
  
##  <a name="a-namedeletefilea--deletefile"></a><a name="deletefile"></a>DeleteFile  
 트랜잭션된 작업으로 기존 파일을 삭제합니다.  
  
```
inline BOOL DeleteFile(LPCTSTR lpFileName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpFileName`  
 삭제할 파일의 이름입니다.  
  
### <a name="remarks"></a>주의  
 이 래퍼 호출의 `DeleteFileTransacted` 함수입니다.  
  
##  <a name="a-namefindfirstfilea--findfirstfile"></a><a name="findfirstfile"></a>FindFirstFile  
 트랜잭션된 작업으로 파일이 나 하위 디렉터리에 대 한 디렉터리를 검색합니다.  
  
```
inline HANDLE FindFirstFile(
  LPCTSTR lpFileName,
  WIN32_FIND_DATA* pNextInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpFileName`  
 디렉터리 또는 경로 및 파일 이름에 대 한 검색입니다. 이 매개 변수는 물음표 ()는 별표 (*) 등의 와일드 카드 문자를 포함할 수 있습니다.  
  
 `pNextInfo`  
 찾은 파일 또는 하위 디렉터리에 대 한 정보를 수신 하는 WIN32_FIND_DATA 구조에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 값에 대 한 후속 호출에 사용 되는 검색 핸들은 함수가 성공 하면 `FindNextFile` 또는 `FindClose`합니다. 함수가 실패 하거나 파일에서 검색 문자열을 찾지 못하면 경우는 `lpFileName` 매개 변수, 반환 값은 INVALID_HANDLE_VALUE가 있습니다.  
  
### <a name="remarks"></a>주의  
 이 래퍼 호출의 `FindFirstFileTransacted` 함수입니다.  
  
##  <a name="a-namegetfileattributesa--getfileattributes"></a><a name="getfileattributes"></a>GetFileAttributes  
 트랜잭션된 작업으로 지정 된 파일 또는 디렉터리에 대 한 파일 시스템 특성을 검색합니다.  
  
```
inline DWORD GetFileAttributes(LPCTSTR lpFileName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpFileName`  
 파일 또는 디렉터리의 이름입니다.  
  
### <a name="remarks"></a>주의  
 이 래퍼 호출의 `GetFileAttributesTransacted` 함수입니다.  
  
##  <a name="a-namegetfileattributesexa--getfileattributesex"></a><a name="getfileattributesex"></a>GetFileAttributesEx  
 트랜잭션된 작업으로 지정 된 파일 또는 디렉터리에 대 한 파일 시스템 특성을 검색합니다.  
  
```
inline BOOL GetFileAttributesEx(
    LPCTSTR lpFileName,
    GET_FILEEX_INFO_LEVELS fInfoLevelId,
    LPVOID lpFileInformation);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpFileName`  
 파일 또는 디렉터리의 이름입니다.  
  
 `fInfoLevelId`  
 검색할 특성 정보 수준입니다.  
  
 `lpFileInformation`  
 특성 정보를 수신 하는 버퍼에 대 한 포인터입니다. 이 버퍼에 저장 되어 있는 특성 정보 유형의 값에 의해 결정 됩니다 `fInfoLevelId`합니다. 하는 경우는 `fInfoLevelId` 매개 변수는 GetFileExInfoStandard 다음이 매개 변수는 WIN32_FILE_ATTRIBUTE_DATA 구조를 가리킵니다.  
  
### <a name="remarks"></a>주의  
 이 래퍼 호출의 `GetFileAttributesTransacted` 함수입니다.  
  
##  <a name="a-namegethandlea--gethandle"></a><a name="gethandle"></a>GetHandle  
 트랜잭션 핸들을 반환합니다.  
  
```
HANDLE GetHandle() const;
```  
  
### <a name="return-value"></a>반환 값  
 클래스에 대 한 트랜잭션 핸들을 반환합니다. 반환 `NULL` 경우는 `CAtlTransactionManager` 핸들에 연결 되지 않습니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameisfallbacka--isfallback"></a><a name="isfallback"></a>IsFallback  
 대체 (fallback) 호출을 사용할지 여부를 결정 합니다.  
  
```
BOOL IsFallback() const;
```  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 은 클래스는 대체 (fallback) 호출을 지원 합니다. 그렇지 않으면 `FALSE`입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namembfallbacka--mbfallback"></a><a name="m_bfallback"></a>m_bFallback  
 `TRUE`지원 되는 대체 하는 경우 `FALSE` 그렇지 않은 경우.  
  
```
BOOL m_bFallback;
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namemhtransactiona--mhtransaction"></a><a name="m_htransaction"></a>m_hTransaction  
 트랜잭션 핸들입니다.  
  
```
HANDLE m_hTransaction;
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namemovefilea--movefile"></a><a name="movefile"></a>MoveFile  
 기존 파일 또는 디렉터리에 자식을 포함 하 여 트랜잭션된 작업으로 이동 합니다.  
  
```
inline BOOL MoveFile(LPCTSTR lpOldFileName, LPCTSTR lpNewFileName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpOldFileName`  
 기존 파일 또는 디렉터리에 로컬 컴퓨터의 현재 이름입니다.  
  
 `lpNewFileName`  
 파일 또는 디렉터리에 대 한 새 이름입니다. 이 이름은 없어야 합니다. 새 파일을 다른 파일 시스템 또는 드라이브를 수 있습니다. 새 디렉터리는 동일한 드라이브에 있어야 합니다.  
  
### <a name="remarks"></a>주의  
 이 래퍼 호출의 `MoveFileTransacted` 함수입니다.  
  
##  <a name="a-nameregcreatekeyexa--regcreatekeyex"></a><a name="regcreatekeyex"></a>RegCreateKeyEx  
 지정된 된 레지스트리 키를 만들고 트랜잭션과 연결 합니다. 키가 이미 있는 경우 함수를 엽니다.  
  
```
inline LSTATUS RegCreateKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD dwReserved,
    LPTSTR lpClass,
    DWORD dwOptions,
    REGSAM samDesired,
    CONST LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    PHKEY phkResult,
    LPDWORD lpdwDisposition);
```  
  
### <a name="parameters"></a>매개 변수  
 `hKey`  
 열린 레지스트리 키에 대 한 핸들입니다.  
  
 `lpSubKey`  
 이 함수를 열거나 만듭니다 하위 키의 이름입니다.  
  
 `dwReserved`  
 이 매개 변수는 예약 되며&0; 이어야 합니다.  
  
 `lpClass`  
 이 키의 사용자 정의 클래스입니다. 이 매개 변수는 무시 될 수 있습니다. 이 매개 변수는 NULL 일 수 있습니다.  
  
 `dwOptions`  
 이 매개 변수는 다음 값 중 하나일 수 있습니다: REG_OPTION_BACKUP_RESTORE, REG_OPTION_NON_VOLATILE, 또는 REG_OPTION_VOLATILE 합니다.  
  
 `samDesired`  
 키에 대 한 액세스 권한을 지정 하는 마스크입니다.  
  
 `lpSecurityAttributes`  
 자식 프로세스에 의해 반환 된 핸들을 상속할 수 있는지 여부를 결정 하는 SECURITY_ATTRIBUTES 구조에 대 한 포인터입니다. 경우 `lpSecurityAttributes` 는 `NULL`, 핸들을 상속할 수 없습니다.  
  
 `phkResult`  
 포인터에서 열린 또는 생성 된 키에 대 한 핸들을 수신 하는 변수입니다. 키 미리 정의 된 레지스트리 키 중 하나가 아닌 경우 호출 된 `RegCloseKey` 핸들 사용을 완료 한 후에 작동 합니다.  
  
 `lpdwDisposition`  
 처리는 다음 값 중 하나를 수신 하는 변수에 대 한 포인터: REG_CREATED_NEW_KEY 또는 REG_OPENED_EXISTING_KEY 합니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 반환 값은 error_success가 있습니다. 함수가 실패 한 경우 반환 값은 Winerror.h에 정의 되어 있는&0;이 아닌 오류 코드입니다.  
  
### <a name="remarks"></a>주의  
 이 래퍼 호출의 `RegCreateKeyTransacted` 함수입니다.  
  
##  <a name="a-nameregdeletekeya--regdeletekey"></a><a name="regdeletekey"></a>RegDeleteKey  
 트랜잭션된 작업으로 하는 레지스트리의 지정된 된 플랫폼 특정 보기에서 하위 키와 해당 값을 삭제합니다.  
  
```
inline LSTATUS RegDeleteKeyEx(HKEY hKey, LPCTSTR lpSubKey);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`hKey`|열린 레지스트리 키에 대 한 핸들입니다.|  
|`lpSubKey`|삭제할 키의 이름입니다.|  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 반환 값은 error_success가 있습니다. 함수가 실패 한 경우 반환 값은 Winerror.h에 정의 되어 있는&0;이 아닌 오류 코드입니다.  
  
### <a name="remarks"></a>주의  
 이 래퍼 호출의 `RegDeleteKeyTransacted` 함수입니다.  
  
##  <a name="a-nameregopenkeyexa--regopenkeyex"></a><a name="regopenkeyex"></a>RegOpenKeyEx  
 지정된 된 레지스트리 키 열리고을 트랜잭션에 연결 됩니다.  
  
```
inline LSTATUS RegOpenKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD ulOptions,
    REGSAM samDesired,
    PHKEY phkResult);
```  
  
### <a name="parameters"></a>매개 변수  
 `hKey`  
 열린 레지스트리 키에 대 한 핸들입니다.  
  
 `lpSubKey`  
 열려는 레지스트리 하위 키의 이름입니다.  
  
 `ulOptions`  
 이 매개 변수는 예약 되며&0; 이어야 합니다.  
  
 `samDesired`  
 키에 대 한 액세스 권한을 지정 하는 마스크입니다.  
  
 `phkResult`  
 포인터에서 열린 또는 생성 된 키에 대 한 핸들을 수신 하는 변수입니다. 키 미리 정의 된 레지스트리 키 중 하나가 아닌 경우 호출 된 `RegCloseKey` 핸들 사용을 완료 한 후에 작동 합니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 반환 값은 error_success가 있습니다. 반환 값은 Winerror.h에 정의 된&0;이 아닌 오류 코드를 함수가 실패 한 경우  
  
### <a name="remarks"></a>주의  
 이 래퍼 호출의 `RegOpenKeyTransacted` 함수입니다.  
  
##  <a name="a-namerollbacka--rollback"></a><a name="rollback"></a>롤백  
 트랜잭션을 롤백할 수 있는 요청 수입니다.  
  
```
inline BOOL Rollback();
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 `TRUE`이고, 그렇지 않으면 `FALSE`입니다.  
  
### <a name="remarks"></a>주의  
 이 래퍼 호출의 `RollbackTransaction` 함수입니다.  
  
##  <a name="a-namesetfileattributesa--setfileattributes"></a><a name="setfileattributes"></a>SetFileAttributes  
 트랜잭션된 작업으로 파일이 나 디렉터리에 대 한 특성을 설정합니다.  
  
```
inline BOOL SetFileAttributes(LPCTSTR lpFileName, DWORD dwAttributes);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpFileName`  
 파일 또는 디렉터리의 이름입니다.  
  
 `dwAttributes`  
 파일 특성 파일에 대 한 설정입니다. 자세한 내용은 참조 [SetFileAttributesTransacted](http://go.microsoft.com/fwlink/linkid=158699)합니다.  
  
### <a name="remarks"></a>주의  
 이 래퍼 호출의 `SetFileAttributesTransacted` 함수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATL COM 데스크톱 구성 요소](../../atl/atl-com-desktop-components.md)

