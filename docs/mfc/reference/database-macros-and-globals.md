---
title: "데이터베이스 매크로 및 전역 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFXDB/AFX_ODBC_CALL
- AFXDB/AFX_SQL_ASYNC
- AFXDB/AFX_SQL_SYNC
- AFXDB/AfxGetHENV
dev_langs:
- C++
helpviewer_keywords:
- global database functions [C++]
- database macros [C++]
- database globals [C++]
- global functions [C++], database functions
- macros [C++], MFC database
ms.assetid: 5b9b9e61-1cf9-4345-9f29-3807dd466488
caps.latest.revision: 13
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 9706c47d9bd5996c28873da6a15a687bf9b5e038
ms.lasthandoff: 02/24/2017

---
# <a name="database-macros-and-globals"></a>데이터베이스 매크로 및 전역
매크로 및 전역 변수 아래에 나열 된 ODBC 기반 데이터베이스 응용 프로그램에 적용 됩니다. DAO 기반 응용 프로그램에서 사용 되지 않습니다.  
  
 매크로, MFC 4.2 이전 `AFX_SQL_ASYNC` 및 `AFX_SQL_SYNC` 다른 프로세스에 대 한 시간 얻을 수 있는 비동기 작업을 제공 했습니다. MFC ODBC 클래스에는 동기 작업만 사용 되기 때문에 변경 된 이러한 매크로의 구현은 MFC 4.2에서 시작 합니다. 매크로 `AFX_ODBC_CALL` MFC 4.2를 합니다.  
  
### <a name="database-macros"></a>데이터베이스 매크로  
  
