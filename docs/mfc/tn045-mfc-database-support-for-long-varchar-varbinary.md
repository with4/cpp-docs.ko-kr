---
title: 'TN045: Long Varchar Varbinary MFC 데이터베이스 지원 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.data
dev_langs:
- C++
helpviewer_keywords:
- TN045
- Varbinary data type
- Varchar data type
ms.assetid: cf572c35-5275-45b5-83df-5f0e36114f40
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bd5201661afcdf6f4ae9676323f3f644817bcf7d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33386082"
---
# <a name="tn045-mfcdatabase-support-for-long-varcharvarbinary"></a>TN045: Long Varchar/Varbinary에 대한 MFC/데이터베이스 지원
> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
 이 노트는 ODBC를 보내고 검색 하는 방법에 설명 **SQL_LONGVARCHAR** 및 **SQL_LONGVARBINARY** MFC를 사용 하 여 데이터 형식을 데이터베이스 클래스입니다.  
  
## <a name="overview-of-long-varcharvarbinary-support"></a>Long Varchar/Varbinary 지원의 개요  
 ODBC **SQL_LONG_VARCHAR** 및 **SQL_LONGBINARY** (긴 데이터 열으로 여기에 나오는) 데이터 형식에서 대량의 데이터를 보유할 수 있습니다. 3 가지 방법으로이 데이터를 처리할 수 있습니다.  
  
-   에 바인딩합니다는 `CString` / `CByteArray`합니다.  
  
-   에 바인딩합니다는 `CLongBinary`합니다.  
  
-   전혀 바인딩 및 검색를 마십시오 보낼 긴 데이터 값을 수동으로 독립적 데이터베이스 클래스입니다.  
  
 세 가지 방법 중 각 장점 및 단점에 있습니다.  
  
 Long 데이터 열을 쿼리에 매개 변수에 대 한 지원 되지 않습니다. OutputColumns에만 지원 됩니다.  
  
## <a name="binding-a-long-data-column-to-a-cstringcbytearray"></a>CString/CByteArray에 대 한 Long 데이터 열 바인딩  
 장점  
  
 이 방법은 이해 하기 간단 하 고 친숙 한 클래스를 사용 합니다. 프레임 워크 제공 `CFormView` 에 대 한 지원 `CString` 와 `DDX_Text`합니다. 일반 문자열 또는 컬렉션 기능을 많은 `CString` 및 `CByteArray` 클래스 및 사용자 데이터 값을 포함 하는 로컬에 할당 된 메모리 양을 제어할 수 있습니다. 프레임 워크를 유지 관리 하는 동안 필드 데이터의 이전 복사본 **편집** 또는 `AddNew` 함수 호출 및 자동으로 데이터의 변경 내용을 사용자에 대 한 검색은 프레임 워크 될 수 있습니다.  
  
> [!NOTE]
>  이후 `CString` 작업 문자 데이터에 대 한 설계 및 `CByteArray` 이진 데이터를 사용 하는 것에 대 한 것이 좋습니다 문자 데이터를 넣으면 (**SQL_LONGVARCHAR**)에 `CString`, 및 이진 데이터 ( **SQL_LONGVARBINARY**)에 `CByteArray`합니다.  
  
 에 대 한 함수는 RFX `CString` 및 `CByteArray` 데이터 열에 대 한 검색 된 값을 보유할 할당 된 메모리의 기본 크기를 무시할 수 있는 추가 인수가 있어야 합니다. 다음 함수 선언에서 nMaxLength 인수 참고:  
  
```  
void AFXAPI RFX_Text(CFieldExchange* pFX,
    const char *szName,  
    CString& value,
    int nMaxLength = 255,
    int nColumnType = 
    SQL_VARCHAR);

 
void AFXAPI RFX_Binary(CFieldExchange* pFX,
    const char *szName,   
    CByteArray& value,
    int nMaxLength = 255);
```  
  
 에 대 한 long 데이터 열을 검색 하는 경우는 `CString` 또는 `CByteArray`, 최대 데이터 양은, 기본적으로 255 바이트를 반환 합니다. 이 여분의 무시 됩니다. 이 경우 프레임 워크에서는 예외를 throw **AFX_SQL_ERROR_DATA_TRUNCATED**합니다. 다행히 명시적으로 향상 시킬 수 있습니다 nMaxLength 값 보다 큰 값을 최대 **MAXINT**합니다.  
  
