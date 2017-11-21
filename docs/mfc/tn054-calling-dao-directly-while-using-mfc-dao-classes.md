---
title: "TN054: MFC DAO 클래스를 사용 하면서 직접 DAO 호출 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.dao
dev_langs: C++
helpviewer_keywords:
- MFC, DAO and
- passwords [MFC], calling DAO
- security [MFC], DAO
- DAO (Data Access Objects), calling directly
- DAO (Data Access Objects), security
- security [MFC]
- TN054
- DAO (Data Access Objects), and MFC
ms.assetid: f7de7d85-8d6c-4426-aa05-2e617c0da957
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d75f7ccf070bdc23702d6999c7fe45b35301360c
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="tn054-calling-dao-directly-while-using-mfc-dao-classes"></a>TN054: MFC DAO 클래스를 사용하면서 직접 DAO 호출
> [!NOTE]
>  Visual c + + 환경 및 마법사 (DAO 클래스에 포함 되어 있으며 계속 사용할 수 있습니다) 이지만 DAO을 지원 하지 않습니다. 사용 하는 것이 좋습니다 [OLE DB 템플릿](../data/oledb/ole-db-templates.md) 또는 [ODBC 및 MFC](../data/odbc/odbc-and-mfc.md) 새 프로젝트에 대 한 합니다. DAO는 기존 응용 프로그램 유지 관리만 사용할 수 있습니다.  
  
 MFC DAO 데이터베이스 클래스를 사용 하는 경우 직접 DAO를 사용 하는 데 필요한 한 상황이 있을 수 있습니다. 일반적으로이 이름은 되지 경우 이지만 MFC에서 직접 DAO 호출 MFC 클래스의 사용을 결합 하는 경우 직접 DAO의 함으로써 호출 간단한를 용이 하 게 하려면 일부 도우미 메커니즘을 제공 합니다. 직접 DAO 하는 DAO MFC 관리 되는 개체의 메서드를 호출 단 몇 줄의 코드를 위해서는 합니다. 만들고 있는 DAO 개체를 사용 해야 *하지* 실제로 호출 하 여 좀 더 많은 작업을 수행할 수 있는 MFC에서 관리 하는 **릴리스** 개체에 있습니다. 이 기술 노트는 직접 DAO 호출 하려는 경우, MFC 도우미를 수행할 수 있는 및 DAO OLE 인터페이스를 사용 하는 방법을 설명 합니다. 마지막으로,이 노트는 DAO 보안 기능에 대 한 직접 DAO 호출 하는 방법을 보여 주는 몇 가지 샘플 기능을 제공 합니다.  
  
## <a name="when-to-make-direct-dao-calls"></a>직접 DAO 호출을 수행 하는 경우  
 MFC에서 래핑되지 기능을 구현 하는 경우 또는 컬렉션을 새로 고칠 수에 필요 하는 경우 직접 DAO 호출 하기 위한 가장 일반적인 상황에서 발생 합니다. MFC에 의해 노출 되지 않는 가장 중요 한 기능은 보안입니다. 보안 기능을 구현 하려는 경우에 직접 DAO 사용자 및 그룹 개체를 사용 해야 합니다. 보안, 외에도 몇 가지 다른 기능 들을 DAO MFC에서 지원 되지 않습니다. 여기에 레코드 집합 복제 및 데이터베이스 복제 기능 뿐만 아니라 DAO로 몇 가지 추가 기능이 포함 됩니다.  
  
## <a name="a-brief-overview-of-dao-and-mfcs-implementation"></a>DAO 및 MFC의 구현에 대 한 간략 한 개요  
 MFC의 래핑 DAO 준다고에 걱정 하지 않아도 되도록 많은 세부 사항을 처리 하 여 보다 쉽게 사용 하는 DAO 하면 수입니다. OLE, 생성 및 DAO 개체 (특히: 컬렉션 개체) 오류 검사 및 제공 되는 강력한 형식의 간단한 인터페이스의 관리를 초기화 하는 여기에 (없음 **VARIANT** 또는 `BSTR` 인수)입니다. 직접 DAO 호출 하 고 여전히 이러한 기능을 이용할 수 있습니다. 코드에서 해야 할 모든 호출이 **릴리스** 직접 DAO에서 생성 된 모든 개체에 대 한 호출 및 *하지* MFC에서 내부적으로 사용할 수 있는 인터페이스 포인터를 수정 합니다. 예를 들어 수정 하지 마십시오는 **m_pDAORecordset** 열린 소속 `CDaoRecordset` 이해 하지 못하면 개체 *모든* 내부 문제를 가져옵니다. 그러나 사용할 수는 **m_pDAORecordset** 가져올 Fields 컬렉션에 직접 DAO 호출 하는 인터페이스입니다. 이 경우에 **m_pDAORecordset** 멤버를 수정할 수는 있습니다. 호출 하기만 하면 **릴리스** 개체와 함께 완료 했으면 필드 컬렉션 개체에 있습니다.  
  
