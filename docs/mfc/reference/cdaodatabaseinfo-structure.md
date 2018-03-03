---
title: "CDaoDatabaseInfo 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoDatabaseInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoDatabaseInfo structure [MFC]
- DAO (Data Access Objects), Databases collection
ms.assetid: 68e9e0da-8382-4fc6-8115-1b1519392ddb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 085d0e525cb00c9fffb3698080194da92a6dbb8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cdaodatabaseinfo-structure"></a>CDaoDatabaseInfo 구조체
`CDaoDatabaseInfo` 구조 데이터 액세스 개체 (DAO)에 대해 정의 된 데이터베이스 개체에 대 한 정보를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct CDaoDatabaseInfo  
{  
    CString m_strName;       // Primary  
    BOOL m_bUpdatable;       // Primary  
    BOOL m_bTransactions;    // Primary  
    CString m_strVersion;    // Secondary  
    long m_lCollatingOrder;  // Secondary  
    short m_nQueryTimeout;   // Secondary  
    CString m_strConnect;    // All  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 `m_strName`  
 고유 하 게 데이터베이스 개체의 이름을 지정 합니다. 이 속성을 직접 검색 하려면 호출 [CDaoDatabase::GetName](../../mfc/reference/cdaodatabase-class.md#getname)합니다. 자세한 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다.  
  
 `m_bUpdatable`  
 데이터베이스에 변경 내용을 만들 수 있는지 여부를 나타냅니다. 이 속성을 직접 검색 하려면 호출 [CDaoDatabase::CanUpdate](../../mfc/reference/cdaodatabase-class.md#canupdate)합니다. 자세한 내용은 DAO 도움말의 "업데이트할 수 있는 Property" 항목을 참조 합니다.  
  
 *m_bTransactions*  
 데이터 소스에서 트랜잭션을 지원 하는지 여부를 지정-는 일련의 변경 내용 나중에 다시 롤백할 수 있는 기록 (취소) 또는 커밋 (저장) 합니다. 데이터베이스는 Microsoft Jet 데이터베이스 엔진을 기반 트랜잭션 속성은 0이 아닌 하 고 트랜잭션을 사용할 수 있습니다. 다른 데이터베이스 엔진 트랜잭션을 지원 하지 않을 수 있습니다. 이 속성을 직접 검색 하려면 호출 [CDaoDatabase::CanTransact](../../mfc/reference/cdaodatabase-class.md#cantransact)합니다. 자세한 내용은 DAO 도움말의 "트랜잭션 Property" 항목을 참조 합니다.  
  
 *m_strVersion*  
 Microsoft Jet 데이터베이스 엔진의 버전을 나타냅니다. 이 속성의 값을 직접 검색 하는 데이터베이스 개체를 호출 [GetVersion](../../mfc/reference/cdaodatabase-class.md#getversion) 멤버 함수입니다. 자세한 내용은 DAO 도움말의 "버전 Property" 항목을 참조 합니다.  
  
 `m_lCollatingOrder`  
 문자열 비교 또는 정렬에 대 한 텍스트 정렬 순서를 지정 합니다. 가능한 값은 다음과 같습니다.  
  
- **dbSortGeneral** 일반 (영어, 프랑스어, 독일어, 포르투갈어, 이탈리아어, 및 현대 스페인어) 정렬 순서를 사용 합니다.  
  
- **dbSortArabic** 아랍어 정렬 순서를 사용 합니다.  
  
- **dbSortCyrillic** 러시아어 정렬 순서를 사용 합니다.  
  
- **dbSortCzech** 체코어 정렬 순서를 사용 합니다.  
  
- **dbSortDutch** 네덜란드어 정렬 순서를 사용 합니다.  
  
- **dbSortGreek** 그리스 정렬 순서를 사용 합니다.  
  
- **dbSortHebrew** 히브리어 정렬 순서를 사용 합니다.  
  
- **dbSortHungarian** 헝가리어 정렬 순서를 사용 합니다.  
  
- **dbSortIcelandic** Icelandic 정렬 순서를 사용 합니다.  
  
- **dbSortNorwdan** 노르웨이어 또는 덴마크어 정렬 순서를 사용 합니다.  
  
- **dbSortPDXIntl** Paradox International 정렬 순서를 사용 합니다.  
  
- **dbSortPDXNor** Paradox 노르웨이어 또는 덴마크어 정렬 순서를 사용 합니다.  
  
- **dbSortPDXSwe** Paradox 스웨덴어 또는 핀란드어 정렬 순서를 사용 합니다.  
  
- **dbSortPolish** 폴란드어 정렬 순서를 사용 합니다.  
  
- **dbSortSpanish** 스페인어 정렬 순서를 사용 합니다.  
  
- **dbSortSwedFin** 스웨덴 또는 핀란드어 정렬 순서를 사용 합니다.  
  
- **dbSortTurkish** 터키어 정렬 순서를 사용 합니다.  
  
- **dbSortUndefined** 정렬 순서는 정의 되지 않거나 알 수 없는 합니다.  
  
 자세한 내용은 "사용자 지정 Windows 레지스트리 설정에 대 한 데이터 액세스" DAO 도움말의 항목을 참조 하십시오.  
  
 *m_nQueryTimeout*  
 초를 대기한 후 시간 초과 오류가 Microsoft Jet 데이터베이스 엔진에는 ODBC 데이터베이스에서 쿼리를 실행할 때 발생 합니다. 기본 제한 시간 값은 60 초입니다. 쿼리 제한 시간을 0으로 설정 하는 경우 시간 제한 없이 발생 합니다. 이 인해 프로그램 작동이 중지 될 수 있습니다. 이 속성의 값을 직접 검색 하는 데이터베이스 개체를 호출 [GetQueryTimeout](../../mfc/reference/cdaodatabase-class.md#getquerytimeout) 멤버 함수입니다. 자세한 내용은 DAO 도움말의 "QueryTimeout Property" 항목을 참조 합니다.  
  
 `m_strConnect`  
 열려 있는 데이터베이스의 원본에 대 한 정보를 제공 합니다. 정보에 대 한 연결 문자열을 한이 속성의 값을 직접 검색 하는 방법에 대 한 정보를 참조 하십시오.는 [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) 멤버 함수입니다. 자세한 내용은 DAO 도움말의 "연결 속성" 항목을 참조 하십시오.  
  
## <a name="remarks"></a>설명  
 클래스의 MFC 개체를 원본으로 하는 DAO 개체 데이터베이스가 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)합니다. 주, 보조 및 위의 모든에 대 한 참조 정보에서 반환 되는 방법을 나타내는 [CDaoWorkspace::GetDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) 멤버 함수입니다.  
  
 검색 한 정보는 [CDaoWorkspace::GetDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) 멤버 함수에 저장 되는 `CDaoDatabaseInfo` 구조입니다. 호출 `GetDatabaseInfo` 에 대 한는 `CDaoWorkspace` 개체가 데이터베이스 데이터 정렬 인 데이터베이스 개체가 저장 되었습니다. `CDaoDatabaseInfo`또한 정의 `Dump` 디버그에서 멤버 함수를 작성 합니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 `CDaoDatabaseInfo` 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoWorkspace 클래스](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoDatabase 클래스](../../mfc/reference/cdaodatabase-class.md)
