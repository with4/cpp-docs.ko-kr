---
title: "CLongBinary 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CLongBinary
- AFXDB_/CLongBinary
- AFXDB_/CLongBinary::CLongBinary
- AFXDB_/CLongBinary::m_dwDataLength
- AFXDB_/CLongBinary::m_hData
dev_langs:
- C++
helpviewer_keywords:
- BLOB (binary large object)
- CLongBinary class
- BLOB (binary large object), CLongBinary class
ms.assetid: f4320059-aeb4-4ee5-bc2b-25f19d898ef5
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: bb73604ee4d15f3a71be8514f348ad265064928a
ms.lasthandoff: 02/24/2017

---
# <a name="clongbinary-class"></a>CLongBinary 클래스
데이터베이스에서 매우 큰 이진 데이터 개체(BLOB 또는 "이진 대형 개체"라고도 함) 사용 작업을 간소화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CLongBinary : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CLongBinary::CLongBinary](#clongbinary)|`CLongBinary` 개체를 생성합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CLongBinary::m_dwDataLength](#m_dwdatalength)|실제 크기에 핸들 저장 된 데이터 개체의 바이트를 포함 `m_hData`합니다.|  
|[CLongBinary::m_hData](#m_hdata)|Windows 포함 `HGLOBAL` 실제 이미지 개체에 대 한 핸들입니다.|  
  
## <a name="remarks"></a>주의  
 예를 들어 SQL 테이블에서 레코드 필드에 그림을 나타내는 비트맵을 포함 될 수 있습니다. A `CLongBinary` 개체는 이러한 개체를 저장 하 고 크기는 추적 합니다.  
  
> [!NOTE]
>  일반적으로 것이 좋습니다 지금 사용 하 여 [CByteArray](../../mfc/reference/cbytearray-class.md) 함께에서 [DFX_Binary](http://msdn.microsoft.com/library/678021a3-2e46-44d7-8528-71bb692dcc07) 함수입니다. 사용할 수 없습니다 `CLongBinary`, 하지만 일반적 `CByteArray` 많은 기능을 제공 Win32에서 되므로 더 이상 발생 16 비트 크기 제한 `CByteArray`합니다. 개방형 데이터베이스 연결 (ODBC) 뿐만 아니라 데이터 액세스 개체 (DAO)를 사용한 프로그래밍에 적용이 가능 합니다.  
  
 사용 하는 `CLongBinary` 개체 형식의 필드 데이터 멤버를 선언 `CLongBinary` 레코드 집합 클래스에 있습니다. 이 멤버는 레코드 집합 클래스의 포함된 된 멤버 되며 레코드 집합 생성 될 때 생성 됩니다. 이후에 `CLongBinary` 개체가 생성 된 레코드 필드 교환 (RFX) 메커니즘 로드, 데이터 개체 데이터 소스에서 현재 레코드의 필드에서는 레코드가 업데이트 될 때 레코드에 다시 저장 합니다. RFX에 대 한 저장소를 할당 하는 이진 대형 개체의 크기에 대 한 데이터 소스를 쿼리 (통해는 `CLongBinary` 개체의 `m_hData` 데이터 멤버)를 저장 하 고는 `HGLOBAL` 의 데이터에 대 한 핸들 `m_hData`합니다. RFX 저장에서 데이터 개체의 실제 크기는 `m_dwDataLength` 데이터 멤버입니다. 통해 개체의 데이터로 작업 `m_hData`, 일반적으로 Windows에 저장 된 데이터를 조작 하는 데 사용할 수 같은 기술을 사용 하 여 `HGLOBAL` 처리 합니다.  
  
 포함된 된 레코드 집합을 삭제 하면 `CLongBinary` 개체도 소멸 하 고 해당 소멸자에서 할당 취소는 `HGLOBAL` 데이터 핸들입니다.  
  
 사용 하 여 큰 개체에 대 한 자세한 내용은 `CLongBinary`, 문서를 참조 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md) 및 [레코드 집합: 대형 데이터 항목 (ODBC)와 작업](../../data/odbc/recordset-working-with-large-data-items-odbc.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CLongBinary`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdb_.h  
  
##  <a name="clongbinary"></a>CLongBinary::CLongBinary  
 `CLongBinary` 개체를 생성합니다.  
  
```  
CLongBinary();
```  
  
##  <a name="m_dwdatalength"></a>CLongBinary::m_dwDataLength  
 실제 크기 (바이트)에 저장 된 데이터의 저장 된 `HGLOBAL` 에 처리할 `m_hData`.  
  
```  
SQLULEN m_dwDataLength;  
```  
  
### <a name="remarks"></a>주의  
 이 크기는 데이터에 할당 된 메모리 블록의 크기 보다 작을 수 있습니다. Win32 호출 [GLobalSize](http://msdn.microsoft.com/library/windows/desktop/aa366593) 함수 할당 된 크기를 가져옵니다.  
  
##  <a name="m_hdata"></a>CLongBinary::m_hData  
 Windows 저장 `HGLOBAL` 실제 이진 대형 개체 데이터에 대 한 핸들입니다.  
  
```  
HGLOBAL m_hData;  
```  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CRecordset 클래스](../../mfc/reference/crecordset-class.md)

