---
title: "레코드 집합: 데이터 열 동적 바인딩(ODBC) | Microsoft Docs"
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
  - "열[C++], 레코드 집합 바인딩"
  - "데이터 바인딩[C++], 레코드 집합의 열"
  - "데이터 바인딩[C++], 레코드 집합 열"
  - "ODBC 레코드 집합[C++], 동적으로 열 바인딩"
  - "레코드 집합[C++], 데이터 바인딩"
ms.assetid: bff67254-d953-4ae4-9716-91c348cb840b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 레코드 집합: 데이터 열 동적 바인딩(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 MFC ODBC 클래스에 적용됩니다.  
  
 레코드 집합은 디자인 타임에 지정된 테이블 열의 바인딩을 관리하지만 디자인 타임에 알 수 없는 열을 바인딩할 수도 있습니다.  다음은 이 항목에서 설명하는 내용입니다.  
  
-   [레코드 집합에 열을 동적으로 바인딩하는 시기](#_core_when_you_might_bind_columns_dynamically)  
  
-   [런타임에 열을 동적으로 바인딩하는 방법](#_core_how_to_bind_columns_dynamically)  
  
> [!NOTE]
>  이 항목은 대량 행 페치가 구현되지 않은 `CRecordset`에서 파생된 개체에 적용됩니다.  대량 행 페치를 사용할 때는 이 문서에서 일반적으로 설명하는 기술을 적용하지 않는 것이 좋습니다.  대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치\(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)를 참조하십시오.  
  
##  <a name="_core_when_you_might_bind_columns_dynamically"></a> 열을 동적으로 바인딩하는 시기  
 디자인 타임에 MFC 응용 프로그램 마법사나 [MFC ODBC 소비자 마법사](../../mfc/reference/adding-an-mfc-odbc-consumer.md)\(**클래스 추가**에서 사용\)는 데이터 소스의 테이블과 열을 기반으로 레코드 집합 클래스를 만듭니다.  런타임에 응용 프로그램에서 테이블과 열을 사용하는 경우 데이터베이스 내용이 디자인 당시와 다를 수 있습니다.  사용자 또는 다른 사용자가 응용 프로그램의 레코드 집합이 의존하는 테이블을 추가하거나 삭제할 수도 있고, 해당 테이블에서 열을 추가하거나 삭제할 수도 있습니다.  이러한 사항은 모든 데이터 액세스 응용 프로그램에 적용되지는 않지만 사용자 응용프로그램이 이러한 경우에 포함된다면 데이터베이스 스키마가 변경될 경우 다시 디자인하거나 컴파일하지 않아도 계속 사용할 수 있는 방법을 찾아야 합니다.  이 항목에서는 이러한 경우에 대처할 수 있는 방법을 제시합니다.  
  
 이 항목에서는 동적으로 열을 바인딩하는 가장 일반적인 경우, 즉 알려진 데이터베이스 스키마를 기반으로 레코드 집합을 시작한 후 런타임에 추가 열을 처리하는 경우에 대해 설명합니다.  또한 가장 일반적인 경우로 추가 열이 `CString` 필드 데이터 멤버에 매핑된다고 가정하며, 다른 데이터 형식을 관리하는 데 도움이 될 방법도 제시합니다.  
  
 예제 코드를 조금만 수정하면 다음과 같은 작업을 수행할 수 있습니다.  
  
-   [런타임에 사용 가능한 열 확인](#_core_to_determine_the_columns_in_a_table_at_run_time)  
  
-   [레코드 집합에 추가 열을 런타임에 동적으로 바인딩하기](#_core_adding_the_columns)  
  
 이 경우 레코드 집합에는 디자인 타임에 사용한 열에 대한 데이터 멤버가 포함됩니다.  또한, 대상 테이블에 새로 추가된 열이 있는지 여부를 동적으로 확인하고 추가된 열이 있으면 해당 열을 레코드 집합 데이터 멤버 대신 할당된 저장소에 동적으로 바인딩하는 약간의 추가 코드가 포함됩니다.  
  
 이 항목에서는 삭제된 테이블이나 열과 같은 다른 동적 바인딩 상황은 다루지 않습니다.  그러한 상황에서는 보다 직접적으로 ODBC API 호출을 사용해야 합니다.  자세한 내용은 MSDN LIBRARY CD에 있는 ODBC SDK Programmer's Reference를 참조하십시오.  
  
##  <a name="_core_how_to_bind_columns_dynamically"></a> 열을 동적으로 바인딩하는 방법  
 열을 동적으로 바인딩하려면 추가 열의 이름을 알고 있거나 확인할 수 있어야 합니다.  또한 추가 필드 데이터 멤버에 저장소를 할당하고, 이름과 형식을 지정하고 추가할 열의 개수를 지정해야 합니다.  
  
 아래에서는 두 가지 레코드 집합, 즉  대상 테이블에서 레코드를 선택하는 주 레코드 집합과  대상 테이블의 열에 대한 정보를 얻는 데 사용하는 특수한 열 레코드 집합입니다.  
  
###  <a name="_core_the_general_process"></a> 일반 절차  
 가장 일반적인 수준에서 다음 단계를 수행합니다.  
  
1.  주 레코드 집합 개체를 생성합니다.  
  
     선택에 따라서는 열려 있는 `CDatabase` 개체의 포인터를 전달하거나 다른 방법으로 연결 정보를 열 레코드 집합에 제공할 수도 있습니다.  
  
2.  동적으로 열을 추가하기 위한 단계를 수행합니다.  
  
     아래 "열 추가"에서 설명하는 프로세스를 참조하십시오.  
  
3.  주 레코드 집합을 엽니다.  
  
     레코드 집합에서는 레코드를 선택한 다음 RFX\(레코드 필드 교환\)를 사용하여 정적 열\(레코드 집합 필드 데이터 멤버에 매핑되는 열\) 및 동적 열\(할당하는 추가 저장소에 매핑되는 열\)을 모두 바인딩합니다.  
  
###  <a name="_core_adding_the_columns"></a> 열 추가  
 런타임에 추가 열을 동적으로 바인딩하려면 다음 단계를 수행해야 합니다.  
  
1.  대상 테이블에 있는 열을 런타임에 확인합니다.  이 정보에 기반하여 레코드 집합 클래스를 디자인한 이후 테이블에 추가된 열 목록을 추출합니다.  
  
     데이터 소스를 쿼리하여 열 이름, 데이터 형식 등과 같이 대상 테이블의 열 정보를 가져오도록 디자인된 열 레코드 집합 클래스를 사용하는 것이 좋습니다.  
  
2.  새 필드 데이터 멤버를 위한 저장소를 지정합니다.  주 레코드 집합 클래스에는 알려지지 않은 열에 대한 필드 데이터 멤버가 없으므로 이름, 결과 값 및 데이터 형식 정보\(열의 데이터 형식이 다른 경우\)를 저장하는 데 사용할 저장소를 지정해야 합니다.  
  
     이렇게 하려면 새 열의 이름, 결과 값, 데이터 형식\(필요한 경우\) 각각에 대해 하나 이상의 동적 목록을 만듭니다.  이러한 목록, 특히 값 목록은 바인딩에 필요한 저장소 및 정보를 제공합니다.  다음 그림은 목록을 만드는 방법을 보여 줍니다.  
  
     ![동적으로 바인딩할 열 목록 만들기](../../data/odbc/media/vc37w61.gif "vc37W61")  
동적으로 바인딩할 열 목록 만들기  
  
3.  추가되는 각 열에 대해 주 레코드 집합의 `DoFieldExchange` 함수에서 RFX 함수를 추가적으로 호출합니다.  이러한 RFX 호출은 추가 열을 포함하여 레코드를 페치하고, 레코드 집합 데이터 멤버 또는 열을 위해 동적으로 제공되는 저장소에 열을 바인딩합니다.  
  
     이를 위해 새 열 목록의 각 열에 대해 적절한 RFX 함수를 호출하면서 목록을 전체 반복하는 루프를 주 레코드 집합의 `DoFieldExchange` 함수에 추가합니다.  각 RFX 호출에서 열 이름 목록의 열 이름과 저장 위치를 결과 값 목록의 해당 멤버에 전달합니다.  
  
###  <a name="_core_lists_of_columns"></a> 열 목록  
 작업할 네 개의 목록은 다음과 같습니다.  
  
 [Current\-Table\-Columns\(그림의 목록 1\)](#_core_illustration_dynamic)  
 현재 데이터 소스의 테이블에 있는 열 목록.  This list might match the list of columns currently bound in your recordset.  
  
 [Bound\-Recordset\-Columns\(그림의 목록 2\)](#_core_illustration_dynamic)  
 레코드 집합에 있는 바인딩된 열 목록.  이러한 열은 이미 `DoFieldExchange` 함수에 RFX 문을 가지고 있습니다.  
  
 [Columns\-To\-Bind\-Dynamically\(그림의 목록 3\)](#_core_illustration_dynamic)  
 레코드 집합에는 없고 테이블에만 있는 열 목록.  이들은 동적으로 바인딩할 열입니다.  
  
 [Dynamic\-Column\-Values\(그림의 목록 4\)](#_core_illustration_dynamic)  
 동적 바인딩 대상 열에서 검색한 값에 대한 저장소를 포함하는 목록.  이 목록의 요소는 Columns\-to\-Bind\-Dynamically 목록의 요소와 일대일로 대응합니다.  
  
###  <a name="_core_building_your_lists"></a> 목록 만들기  
 일반적인 전략을 세운 다음에는 세부 사항을 살펴볼 수 있습니다.  이 항목의 나머지 부분에 나오는 절차는 [열 목록](#_core_lists_of_columns)에서 소개한 목록을 만드는 방법을 보여 줍니다.  이 절차에서는 다음과 같은 과정에 대해 설명합니다.  
  
-   [레코드 집합에 없는 열 이름 확인](#_core_determining_which_table_columns_are_not_in_your_recordset)  
  
-   [테이블에 새로 추가된 열에 동적 저장소 제공](#_core_providing_storage_for_the_new_columns)  
  
-   [동적으로 새 열에 대한 RFX 호출 추가](#_core_adding_rfx_calls_to_bind_the_columns)  
  
###  <a name="_core_determining_which_table_columns_are_not_in_your_recordset"></a> 레코드 집합에 없는 테이블 열 확인  
 주 레코드 집합에 있는 이미 바인딩된 열 목록을 포함하는 목록\([그림](#_core_illustration_dynamic)의 목록 2와 같은 Bound\-Recordset\-Columns\)을 만듭니다.  그런 다음 주 레코드 집합에는 없고 데이터 소스의 테이블에는 있는 열 이름을 포함하는 목록\(Current\-Table\-Columns 및 Bound\-Recordset\-Columns에서 파생된 Columns\-to\-Bind\-Dynamically\)을 만듭니다.  
  
##### 레코드 집합에 없는 열 이름\(Columns\-to\-Bind\-Dynamically\)을 확인하려면  
  
1.  주 레코드 집합에 있는 이미 바인딩된 열 목록\(Bound\-Recordset\-Columns\)을 만듭니다.  
  
     이렇게 하려면 디자인 타임에 Bound\-Recordset\-Columns를 만듭니다.  레코드 집합의 `DoFieldExchange`함수에서 RFX 함수 호출을 검사하여 이러한 열의 이름을 얻을 수 있습니다.  그런 다음 해당 이름으로 초기화된 배열로 목록을 설정합니다.  
  
     예를 들어 세 요소를 포함하는 Bound\-Recordset\-Columns\(목록 2\)가 [그림](#_core_illustration_dynamic)에 표시되어 있습니다.  Bound\-Recordset\-Columns에는 Current\-Table\-Columns\(목록 1\)에 나타난 Phone 열이 없습니다.  
  
2.  Current\-Table\-Columns와 Bound\-Recordset\-Columns를 비교하여 주 레코드 집합에 있는 아직 바인딩되지 않은 열 목록\(Columns\-to\-Bind\-Dynamically\)을 만듭니다.  
  
     이렇게 하려면 런타임에 테이블에 있는 열의 목록\(Current\-Table\-Columns\) 및 레코드 집합에 있는 이미 바인딩된 열 목록\(Bound\-Recordset\-Columns\)을 병렬로 전체 반복합니다.  Current\-Table\-Columns에는 있지만 Bound\-Recordset\-Columns에는 없는 모든 이름을 Columns\-to\-Bind\-Dynamically에 넣습니다.  
  
     예를 들어 [그림](#_core_illustration_dynamic)의 Current\-Table\-Columns\(목록 1\)에는 있지만 Bound\-Recordset\-Columns\(목록 2\)에는 없는 요소인 Phone 열을 포함하는 Columns\-to\-Bind\-Dynamically\(목록 3\)가 표시되어 있습니다.  
  
3.  [그림](#_core_illustration_dynamic)의 목록 4와 같은 Dynamic\-Column\-Values 목록을 만듭니다. 이 목록에는 동적으로 바인딩할 열의 목록\(Columns\-to\-Bind\-Dynamically\)에 저장된 각 열 이름에 해당하는 데이터 값이 저장됩니다.  
  
     이 목록의 요소는 새 레코드 집합 필드 데이터 멤버의 역할을 하며  동적 열이 바인딩될 저장 위치입니다.  목록에 대한 설명은 [열 목록](#_core_lists_of_columns)을 참조하십시오.  
  
###  <a name="_core_providing_storage_for_the_new_columns"></a> 새 열을 위한 저장소 제공  
 다음으로 동적으로 바인딩될 열의 저장 위치를 설정합니다.  이렇게 하면 각 열 값을 저장할 목록 요소가 만들어집니다.  이러한 저장 위치는 일반적으로 바인딩된 열을 저장하는 레코드 집합 멤버 변수와 상응합니다.  
  
##### 새 열이 저장될 동적 저장소\(Dynamic\-Column\-Values\)를 제공하려면  
  
1.  각 열의 데이터 값을 포함하기 위해 Columns\-to\-Bind\-Dynamically에 상응하는 Dynamic\-Column\-Values를 만듭니다.  
  
     예를 들어 [그림](#_core_illustration_dynamic)에는 Dynamic\-Column\-Values\(목록 4\) 목록이 표시되어 있습니다. 이 목록에는 현재 레코드에 대한 실제 전화 번호인 "555\-1212"가 들어 있는 `CString` 개체가 포함됩니다.  
  
     대개 Dynamic\-Column\-Values는 `CString`형식의 요소를 포함합니다.  열의 데이터 형식이 가변적이면 다양한 형식의 요소를 포함할 수 있는 목록이 필요합니다.  
  
 위의 절차를 수행하고 나면 열 이름을 포함하는 Columns\-to\-Bind\-Dynamically, 현재 레코드의 열 값을 포함하는 Dynamic\-Column\-Values 등 두 개의 주 목록이 생성됩니다.  
  
> [!TIP]
>  새 열의 데이터 형식이 모두 동일하지 않은 경우 열 목록에 있는 각 해당 요소의 형식을 정의하는 항목을 포함하는 추가 병렬 목록을 사용할 수도 있습니다. 필요한 경우 **AFX\_RFX\_BOOL**, **AFX\_RFX\_BYTE** 등의 값을 이 목적에 사용할 수 있습니다.  이러한 상수는 AFXDB.H 파일에 정의되어 있습니다. 열 데이터 형식을 표시하는 방법에 따라 목록 형식을 선택합니다.  
  
###  <a name="_core_adding_rfx_calls_to_bind_the_columns"></a> 열 바인딩을 위한 RFX 호출 추가  
 마지막으로 `DoFieldExchange` 함수에 새 열에 대한 RFX 호출을 추가하여 동적 바인딩을 준비합니다.  
  
##### 동적으로 새 열에 대한 RFX 호출을 추가하려면  
  
1.  새 열 목록\(Columns\-to\-Bind\-Dynamically\)을 전체 반복하는 코드를 주 레코드 집합의 `DoFieldExchange` 멤버 함수에 추가합니다.  각 루프에서, Columns\-to\-Bind\-Dynamically에서 열 이름을 추출하고 Dynamic\-Column\-Values에서 열의 결과 값을 추출합니다.  이 항목들을 열의 데이터 형식에 적합한 RFX 함수 호출에 전달합니다.  목록에 대한 설명은 [열 목록](#_core_lists_of_columns)을 참조하십시오.  
  
 일반적으로 다음 코드와 같이 `RFX_Text` 함수를 호출하여 목록에서 `CString` 개체를 추출합니다. 이 코드에서 Columns\-to\-Bind\-Dynamically는 `m_listName`이라는 `CStringList`이고 Dynamic\-Column\-Values는 `m_listValue`라는 `CStringList`입니다.  
  
```  
RFX_Text( pFX,   
            m_listName.GetNext( posName ),   
            m_listValue.GetNext( posValue ));  
```  
  
 RFX 함수에 대한 자세한 내용은 클래스 라이브러리 참조의 [Macros and Globals](../../mfc/reference/mfc-macros-and-globals.md)을 참조하십시오.  
  
> [!TIP]
>  새 열이 다른 데이터 형식이면 루프에서 switch 문을 사용하여 각 형식에 적합한 RFX 함수를 호출합니다.  
  
 **Open** 프로세스 동안 프레임워크가 `DoFieldExchange`를 호출하여 열을 레코드 집합에 바인딩하면 정적 열에 대한 RFX 호출은 이 열을 바인딩합니다.  루프가 실행되면서 동적 열에 대한 RFX 함수가 반복해서 호출됩니다.  
  
## 참고 항목  
 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 대형 데이터 항목 작업\(ODBC\)](../../data/odbc/recordset-working-with-large-data-items-odbc.md)