## <a name="description-of-helpers-to-make-dao-calls-easier"></a>DAO 있도록 도우미의 설명 보다 쉽게 호출  
 DAO를 쉽게 호출할 수 있도록 하는 도우미에는 MFC DAO 데이터베이스 클래스에서 내부적으로 사용 되는 동일한 도우미입니다. 이러한 도우미 로그 디버그 출력을 예상된 오류를 검사 하 고 필요한 경우 적절 한 예외를 throw 하는 직접 DAO 호출을 수행할 때 반환 코드를 확인 하는 데 사용 됩니다. 이러한 두 도우미 중 하나에 매핑되는 4 개의 매크로 및 기본 도우미 함수 두 가지가 있습니다. 가장 하기만 하는 코드를 읽을 수 있습니다. 참조 **DAO_CHECK**, **DAO_CHECK_ERROR**, **DAO_CHECK_MEM**, 및 **DAO_TRACE** AFXDAO에 있습니다. 매크로, 및 참조를 H **AfxDaoCheck** 및 **AfxDaoTrace** DAOCORE에 있습니다. CPP 합니다.  
  
## <a name="using-the-dao-ole-interfaces"></a>DAO OLE 인터페이스를 사용 하 여  
 DAO 개체 계층 구조에 있는 각 개체에 대 한 OLE 인터페이스 DBDAOINT 헤더 파일에 정의 됩니다. H files\microsoft Visual Studio.NET 2003\VC7\include 디렉터리에 있습니다. 이러한 인터페이스에는 전체 DAO 계층을 조작할 수 있도록 하는 방법을 제공 합니다.  
  
 DAO 인터페이스의 메서드 중 많은 경우 조작 해야 합니다는 `BSTR` 개체 (길이 접두사가 문자열에 OLE 자동화 사용). `BSTR` 내 개체에 캡슐화 일반적으로 **VARIANT** 데이터 형식입니다. MFC 클래스 `COleVariant` 자체에서 상속 되는 **VARIANT** 데이터 형식입니다. 여부 ANSI 또는 유니코드에 대 한 프로젝트를 빌드할에 따라 DAO 인터페이스 돌아갑니다 ANSI 또는 유니코드 `BSTR`s입니다. 두 매크로 **V_BSTR** 및 **V_BSTRT**는 가져옵니다 DAO 인터페이스 지 확인 하는 데는 유용는 `BSTR` 예상 되는 형식의 합니다.  
  
 **V_BSTR** 추출 됩니다는 **bstrVal** 의 멤버는 `COleVariant`합니다. 콘텐츠를 전달 해야 하는 경우이 매크로 일반적으로 사용 되는 `COleVariant` DAO 인터페이스의 메서드에 합니다. 다음 코드는 선언 및 사용 하는 DAO DAOUser 인터페이스의 두 가지 방법에 대 한 실제 사용을 모두 표시는 **V_BSTR** 매크로:  
  
```  
COleVariant varOldName;  
COleVariant varNewName(_T("NewUser"), VT_BSTRT);

 
// Code to assign pUser to a valid value omitted  
DAOUser *pUser = NULL;  
 
// These method declarations were taken from DBDAOINT.H  
// STDMETHOD(get_Name) (THIS_ BSTR FAR* pbstr) PURE;  
// STDMETHOD(put_Name) (THIS_ BSTR bstr) PURE;  
 
DAO_CHECK(pUser->get_Name(&V_BSTR (&varOldName)));

DAO_CHECK(pUser->put_Name(V_BSTR (&varNewName)));
```  
  
 `VT_BSTRT` 에 지정 된 인수는 `COleVariant` 위의 생성자 통해 ANSI 있게 되며 `BSTR` 에 `COleVariant` 는 ANSI 버전의 응용 프로그램 및 유니코드 빌드하는 경우 `BSTR` 의 유니코드 버전에 대 한 응용 프로그램입니다. 이 DAO이 기대 합니다.  
  
 다른 매크로 **V_BSTRT**, ANSI 또는 유니코드 중 하나를 추출 합니다 **bstrVal** 소속 `COleVariant` 빌드 (ANSI 또는 유니코드)의 유형에 따라 합니다. 다음 코드를 추출 하는 방법을 보여 줍니다는 `BSTR` 에서 값을 `COleVariant` 에 `CString`:  
  
