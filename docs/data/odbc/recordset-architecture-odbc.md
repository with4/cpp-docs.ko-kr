---
title: "레코드 집합: 아키텍처(ODBC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "필드 데이터 멤버"
  - "필드 데이터 멤버, 레코드 집합 아키텍처"
  - "m_nFields 데이터 멤버"
  - "m_nFields 데이터 멤버, 레코드 집합"
  - "m_nParams 데이터 멤버"
  - "m_nParams 데이터 멤버, 레코드 집합"
  - "ODBC 레코드 집합, 아키텍처"
  - "레코드 집합의 매개 변수 데이터 멤버"
  - "레코드 집합, 아키텍처"
  - "레코드 집합, 데이터 멤버"
ms.assetid: 47555ddb-11be-4b9e-9b9a-f2931764d298
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 레코드 집합: 아키텍처(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 MFC ODBC 클래스에 적용됩니다.  
  
 이 항목에서는 레코드 집합 개체의 아키텍처를 구성하는 데이터 멤버에 대해 설명합니다.  
  
-   [필드 데이터 멤버](#_core_field_data_members)  
  
-   [매개 변수 데이터 멤버](#_core_parameter_data_members)  
  
-   [m\_nFields 및 m\_nParams 데이터 멤버 사용](#_core_using_m_nfields_and_m_nparams)  
  
> [!NOTE]
>  이 항목은 대량 행 페치가 구현되지 않은 `CRecordset`에서 파생된 개체에 적용됩니다.  대량 행 페치가 구현되어 있는 경우에도 아키텍처는 유사합니다.  차이점을 이해하려면 [레코드 집합: 대량 레코드 페치\(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)를 참조하십시오.  
  
##  <a name="_core_a_sample_class"></a> 샘플 클래스  
 **클래스 추가 마법사**의 [MFC ODBC 소비자 마법사](../../mfc/reference/adding-an-mfc-odbc-consumer.md)를 사용하여 `CRecordset`에서 파생된 레코드 집합 클래스를 선언하면 다음과 같은 간단한 클래스의 구조와 유사한 클래스가 생성됩니다.  
  
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
  
 마법사에서는 클래스의 시작 부분에 [필드 데이터 멤버](#_core_field_data_members) 집합을 작성합니다.  클래스를 만드는 경우 하나 이상의 필드 데이터 멤버가 지정되어 있어야 합니다.  데이터 멤버 `m_strIDParam`이 포함된 위의 샘플 클래스와 같이 클래스에 매개 변수가 있으면 사용자가 직접 [매개 변수 데이터 멤버](#_core_parameter_data_members)를 추가해야 합니다.  마법사에서는 클래스에 매개 변수를 추가하는 기능을 지원하지 않습니다.  
  
##  <a name="_core_field_data_members"></a> 필드 데이터 멤버  
 레코드 집합 클래스에서 가장 중요한 멤버는 필드 데이터 멤버입니다.  클래스에는 데이터 소스에서 선택한 각 열에 적합한 데이터 형식의 데이터 멤버가 포함됩니다.  예를 들어 이 항목의 앞 부분에서 소개한 [샘플 클래스](#_core_a_sample_class)에는 `m_strCourseID`와 `m_strCourseTitle`이라고 하는 두 개의 필드 데이터 멤버가 있습니다. 데이터 형식은 둘 다 `CString`입니다.  
  
 레코드 집합이 일부 레코드를 선택하면 프레임워크는 자동으로 현재 레코드\(**Open**을 호출한 후 첫째 레코드가 현재 레코드\)의 열을 해당 개체의 필드 데이터 멤버에 바인딩합니다.  이것은 프레임워크에서 해당 필드 데이터 멤버를 레코드 열의 내용을 저장할 버퍼로 사용합니다.  
  
 사용자가 새 레코드로 스크롤하면 프레임워크에서 필드 데이터 멤버를 사용하여 현재 레코드를 표시합니다.  그런 다음 이전 레코드 값을 바꿔 필드 데이터 멤버를 새로 고칩니다.  필드 데이터 멤버는 또한 현재 레코드를 업데이트하고 새 레코드를 추가하기 위해 사용됩니다.  레코드 업데이트 과정 중에 해당 필드 데이터 멤버에 직접 값을 할당하여 업데이트 값을 지정합니다.  
  
##  <a name="_core_parameter_data_members"></a> 매개 변수 데이터 멤버  
 매개 변수가 있는 클래스는 하나 이상의 매개 변수 데이터 멤버를 포함합니다.  매개 변수가 있는 클래스를 이용하면 런타임에 가져오거나 계산된 정보를 기반으로 레코드 집합 쿼리를 만들 수 있습니다.  
  
 일반적으로 매개 변수를 사용하면 다음 예제와 같이 선택 항목을 줄일 수 있습니다.  이 항목의 시작 부분에 나오는 [샘플 클래스](#_core_a_sample_class)를 기반으로 레코드 집합 개체는 다음과 같은 SQL 문을 실행합니다.  
  
```  
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = ?  
```  
  
 "?"는 런타임에 제공하는 매개 변수 값의 자리 표시자입니다.  레코드 집합을 생성하고 해당 `m_strIDParam` 데이터 멤버를 MATH101로 설정하는 경우 레코드 집합에 유효한 SQL 문은 다음과 같습니다.  
  
```  
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = MATH101  
```  
  
 매개 변수 데이터 멤버를 정의하여 SQL 문자열에 있는 매개 변수에 대한 정보를 프레임워크에 알립니다.  프레임워크는 매개 변수를 바인딩하여 자리 표시자를 대체할 값을 가져올 위치를 ODBC에 알립니다.  예제에서 결과 레코드 집합에는 CourseID 열 값이 MATH101인 Course 테이블의 레코드만 포함됩니다.  이 레코드에서 지정된 모든 열이 선택됩니다.  필요한 개수 만큼 매개 변수와 자리 표시자를 지정할 수 있습니다.  
  
> [!NOTE]
>  MFC 자체는 매개 변수에 아무런 영향을 주지 않으며 특히 텍스트 대체와 같은 작업은 수행하지 않습니다.  대신에 매개 변수를 가져올 위치를 ODBC에 알려 ODBC에서 데이터를 검색하고 필요한 매개 변수화를 수행할 수 있도록 합니다.  
  
> [!NOTE]
>  매개 변수 순서가 중요한 경우.  매개 변수에 대한 이 내용 및 기타 자세한 내용은 [레코드 집합: 레코드 집합 매개 변수화\(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)를 참조하십시오.  
  
##  <a name="_core_using_m_nfields_and_m_nparams"></a> m\_nFields 및 m\_nParams 사용  
 마법사에서는 클래스의 생성자를 작성할 때 클래스의 [필드 데이터 멤버](#_core_field_data_members) 개수를 지정하는 [m\_nFields](../Topic/CRecordset::m_nFields.md) 데이터 멤버를 초기화합니다.  클래스에 [매개 변수](#_core_parameter_data_members)를 추가할 때는 매개 변수 데이터 멤버의 개수를 지정하는 [m\_nParams](../Topic/CRecordset::m_nParams.md) 데이터 멤버를 추가적으로 초기화해야 합니다.  프레임워크는 이러한 값을 사용하여 데이터 멤버 작업을 합니다.  
  
 자세한 내용 및 예제는 [레코드 필드 교환: RFX 사용](../../data/odbc/record-field-exchange-using-rfx.md)을 참조하십시오.  
  
## 참고 항목  
 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 테이블에 대한 클래스 선언\(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)   
 [RFX](../../data/odbc/record-field-exchange-rfx.md)