> [!NOTE]
>  NMaxLength의 값은 MFC를 설정할 때 사용의 로컬 버퍼는 **SQLBindColumn** 함수입니다. 이 데이터의 저장소에 대 한 로컬 버퍼 이며 ODBC 드라이버에서 반환 된 데이터의 양을 실제로 영향을 주지 않습니다. `RFX_Text` 및 `RFX_Binary` 만 사용 하 여 호출 하나를 만들어 **SQLFetch** 백 엔드 데이터베이스에서 데이터를 검색할 수 있습니다. 각 ODBC 드라이버의 단일 인출에서 반환할 수는 데이터 양에 대 다른 제한이 있습니다. 이 한도 있으며이 경우는 예외에 nMaxLength에 설정 된 값 보다 훨씬 더 작은 수 **AFX_SQL_ERROR_DATA_TRUNCATED** throw 됩니다. 이러한 상황에서는 사용 하도록 전환 `RFX_LongBinary` 대신 `RFX_Text` 또는 `RFX_Binary` 모든 데이터를 검색할 수 있도록 합니다.  
  
 클래스 마법사 바인딩합니다는 **SQL_LONGVARCHAR** 에 `CString`, 또는 **SQL_LONGVARBINARY** 에 `CByteArray` 드립니다. 검색할 수 있는 긴 데이터 열에 255 바이트 이상의 할당 하려는 경우 다음 nMaxLength에 명시적 값을 제공할 수 있습니다.  
  
 Long 데이터가 열에 바인딩된 경우는 `CString` 또는 `CByteArray`는 SQL_에 바인딩될 때와 동일 하 게 작동 하는 필드 업데이트 하 여**VARCHAR** 또는 SQL_**VARBINARY**합니다. 동안 **편집**, 데이터 값이 떨어져 있고 나중에 비교할 때 캐시 됩니다 **업데이트** 값 및는 Dirty 설정 및 Null 열에 대 한 값을 적절 하 게 데이터의 변경 내용을 감지 하기 위해 호출 됩니다.  
  
## <a name="binding-a-long-data-column-to-a-clongbinary"></a>Long 데이터 열을 CLongBinary에 바인딩  
 더 긴 데이터 열에 포함 될 수 있습니다 하는 경우 **MAXINT** 데이터의 바이트를 아마도 고려해 야로 검색 하는 `CLongBinary`합니다.  
  
 장점  
  
 최대 사용 가능한 메모리는 전체 긴 데이터 열을 검색합니다.  
  
 단점  
  
 데이터는 메모리에 유지 됩니다. 이 방법은 매우 많은 양의 데이터에 대 한 많은 비용이 들도 합니다. 호출 해야 `SetFieldDirty` 바인딩된 데이터 필드를 확인 하는 멤버에 포함 되는 **업데이트** 작업 합니다.  
  
 에 대 한 long 데이터 열을 검색 하는 경우는 `CLongBinary`, 데이터베이스 클래스 긴 데이터 열의 전체 크기를 확인 한 후 할당가 `HGLOBAL` 전체 데이터 값을 보유할 수 있을 만큼 큰 메모리 세그먼트입니다. 데이터베이스 클래스에 할당 된 다음 전체 데이터 값을 검색 `HGLOBAL`합니다.  
  
 데이터 소스는 긴 데이터 열의 예상된 크기를 반환할 수 없습니다, 프레임 워크는 예외를 throw 합니다 **AFX_SQL_ERROR_SQL_NO_TOTAL**합니다. 경우 할당 하지는 `HGLOBAL` 실패 하면 표준 메모리 예외가 throw 됩니다.  
  
 클래스 마법사 바인딩합니다는 **SQL_LONGVARCHAR** 또는 **SQL_LONGVARBINARY** 에 `CLongBinary` 드립니다. 선택 `CLongBinary` 멤버 변수 추가 대화 상자에서 변수 형식으로. 클래스 마법사는 다음 추가 `RFX_LongBinary` 에 대 한 호출 프로그램 `DoFieldExchange` 호출 하 고 바인딩된 필드의 총 수를 증가 시킵니다.  
  
 긴 데이터 열 값을 업데이트 하려면 먼저 있어야 할당 된 `HGLOBAL` 호출 하 여 새 데이터를 저장할 수 있도록 충분히 큰 **:: GlobalSize** 에 `m_hData` 의 멤버는 `CLongBinary`합니다. 너무 작으면 릴리스는 `HGLOBAL` 하나 적절 한 크기를 할당 하 고 있습니다. 다음 설정 `m_dwDataLength` 새 크기를 반영 하도록 합니다.  
  
 그렇지 않은 경우, `m_dwDataLength` 크기 보다 크면 대체 하는 데이터의 있습니다 수 하거나 해제 하 고 다시 할당는 `HGLOBAL`, 또는 할당 된 두세요. 에 실제로 사용 된 바이트 수를 지정 해야 `m_dwDataLength`합니다.  
  