```  
COleVariant varName(_T("MyName"), VT_BSTRT);

CString str = V_BSTRT(&varName);
```  
  
 **V_BSTRT** 매크로에 저장 되어 있는 다른 형식을에 명시 된 기타 기술 함께 `COleVariant`, DAOVIEW 샘플에서와 합니다. 특히,이 변환에서 수행 된 **CCrack::strVARIANT** 메서드. 변환의 값을 가능한 경우,이 메서드는 `COleVariant` 의 인스턴스로 `CString`합니다.  
  
## <a name="simple-example-of-a-direct-call-to-dao"></a>직접 DAO 호출의 간단한 예  
 상황에는 기본 DAO 컬렉션 개체를 새로 고치려면 필요한 경우에 발생할 수 있습니다. 일반적으로 필요에 따라 해야 하지만 필요한 경우는 간단한 프로시저를 쉽습니다. 새로 고쳐져 야 컬렉션 수 해야 하는 경우의 예로 여러 사용자가 만드는 새 테이블에 정의 된 다중 사용자 환경에서 작동 하는 경우. 이 경우 tabledefs 컬렉션 부실 해질 수 있습니다. 컬렉션을 새로 고치려면 단순히를 호출 해야는 **새로 고침** 오류에 대 한 특정 컬렉션 개체 및 확인 방법:  
  
```  
DAO_CHECK(pMyDaoDatabase->  
    m_pDAOTableDefs->Refresh());
```  
  
 모든 DAO 컬렉션 개체 인터페이스 MFC DAO 데이터베이스 클래스의 문서화 되지 않은 구현 세부 정보는 현재 참고 합니다.  
  
## <a name="using-dao-directly-for-dao-security-features"></a>DAO 보안 기능에 대 한 직접 DAO를 사용 하 여  
 MFC DAO 데이터베이스 클래스에서 DAO 보안 기능을 래핑하지 마십시오. DAO 일부 DAO 보안 기능을 사용 하는 인터페이스의 메서드를 호출 해야 합니다. 다음 함수는 시스템 데이터베이스를 설정 하 고 사용자의 암호를 변경 합니다. 이 함수는 다른 함수는 정의 된 이후에 호출 합니다.  
  
```  
void ChangeUserPassword()  
{ *// Specify path to the Microsoft Access *// system database  
    CString strSystemDB = 
    _T("c:\\Program Files\\MSOffice\\access\\System.mdw");

 *// Set system database before MFC initilizes DAO *// NOTE: An MFC module uses only one instance *// of a DAO database engine object. If you have *// called a DAO object in your application prior *// to calling the function below,
    you must call *// AfxDaoTerm to destroy the existing database *// engine object. Otherwise,
    the database engine *// object already in use will be reused,
    and setting *// a system datbase will have no effect. *// *// If you have used a DAO object prior to calling *// this function it is important that DAO be *// terminated with AfxDaoTerm since an MFC *// module only gets one copy of the database engine *// and that engine will be reused if it hasn't been *// terminated. In other words,
    if you do not call *// AfxDaoTerm and there is currently a database *// initialized,
    setting the system database will *// have no affect.  
 
    SetSystemDB(strSystemDB);

 *// User name and password manually added *// by using Microsoft Access  
    CString strUserName = _T("NewUser");

    CString strOldPassword = _T("Password");

    CString strNewPassword = _T("NewPassword");

 *// Set default user so that MFC will be able *// to log in by default using the user name and *// password from the system database  
    SetDefaultUser(strUserName,
    strOldPassword);

 *// Change the password. You should be able to *// call this function from anywhere in your *// MFC application  
    ChangePassword(strUserName,
    strOldPassword,   
    strNewPassword);

 
 .  
 .  
 .  
 
}  
```  
  
 다음 네 개의 예제에서는 설명 하는 방법:  
  
-   시스템 DAO 데이터베이스 설정 (합니다. MDW 파일)입니다.  
  
-   기본 사용자 이름과 암호를 설정 합니다.  
  
-   사용자의 암호를 변경 합니다.  
  
-   암호를 변경 하는 합니다. MDB 파일입니다.  
  
### <a name="setting-the-system-database"></a>시스템 데이터베이스를 설정합니다.  
 다음은 응용 프로그램에 의해 사용 될 시스템 데이터베이스를 설정 하는 샘플 함수입니다. 이 함수는 다른 DAO 호출 전에 호출 되어야 합니다.  
  
