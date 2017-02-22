---
title: "레코드 집합: 레코드 집합 만들기 및 닫기(ODBC) | Microsoft Docs"
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
  - "ODBC 레코드 집합, 닫기"
  - "ODBC 레코드 집합, 만들기"
  - "ODBC 레코드 집합, 열기"
  - "레코드 집합, 닫기"
  - "레코드 집합, 만들기"
  - "레코드 집합, 열기"
ms.assetid: 8d2aac23-4396-4ce2-8c60-5ecf1b360d3d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 레코드 집합: 레코드 집합 만들기 및 닫기(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 MFC ODBC 클래스에 적용됩니다.  
  
 레코드 집합을 사용하려면 레코드 집합 개체를 생성한 다음 해당 개체의 **Open** 멤버 함수를 호출하여 레코드 집합의 쿼리를 실행하고 레코드를 선택합니다.  레코드 집합을 다 사용한 후에는 개체를 닫고 삭제합니다.  
  
 다음은 이 항목에서 설명하는 내용입니다.  
  
-   [레코드 집합 개체를 만드는 방법 및 시기](#_core_creating_recordsets_at_run_time)  
  
-   [매개 변수화, 필터, 정렬 또는 잠금을 사용한 레코드 집합 동작 제어 방법 및 시기](#_core_setting_recordset_options)  
  
-   [레코드 집합 개체를 닫는 방법 및 시기](#_core_closing_a_recordset)  
  
##  <a name="_core_creating_recordsets_at_run_time"></a> 런타임에 레코드 집합 만들기  
 대부분의 경우 프로그램에서 레코드 집합 개체를 만들려면 먼저 해당 응용 프로그램과 관련된 레코드 집합 클래스를 작성해야 합니다.  이러한 예비 단계에 대한 자세한 내용은 [MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md)를 참조하십시오.  
  
 데이터 소스에서 레코드를 선택해야 하면 다이너셋 또는 스냅숏을 엽니다.  만들 개체의 형식은 응용 프로그램에서 데이터를 이용해서 수행할 작업과 ODBC 드라이버가 지원하는 내용에 따라 달라집니다.  자세한 내용은 [다이너셋](../../data/odbc/dynaset.md) 및 [스냅숏](../../data/odbc/snapshot.md)을 참조하십시오.  
  
#### 레코드 집합을 열려면  
  
1.  `CRecordset`에서 파생된 클래스의 개체를 생성합니다.  
  
     힙 또는 함수의 스택 프레임에 개체를 생성할 수 있습니다.  
  
2.  선택적으로 기본 레코드 집합의 동작을 수정합니다.  사용 가능한 옵션에 대해서는 [레코드 집합 옵션 설정](#_core_setting_recordset_options)을 참조하십시오.  
  
3.  해당 개체의 [Open](../Topic/CRecordset::Open.md) 멤버 함수를 호출합니다.  
  
 생성자에서 `CDatabase` 개체에 대한 포인터를 전달합니다. 또는 [GetDefaultConnect](../Topic/CRecordset::GetDefaultConnect.md) 멤버 함수에서 반환되는 연결 문자열을 기준으로 프레임워크에서 임시 데이터베이스 개체를 생성하여 열게 하려면 **NULL**을 전달합니다.  `CDatabase` 개체는 데이터 소스에 이미 연결되었을 수 있습니다.  
  
 **Open** 호출에서 SQL을 사용하여 데이터 소스에서 레코드를 선택합니다.  선택된 첫째 레코드\(있는 경우\)가 현재 레코드입니다.  이 레코드 필드의 값은 레코드 집합 개체의 필드 데이터 멤버에 저장됩니다.  레코드가 선택되었으면 `IsBOF` 및 `IsEOF` 멤버 함수 모두에서 0이 반환됩니다.  
  
 [Open](../Topic/CRecordset::Open.md) 호출에서 다음과 같이 지정할 수 있습니다.  
  
-   레코드 집합이 다이너셋인지 스냅숏인지 지정합니다.  기본적으로 레코드 집합은 스냅숏으로 열립니다.  레코드를 한 번에 하나씩 앞으로만 스크롤할 수 있는 앞으로만 이동 가능한 레코드 집합을 지정할 수도 있습니다.  
  
     기본적으로 레코드 집합은 `CRecordset` 데이터 멤버 **m\_nDefaultType**에 저장된 기본 형식을 사용합니다.  마법사에서는 사용자가 선택한 레코드 집합 형식으로 **m\_nDefaultType**을 초기화하는 코드를 작성합니다.  이 기본값을 적용하지 않고 다른 레코드 집합 형식을 지정할 수도 있습니다.  
  
-   레코드 집합에서 생성된 기본 SQL **SELECT** 문을 대체하는 문자열을 지정합니다.  
  
-   레코드 집합이 읽기 전용인지 또는 추가 전용인지 지정합니다.  기본적으로 레코드 집합은 전체 업데이트가 가능하지만 새 레코드만을 추가하도록 제한하거나 모든 업데이트를 허용하지 않을 수도 있습니다.  
  
 다음 예제에서는 응용 프로그램 고유의 클래스인 `CStudentSet`의 읽기 전용 스냅숏 개체를 여는 방법을 보여 줍니다.  
  
```  
// Construct the snapshot object  
CStudentSet rsStudent( NULL );  
// Set options if desired, then open the recordset  
if(!rsStudent.Open(CRecordset::snapshot, NULL, CRecordset::readOnly))  
    return FALSE;  
// Use the snapshot to operate on its records...  
```  
  
 **Open**을 호출한 다음 개체의 멤버 함수와 데이터 멤버를 사용하여 레코드 작업을 수행합니다.  경우에 따라 데이터 소스에서 발생한 변경 내용을 포함하도록 레코드 집합을 다시 쿼리하거나 새로 고칠 수 있습니다.  자세한 내용은 [레코드 집합: 레코드 집합 다시 쿼리\(ODBC\)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)를 참조하십시오.  
  
> [!TIP]
>  개발하는 동안 사용하는 연결 문자열은 최종 사용자에게 필요하지 않을 수도 있습니다.  이런 점과 관련하여 응용 프로그램을 일반화하는 데 대한 정보는 [데이터 소스: 연결 관리\(ODBC\)](../../data/odbc/data-source-managing-connections-odbc.md)를 참조하십시오.  
  
##  <a name="_core_setting_recordset_options"></a> 레코드 집합 옵션 설정  
 레코드 집합 개체를 생성한 후 **Open**을 호출하여 레코드를 선택하기 전에 레코드 집합의 동작을 제어하기 위한 몇 가지 옵션을 설정할 수 있습니다.  모든 레코드 집합에 대해 다음과 같이 지정할 수 있습니다.  
  
-   레코드 선택을 제한하는 [필터](../../data/odbc/recordset-filtering-records-odbc.md)를 지정합니다.  
  
-   레코드에 대한 [정렬](../../data/odbc/recordset-sorting-records-odbc.md) 순서를 지정합니다.  
  
-   런타임에 가져오거나 계산된 정보를 사용하여 레코드를 선택할 수 있도록 [매개 변수](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)를 지정합니다.  
  
 적절한 경우 다음과 같은 옵션을 설정할 수도 있습니다.  
  
-   레코드 집합이 업데이트 가능하고 잠금 옵션을 지원하는 경우 업데이트에 사용할 [잠금](../../data/odbc/recordset-locking-records-odbc.md) 방법을 지정합니다.  
  
> [!NOTE]
>  이러한 설정이 레코드 선택에 적용되도록 하려면 **Open** 멤버 함수를 호출하기 전에 옵션을 설정해야 합니다.  
  
##  <a name="_core_closing_a_recordset"></a> 레코드 집합 닫기  
 레코드 집합에 대한 작업을 마치면 레코드 집합을 닫아 메모리 할당을 취소해야 합니다.  
  
#### 레코드 집합을 닫으려면  
  
1.  레코드 집합의 [Close](../Topic/CRecordset::Close.md) 멤버 함수를 호출합니다.  
  
2.  레코드 집합 개체를 삭제합니다.  
  
     레코드 집합을 함수의 스택 프레임에 선언한 경우 개체는 범위를 벗어날 때 자동으로 삭제됩니다.  그렇지 않으면 **delete** 연산자를 사용하여 삭제해야 합니다.  
  
 **Close**를 호출하면 레코드 집합의 **HSTMT** 핸들은 해제되지만  C\+\+ 개체는 삭제되지 않습니다.  
  
## 참고 항목  
 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 스크롤\(ODBC\)](../../data/odbc/recordset-scrolling-odbc.md)   
 [레코드 집합: 레코드 추가, 업데이트 및 삭제\(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)