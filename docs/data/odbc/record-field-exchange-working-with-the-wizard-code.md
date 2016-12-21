---
title: "레코드 필드 교환: 마법사 코드 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DoFieldExchange 메서드, 재정의"
  - "필드 데이터 멤버"
  - "필드 데이터 멤버, 선언"
  - "m_nFields 데이터 멤버"
  - "m_nFields 데이터 멤버, 초기화"
  - "m_nParams 데이터 멤버"
  - "m_nParams 데이터 멤버, 초기화"
  - "ODBC, RFX"
  - "재정의, DoFieldExchange"
  - "RFX(ODBC), 구현"
  - "RFX(ODBC), 마법사 코드"
  - "Unicode, 데이터베이스 클래스 사용"
ms.assetid: f00d882a-ff1b-4a75-9717-98d8762bb237
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 레코드 필드 교환: 마법사 코드 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 MFC 응용 프로그램 마법사 및 **클래스 추가**\([MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md)에서 설명\)에서 RFX를 지원하기 위해 작성하는 코드를 설명하고 이 마법사 코드를 수정하는 방법을 설명합니다.  
  
> [!NOTE]
>  이 항목은 대량 행 페치가 구현되지 않은 `CRecordset`에서 파생된 클래스에 적용됩니다.  대량 행 페치를 사용하는 경우 Bulk RFX\(대량 레코드 필드 교환\)가 구현됩니다.  Bulk RFX는 RFX와 비슷합니다.  차이점을 이해하려면 [레코드 집합: 대량 레코드 페치\(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)를 참조하십시오.  
  
 MFC 응용 프로그램 마법사 또는 **클래스 추가**를 사용하여 레코드 집합 클래스를 만들면 선택한 데이터 소스와 테이블 및 열을 기반으로 다음과 같은 RFX 관련 요소들을 마법사가 작성합니다.  
  
-   레코드 집합 클래스에서 레코드 집합 필드 데이터 멤버 선언  
  
-   `CRecordset::DoFieldExchange`의 재정의  
  
-   레코드 집합 클래스 생성자에서 레코드 집합 필드 데이터 멤버 초기화  
  
##  <a name="_core_the_field_data_member_declarations"></a> 필드 데이터 멤버 선언  
 마법사는 .h 파일에서 `CSections` 클래스에 대해 다음과 같은 레코드 집합 클래스 선언을 작성합니다.  
  
```  
class CSections : public CRecordset  
{  
public:  
   CSections(CDatabase* pDatabase = NULL);  
   DECLARE_DYNAMIC(CSections)  
  
// Field/Param Data  
   CString   m_strCourseID;  
   CString   m_strInstructorID;  
   CString   m_strRoomNo;  
   CString   m_strSchedule;  
   CString   m_strSectionNo;  
  
// Overrides  
   // Wizard generated virtual function overrides  
   protected:  
   virtual CString GetDefaultConnect();  // Default connection string  
   virtual CString GetDefaultSQL();      // Default SQL for Recordset  
   virtual void DoFieldExchange(CFieldExchange* pFX);  // RFX support  
  
// Implementation  
#ifdef _DEBUG  
   virtual void AssertValid() const;  
   virtual void Dump(CDumpContext& dc) const;  
#endif  
  
};  
```  
  
 바인딩할 매개 변수 데이터 멤버 또는 새 필드 데이터 멤버를 사용자가 직접 추가하는 경우에는 마법사가 해당 데이터 멤버를 생성한 다음에 추가해야 합니다.  
  
 또한 마법사는 `CRecordset` 클래스의 `DoFieldExchange` 멤버 함수를 재정의하기도 합니다.  
  
##  <a name="_core_the_dofieldexchange_override"></a> DoFieldExchange 재정의  
 [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md)는 RFX의 핵심 요소입니다.  프레임워크는 데이터 소스에서 레코드 집합으로 또는 레코드 집합에서 데이터 소스로 데이터를 옮기는 데 필요할 때마다 `DoFieldExchange`를 호출합니다.  `DoFieldExchange`는 [IsFieldDirty](../Topic/CRecordset::IsFieldDirty.md) 및 [IsFieldNull](../Topic/CRecordset::IsFieldNull.md) 멤버 함수를 통해 필드 데이터 멤버에 대한 정보도 가져옵니다.  
  
 다음은 `CSections` 클래스에 대한 `DoFieldExchange`재정의의 예입니다.  마법사는 .cpp 파일에 레코드 집합 클래스에 대한 함수를 작성합니다.  
  
```  
void CSections::DoFieldExchange(CFieldExchange* pFX)  
{  
   pFX->SetFieldType(CFieldExchange::outputColumn);  
   RFX_Text(pFX, "CourseID", m_strCourseID);  
   RFX_Text(pFX, "InstructorID", m_strInstructorID);  
   RFX_Text(pFX, "RoomNo", m_strRoomNo);  
   RFX_Text(pFX, "Schedule", m_strSchedule);  
   RFX_Text(pFX, "SectionNo", m_strSectionNo);  
}  
```  
  
 다음은 이 함수의 핵심적인 특징입니다.  
  
-   DoFieldExchange 함수의 이 섹션은 필드 맵이라고 합니다.  
  
-   `pFX` 포인터를 통해 `CFieldExchange::SetFieldType`을 호출합니다.  이 호출에서는 `DoFieldExchange` 마지막 부분에서 모든 RFX 함수가 호출되며 `SetFieldType`의 다음 호출이 output column임을 지정합니다.  자세한 내용은 [CFieldExchange::SetFieldType](../Topic/CFieldExchange::SetFieldType.md)을 참조하십시오.  
  
-   각 필드 데이터 멤버마다 한 번씩 `RFX_Text` 전역 함수를 여러 번 호출합니다\(이 예제에서는 모두 `CString` 변수\).  이 호출은 데이터 소스의 열 이름과 필드 데이터 멤버 사이의 관계를 지정합니다.  RFX 함수는 데이터를 실제로 전달합니다.  클래스 라이브러리는 일반 데이터 형식 모두에 대해 RFX 함수를 제공합니다.  RFX 함수에 대한 자세한 내용은 [레코드 필드 교환: RFX 함수 사용](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)을 참조하십시오.  
  
    > [!NOTE]
    >  결과 집합의 열 순서는 `DoFieldExchange`의 RFX 함수 호출 순서와 일치해야 합니다.  
  
-   프레임워크에서 `DoFieldExchange`를 호출하는 경우 [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) 개체에 대한 `pFX` 포인터가 전달됩니다.  `CFieldExchange` 개체는 `DoFieldExchange`가 수행할 작업과 전송 방향 및 기타 컨텍스트 정보를 지정합니다.  
  
##  <a name="_core_the_recordset_constructor"></a> 레코드 집합 생성자  
 마법사가 작성한 레코드 집합 생성자에는 RFX 관련 사항이 두 가지 포함됩니다.  
  
-   각 필드 데이터 멤버의 초기화  
  
-   픨드 데이터 멤버의 수가 들어 있는 [CRecordset::m\_nFields](../Topic/CRecordset::m_nFields.md) 데이터 멤버의 초기화  
  
 `CSections` 레코드 집합 생성자의 예제는 다음과 같습니다.  
  
```  
CSections::CSections(CDatabase* pdb)  
   : CRecordset(pdb)  
{  
   m_strCourseID = "";  
   m_strInstructorID = "";  
   m_strRoomNo = "";  
   m_strSchedule = "";  
   m_strSectionNo = "";  
   m_nFields = 5;  
}  
```  
  
> [!NOTE]
>  필드 데이터 멤버를 직접 추가하는 경우에는 새 열을 동적으로 바인딩할 때와 마찬가지로 `m_nFields`의 값을 증가시켜야 합니다.  이렇게 하려면 다음과 같은 줄을 코드에 추가합니다.  
  
```  
m_nFields += 3;  
```  
  
 이 코드는 세 개의 필드를 새로 추가합니다.  매개 변수 데이터 멤버를 추가하는 경우 매개 변수 데이터 멤버의 수를 포함하는 [m\_nParams](../Topic/CRecordset::m_nParams.md) 데이터 멤버를 초기화해야 합니다.  `m_nParams` 초기화는 괄호 밖에 배치합니다.  
  
## 참고 항목  
 [RFX](../../data/odbc/record-field-exchange-rfx.md)