```  
// Set the system database that the   
// DAO database engine will use  
 
void SetSystemDB(CString& strSystemMDB)  
{  
    COleVariant varSystemDB(strSystemMDB, VT_BSTRT);

 *// Initialize DAO for MFC  
    AfxDaoInit();
DAODBEngine* pDBEngine = AfxDaoGetEngine();

 
    ASSERT(pDBEngine != NULL);

 *// Call put_SystemDB method to set the *// system database for DAO engine  
    DAO_CHECK(pDBEngine->put_SystemDB(varSystemDB.bstrVal));

} 
```  
  
### <a name="setting-the-default-user-and-password"></a>기본 사용자 이름 및 암호를 설정합니다.  
 기본 사용자 및 시스템 데이터베이스에 대 한 암호를 설정 하려면 다음 함수를 사용 합니다.  
  
```  
void SetDefaultUser(CString& strUserName,
    CString& strPassword)  
{  
    COleVariant varUserName(strUserName,
    VT_BSTRT);

    COleVariant varPassword(strPassword,
    VT_BSTRT);

 
    DAODBEngine* pDBEngine = AfxDaoGetEngine();
ASSERT(pDBEngine != NULL);

 *// Set default user:  
    DAO_CHECK(pDBEngine->put_DefaultUser(varUserName.bstrVal));

 *// Set default password:  
    DAO_CHECK(pDBEngine->put_DefaultPassword(varPassword.bstrVal));

} 
```  
  
### <a name="changing-a-users-password"></a>사용자의 암호를 변경합니다.  
 사용자의 암호를 변경 하려면 다음 함수를 사용 합니다.  
  
```  
void ChangePassword(CString &strUserName,   
    CString &strOldPassword,   
    CString &strNewPassword)  
{ *// Create (open) a workspace  
    CDaoWorkspace wsp;  
    CString strWspName = _T("Temp Workspace");

 
    wsp.Create(strWspName, strUserName,  
    strOldPassword);

 wsp.Append();

 *// Determine how many objects there are *// in the Users collection  
    short nUserCount;  
    short nCurrentUser;  
    DAOUser *pUser = NULL;  
    DAOUsers *pUsers = NULL;  
 *// Side-effect is implicit OLE AddRef() *// on DAOUser object:  
    DAO_CHECK(wsp.m_pDAOWorkspace->get_Users(&pUsers));

 *// Side-effect is implicit OLE AddRef() *// on DAOUsers object  
    DAO_CHECK(pUsers->getcount(&nUserCount));

 *// Traverse through the list of users *// and change password for the userid *// used to create/open the workspace  
    for(nCurrentUser = 0; nCurrentUser <nUserCount;  
    nCurrentUser++) 
 {  
    COleVariant varIndex(nCurrentUser, VT_I2);

    COleVariant varName;  
 *// Retrieve information for user nCurrentUser  
    DAO_CHECK(pUsers->get_Item(varIndex, &pUser));

 *// Retrieve name for user nCurrentUser  
    DAO_CHECK(pUser->get_Name(&V_BSTR(&varName)));

 
    CString strTemp = V_BSTRT(&varName);

 *// If there is a match, change the password  
    if(strTemp == strUserName)  
 {  
    COleVariant varOldPwd(strOldPassword,   
    VT_BSTRT);

 COleVariant  varNewPwd(strNewPassword,   
    VT_BSTRT);

 
    DAO_CHECK(pUser->NewPassword(V_BSTR(&varOldPwd), 
    V_BSTR(&varNewPwd)));

 
    TRACE("\t Password is changed\n");

 }  
 }  
 *// Clean up: decrement the usage count *// on the OLE objects  
    pUser->Release();
pUsers->Release();

 
    wsp.Close();

} 
```  
  
### <a name="changing-the-password-of-an-mdb-file"></a>암호를 변경 하는 합니다. MDB 파일  
 암호를 변경 하는 합니다. MDB 파일에서 다음 함수를 사용 합니다.  
  
```  
void SetDBPassword(LPCTSTR pDB,
    LPCTSTR pszOldPassword,
    LPCTSTR pszNewPassword)  
{  
    CDaoDatabase db;  
    CString strConnect(_T(";pwd="));

 *// the database must be opened as exclusive *// to set a password  
    db.Open(pDB,
    TRUE,
    FALSE,   
    strConnect + pszOldPassword);

 
    COleVariant NewPassword(pszNewPassword,
    VT_BSTRT),  
    OldPassword(pszOldPassword,
    VT_BSTRT);

 
    DAO_CHECK(db.m_pDAODatabase->NewPassword(V_BSTR(&OldPassword), 
    V_BSTR(&NewPassword)));

 
    db.Close();

} 
```  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