## <a name="how-updating-a-clongbinary-works"></a>어떻게 업데이트는 CLongBinary 작동  
 이해할 필요는 없습니다 어떻게 업데이트는 `CLongBinary` 작동 하지만 데이터 원본에 긴 데이터 값을 보내는 방법에 대 한 예로 유용할 수 있습니다이 세 번째 메서드에 아래에 설명 된 경우 선택 합니다.  
  
> [!NOTE]
>  되려면에서는 `CLongBinary` 필드는 업데이트에 포함 되도록 명시적으로 호출 해야 `SetFieldDirty` 필드에 대 한 합니다. 호출 해야 Null 설정을 포함 하는 필드를 변경 하는 경우 `SetFieldDirty`합니다. 도 호출 해야 `SetFieldNull`, 되 고 두 번째 매개 변수 **FALSE**, 필드 값을 가진 것으로 표시 합니다.  
  
 업데이트할 때는 `CLongBinary` 데이터베이스 클래스가 사용 하는 ODBC의 필드 **DATA_AT_EXEC** 메커니즘 (ODBC 설명서를 참조 하십시오 **SQLSetPos**의 rgbValue 인수). 프레임 워크에서 insert 또는 update 문의 가리키는 대신를 준비 하는 경우는 `HGLOBAL` 데이터를 포함 하는 *주소* 의 `CLongBinary` 으로 설정 된 *값* 열의 대신, 길이 표시기로 설정 하 고 **SQL_DATA_AT_EXEC**합니다. 나중에 데이터 소스에 update 문을 보내집니다 **SQLExecDirect** 돌아갑니다 **SQL_NEED_DATA**합니다. 이 열에 대 한 매개 변수 값의 주소가 실제로 인지 프레임 워크가이 경고는 `CLongBinary`합니다. 프레임 워크를 호출 하 여 **SQLGetData** 한 번 작은 버퍼로 데이터의 실제 길이 반환 하는 드라이버를 예상 합니다. 이진 대형 개체 (BLOB)의 실제 길이 반환 하는 드라이버, MFC 다시 BLOB 인출 하는 데 필요한 많은 공간을 할당 합니다. 데이터 원본 반환 **SQL_NO_TOTAL**, BLOB의 크기를 확인할 수 없음을 나타내는, MFC 만들어집니다 작은 블록입니다. 기본 초기 크기는 64k 및 후속 블록 크기의 두 배; 됩니다. 예를 들어 두 번째 128k 됩니다, 그리고 세 번째는 256 K, 및 기타 등등. 초기 크기는 구성할 수 있습니다.  
  
## <a name="not-binding-retrievingsending-data-directly-from-odbc-with-sqlgetdata"></a>바인딩 하지: 검색/데이터 보내기 SQLGetData 사용 하 여 ODBC에서 직접  
 이 방법을 사용 하면 완전히 데이터베이스 클래스를 무시 하 고 긴 데이터 열과 처리 합니다.  
  
 장점  
  
 필요한 경우 디스크 또는 동적으로 데이터 양을 결정 검색할 데이터를 캐시할 수 있습니다.  
  
 단점  
  
 프레임 워크의를 얻지 **편집** 또는 `AddNew` 지원 하 고 작성 해야 코드를 직접 기본 기능을 수행 하도록 (**삭제** 의 작동 하지만 열 수준 작업 이기 때문).  
  
 이 경우 긴 데이터 열은 레코드 집합의 select 목록에 있어야 하지만 프레임 워크에서에 바인딩되어 있지 해야 합니다. 작업을 수행 하는 한 가지 방법은이 통해 직접 SQL 문을 제공 `GetDefaultSQL` 또는 lpszSQL 인수로 `CRecordset`의 **열려** 함수 및 바인딩할 RFX_ 함수 호출으로 별도 열입니다. ODBC 바인딩되지 않은 필드가 바인딩된 필드의 오른쪽에 나타나도록 해야 하므로 select 목록의 끝에 바인딩되지 않은 열 또는 열을 추가 하세요.  
  
> [!NOTE]
>  변경 내용을와 처리 되지 않으며 프레임 워크에서 긴 데이터 열에 바인딩되어 있지 않아서, `CRecordset::Update` 호출 합니다. 만들고 필요한 SQL 송신 해야 **삽입** 및 **업데이트** 문을 직접 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