|||  
|-|-|  
|[AFX_ODBC_CALL](#afx_odbc_call)|반환 하는 ODBC API 함수를 호출 `SQL_STILL_EXECUTING`합니다. `AFX_ODBC_CALL`반복적으로 함수를 호출할 때까지 더 이상 반환 `SQL_STILL_EXECUTING`합니다.|  
|[AFX_SQL_ASYNC](#afx_sql_async)|`AFX_ODBC_CALL`.|  
|[AFX_SQL_SYNC](#afx_sql_sync)|호출이 반환 하지 않는 ODBC API 함수 `SQL_STILL_EXECUTING`합니다.|  
  
### <a name="database-globals"></a>데이터베이스 전역  
  
|||  
|-|-|  
|[AfxGetHENV](#afxgethenv)|MFC에서 사용 중인 ODBC 환경에 대 한 핸들을 검색합니다. 직접 ODBC 호출에서이 핸들을 사용할 수 있습니다.|  
  
##  <a name="afx_odbc_call"></a>AFX_ODBC_CALL  
 이 매크로 사용 하 여 반환할 수 있는 모든 ODBC API 함수를 호출 하려면 `SQL_STILL_EXECUTING`합니다.  
  
```  
AFX_ODBC_CALL(SQLFunc)  
```  
  
### <a name="parameters"></a>매개 변수  
 `SQLFunc`  
 ODBC API 함수입니다. ODBC API 함수에 대한 자세한 내용은 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]를 참조하십시오.  
  
### <a name="remarks"></a>주의  
 `AFX_ODBC_CALL`함수 반복적으로 호출 될 때까지 더 이상 반환 `SQL_STILL_EXECUTING`합니다.  
  
 호출 하기 전에 `AFX_ODBC_CALL`, 변수를 선언 해야 `nRetCode`, 형식의 **RETCODE**합니다.  
  
 MFC ODBC 클래스 지금 사용 하 여 동기적 처리만는 note 합니다. 비동기 작업을 수행 하려면 ODBC API 함수를 호출 해야 **SQLSetConnectOption**합니다. 자세한 내용은 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]에서 "비동기적으로 함수 실행" 항목을 참조하십시오.  

  
### <a name="example"></a>예제  
 이 예에서는 `AFX_ODBC_CALL` 를 호출 하는 **SQLColumns** 의해 명명 된 테이블의 열 목록이 반환 하는 ODBC API 함수를 `strTableName`합니다. 선언을 확인 하십시오 `nRetCode` 및 함수에 매개 변수를 전달 하는 레코드 집합 데이터 멤버를 사용 합니다. 사용 하 여 호출의 결과 확인 하면 예제도와 **확인**, 클래스의 멤버 함수 `CRecordset`합니다. 변수 `prs` 에 대 한 포인터는 `CRecordset` 개체를 다른 곳에서 선언 합니다.  
  
 [!code-cpp[NVC_MFCDatabase #&39;](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** afxdb.h  

##  <a name="afx_sql_async"></a>AFX_SQL_ASYNC  
 이 매크로의 구현은 MFC 4.2에서 변경되었습니다.  
  
```   
AFX_SQL_ASYNC(prs, SQLFunc)   
```  
  
### <a name="parameters"></a>매개 변수  
 `prs`  
 `CRecordset` 개체 또는 `CDatabase` 개체에 대한 포인터입니다. MFC 4.2부터는 이 매개 변수 값이 무시됩니다.  
  
 `SQLFunc`  
 ODBC API 함수입니다. ODBC API 함수에 대한 자세한 내용은 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]를 참조하십시오.  
  
### <a name="remarks"></a>주의  
 `AFX_SQL_ASYNC`매크로 호출 하기만 하면 [AFX_ODBC_CALL](#afx_odbc_call) 무시 하 고는 `prs` 매개 변수입니다. MFC 4.2 이전 버전에서, `AFX_SQL_ASYNC`는 `SQL_STILL_EXECUTING`를 반환할 수 있는 ODBC API 함수를 호출하기 위해 사용되었습니다. ODBC API 함수가 `SQL_STILL_EXECUTING`을 반환한 경우, `AFX_SQL_ASYNC`가 `prs->OnWaitForDataSource`를 호출합니다.  
  
> [!NOTE]
>  MFC ODBC 클래스에는 이제 동기적 처리만 사용됩니다. 비동기 작업을 수행 하려면 ODBC API 함수를 호출 해야 **SQLSetConnectOption**합니다. 자세한 내용은 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]에서 "비동기적으로 함수 실행" 항목을 참조하십시오.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdb.h  
  
##  <a name="afx_sql_sync"></a>AFX_SQL_SYNC  
 `AFX_SQL_SYNC` 매크로 함수를 호출 하면 `SQLFunc`합니다.  
  
```   
AFX_SQL_SYNC(SQLFunc)   
```  
  
### <a name="parameters"></a>매개 변수  
 `SQLFunc`  
 ODBC API 함수입니다. 이러한 함수에 대 한 자세한 내용은 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 반환 하지 것입니다 ODBC API 함수를 호출 하려면 `SQL_STILL_EXECUTING`합니다.  
  
 호출 하기 전에 `AFX_SQL_SYNC`, 변수를 선언 해야 `nRetCode`, 형식의 **RETCODE**합니다. 값을 확인할 수 있습니다 `nRetCode` 매크로 호출 합니다.  
  
 구현의 `AFX_SQL_SYNC` MFC 4.2에서 변경 되었습니다. 서버 상태 검사는 더 이상 필요 하기 때문에 `AFX_SQL_SYNC` 값을 할당 `nRetCode`합니다. 예를 들어 호출을 수행 하는 대신  
  
 [!code-cpp[NVC_MFCDatabase #&40;](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]  
  
 할당 만들 수 있습니다.  
  
 [!code-cpp[NVC_MFCDatabase #&41;](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdb.h  
  
##  <a name="afxgethenv"></a>AfxGetHENV  
 직접 ODBC 호출에서 반환된 된 핸들을 사용할 수 있지만 핸들 또는 핸들 이라고 가정 여전히 유효 하 고 사용할 수 있는 모든 기존 해야 `CDatabase`-또는 `CRecordset`-파생 된 개체가 소멸 되었다고 합니다.  
  
```   
HENV AFXAPI AfxGetHENV(); 
```  
  
### <a name="return-value"></a>반환 값  
 MFC에서 사용 중인 ODBC 환경 핸들입니다. 수 `SQL_HENV_NULL` 있으면 없는 [CDatabase](../../mfc/reference/cdatabase-class.md) 개체 및&0; [CRecordset](../../mfc/reference/crecordset-class.md) 사용 중인 개체입니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdb.h  
    
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)

