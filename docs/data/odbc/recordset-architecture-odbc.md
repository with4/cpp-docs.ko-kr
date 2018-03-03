---
title: "레코드 집합: 아키텍처 (ODBC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- recordsets, data members
- field data members, recordset architecture
- field data members
- m_nParams data member, recordsets
- recordsets, architecture
- parameter data members in recordsets
- m_nFields data member
- ODBC recordsets, architecture
- m_nParams data member
- m_nFields data member, recordsets
ms.assetid: 47555ddb-11be-4b9e-9b9a-f2931764d298
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 169d371327137cf4f51ed10429eb5e9708a0e088
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-architecture-odbc"></a>레코드 집합: 아키텍처(ODBC)
MFC ODBC 클래스에이 항목에 적용 됩니다.  
  
 이 항목에서는 레코드 집합 개체의 아키텍처를 구성 하는 데이터 멤버를 설명 합니다.  
  
-   [필드 데이터 멤버](#_core_field_data_members)  
  
-   [매개 변수 데이터 멤버](#_core_parameter_data_members)  
  
-   [M_nFields 및 m_nParams 데이터 멤버 사용](#_core_using_m_nfields_and_m_nparams)  
  
> [!NOTE]
>  이 항목에서 파생 된 개체에 적용 됩니다. `CRecordset` 에서 대량 행 페치 구현 되지 않았습니다. 대량 행 페치를 구현 하는 경우에 아키텍처가 비슷합니다. 차이점을 이해 하려면 참조 [레코드 집합: 레코드 페치 대량 (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.  
  
##  <a name="_core_a_sample_class"></a>샘플 클래스  
 사용 하는 경우는 [MFC ODBC 소비자 마법사](../../mfc/reference/adding-an-mfc-odbc-consumer.md) 에서 **클래스 추가** 레코드 집합 클래스를 선언 하는 마법사에서 파생 된 `CRecordset`, 결과 클래스에는 다음과 같이 간단한 일반 구조 클래스:  
  
```  
class CCourse : public CRecordset  
{  
public:  
   CCourse(CDatabase* pDatabase = NULL);  
   ...  
   CString m_strCourseID;  
   CString m_strCourseTitle;  
   CString m_strIDParam;  
};  
```  
  
 클래스의 시작 부분에서 마법사는 집합을 작성 [필드 데이터 멤버](#_core_field_data_members)합니다. 클래스를 만들 때 하나 이상의 필드 데이터 멤버를 지정 해야 합니다. 샘플으로 클래스는 클래스에 매개 변수가 있으면 (데이터 멤버와 `m_strIDParam`)를 수동으로 추가 해야 [매개 변수 데이터 멤버](#_core_parameter_data_members)합니다. 마법사에서 클래스에는 매개 변수 추가 지원 하지 않습니다.  
  
##  <a name="_core_field_data_members"></a>필드 데이터 멤버  
 레코드 집합 클래스의 가장 중요 한 멤버는 필드 데이터 멤버입니다. 데이터 원본에서 선택한 각 열에 대 한 클래스는 해당 열에 대 한 적절 한 데이터 형식의 데이터 멤버를 포함 합니다. 예를 들어는 [샘플 클래스](#_core_a_sample_class) 이 맨 앞에 표시 된 항목 형식의 모두 두 명의 필드 데이터 멤버에 `CString`라는 `m_strCourseID` 및 `m_strCourseTitle`합니다.  
  
 프레임 워크는 현재 레코드의 열을 자동으로 바인딩하는 레코드를 레코드 집합을 선택 합니다 (후의 **열려** 호출에서 첫 번째 레코드를) 개체의 필드 데이터 멤버에 있습니다. 즉, 프레임 워크 레코드 열의 내용을 저장 하는 버퍼와 해당 필드 데이터 멤버를 사용 합니다.  
  
 사용자가 새 레코드를 스크롤할 프레임 워크를 사용 하 여 필드 데이터 멤버 현재 레코드를 표시 합니다. 프레임 워크를 바꿀 값이 이전 레코드의 필드 데이터 멤버를 새로 고칩니다. 필드 데이터 멤버는 현재 레코드를 업데이트 하 고 새 레코드를 추가 하는 데에 사용 됩니다. 레코드를 업데이트 하는 과정의 일환으로, 해당 필드 데이터 멤버 또는 멤버에 직접 값을 할당 하 여 업데이트 값을 지정 합니다.  
  
##  <a name="_core_parameter_data_members"></a>매개 변수 데이터 멤버  
 클래스에 매개 변수가 있으면 하나 이상의 매개 변수 데이터 멤버에 있습니다. 매개 변수가 있는 클래스를 사용 하면 쿼리의 기반으로 레코드 집합 가져오거나 런타임 시 계산 정보 수 있습니다.  
  
 일반적으로 매개 변수는 다음 예제와 같이 선택 항목을 줄일 수 있습니다. 에 따라는 [샘플 클래스](#_core_a_sample_class) 이 항목의 시작 부분에서 레코드 집합 개체는 다음 SQL 문을 실행 합니다.  
  
```  
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = ?  
```  
  
 "?"는 런타임 시 제공 하는 매개 변수 값에 대 한 자리 표시자입니다. 레코드 집합을 생성할 때 설정 하 고 해당 `m_strIDParam` MATH101 데이터 멤버, 레코드 집합에 대 한 효율적인 SQL 문이 됩니다:  
  
```  
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = MATH101  
```  
  
 매개 변수 데이터 멤버를 정의 하 여 SQL 문자열의 매개 변수에 대 한 프레임 워크를 지시 합니다. 프레임 워크에는 매개 변수를 자리 표시자를 대체할 값을 가져올 위치 알 ODBC를 바인딩합니다. 예제에서는 결과 레코드 집합의 값은 MATH101 CourseID 열이 있는 Course 테이블에서 레코드에만 포함 합니다. 이 레코드의 모든 지정 된 열을 선택 합니다. 많은 매개 변수 (및 자리 표시자)을 지정할 수 있습니다 필요에 따라 합니다.  
  
> [!NOTE]
>  매개 변수를 가진도 MFC는 자체 아무 작업도 수행-특히 텍스트 대체를 수행 하지 않습니다. 대신 ODBC에 알려; 매개 변수를 가져올 위치 ODBC는 데이터를 검색 하 고 필요한 매개 변수화를 수행 합니다.  
  
> [!NOTE]
>  매개 변수 순서가 중요 합니다. 이 대 한 정보와 매개 변수에 대 한 자세한 내용은 참조 하세요. [레코드 집합: 레코드 집합 (ODBC)를 매개 변수화](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)합니다.  
  
##  <a name="_core_using_m_nfields_and_m_nparams"></a>M_nFields 및 m_nParams 사용 하 여  

 마법사 클래스에 대 한 생성자를 쓰려면 때 초기화는 [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) 데이터 멤버의 수를 지정 하는 [필드 데이터 멤버](#_core_field_data_members) 클래스에 있습니다. 추가 하는 경우 [매개 변수](#_core_parameter_data_members) 클래스에 추가 해야에 대 한 초기화는 [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams) 데이터 멤버를 매개 변수 데이터 멤버의 수를 지정 합니다. 프레임 워크 데이터 멤버와 함께 작동 하도록 이러한 값을 사용 합니다.  
  
 자세한 내용 및 예제에 대 한 참조 [레코드 필드 교환: RFX 사용](../../data/odbc/record-field-exchange-using-rfx.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 테이블 (ODBC)에 대 한 클래스 선언](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)   
 [RFX(레코드 필드 교환)](../../data/odbc/record-field-exchange-rfx.md)