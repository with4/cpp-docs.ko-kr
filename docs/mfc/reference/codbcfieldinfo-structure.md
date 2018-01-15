---
title: "CODBCFieldInfo 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CODBCFieldInfo
dev_langs: C++
helpviewer_keywords:
- ODBC [MFC], data source information
- CODBCFieldInfo structure [MFC]
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5b2b5d707b9915aa0d5e3fd1362746fe30a99a22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="codbcfieldinfo-structure"></a>CODBCFieldInfo 구조체
`CODBCFieldInfo` 구조는 ODBC 데이터 원본에 있는 필드에 대 한 정보를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct CODBCFieldInfo  
{  
    CString m_strName;  
    SWORD m_nSQLType;  
    UDWORD m_nPrecision;  
    SWORD m_nScale;  
    SWORD m_nNullability;  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 `m_strName`  
 @FSHO2@필드의 이름입니다.  
  
 *m_nSQLType*  
 필드의 SQL 데이터 형식입니다. 이 ODBC SQL 데이터 형식이 나 드라이버별 SQL 데이터 형식과 수 있습니다. 목록이 유효한 ODBC SQL 데이터 형식에 대 한 Windows SDK의 "SQL 데이터 형식"을 참조 하십시오. 드라이버별 SQL 데이터 형식에 대 한 내용은 드라이버의 설명서를 참조 하십시오.  
  
 *m_nPrecision*  
 필드의 최대 전체 자릿수입니다. 자세한 내용은 Windows SDK의 "전체 자릿수, 소수 자릿수, 길이 및 표시 크기"를 참조 합니다.  
  
 *m_nScale*  
 필드의 소수 자릿수입니다. 자세한 내용은 Windows SDK의 "전체 자릿수, 소수 자릿수, 길이 및 표시 크기"를 참조 합니다.  
  
 *m_nNullability*  
 필드에 Null 값을 수락할지 여부. 두 값 중 하나일 수 있습니다이: **SQL_NULLABLE** 필드에서 Null 값을 허용 하는 경우 또는 **SQL_NO_NULLS** 필드는 Null 값을 허용 하지 않는 경우.  
  
## <a name="remarks"></a>설명  
 이 정보를 검색 하려면 [CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdb.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)   
 [CRecordset::GetFieldValue](../../mfc/reference/crecordset-class.md#getfieldvalue)


