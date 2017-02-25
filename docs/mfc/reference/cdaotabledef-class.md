---
title: "CDaoTableDef Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoTableDef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoTableDef class"
  - "데이터베이스 클래스[C++], DAO"
  - "database tables [C++], attached table definition"
  - "database tables [C++], base table definition"
  - "tabledefs [C++]"
ms.assetid: 7c5d2254-8475-43c4-8a6c-2d32ead194c9
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CDaoTableDef Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본 테이블 또는 연결된 된 테이블의 저장 된 정의 나타냅니다.  
  
## 구문  
  
```  
class CDaoTableDef : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDaoTableDef::CDaoTableDef](../Topic/CDaoTableDef::CDaoTableDef.md)|생성 된  **CDaoTableDef**  개체입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDaoTableDef::Append](../Topic/CDaoTableDef::Append.md)|데이터베이스에 새 테이블을 추가합니다.|  
|[CDaoTableDef::CanUpdate](../Topic/CDaoTableDef::CanUpdate.md)|테이블을 업데이트할 수 있는 경우에 0이 아닌 반환 \(정의의 필드 또는 테이블 속성을 수정할 수 있습니다\).|  
|[CDaoTableDef::Close](../Topic/CDaoTableDef::Close.md)|열려 있는 tabledef를 닫습니다.|  
|[CDaoTableDef::Create](../Topic/CDaoTableDef::Create.md)|사용 하 여 데이터베이스에 추가할 수 있는 테이블을 만들고  [추가](../Topic/CDaoTableDef::Append.md).|  
|[CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md)|테이블 필드를 만들기 위해 호출 됩니다.|  
|[CDaoTableDef::CreateIndex](../Topic/CDaoTableDef::CreateIndex.md)|테이블 인덱스를 만들기 위해 호출 됩니다.|  
|[CDaoTableDef::DeleteField](../Topic/CDaoTableDef::DeleteField.md)|테이블에서 필드를 삭제 하기 위해 호출 됩니다.|  
|[CDaoTableDef::DeleteIndex](../Topic/CDaoTableDef::DeleteIndex.md)|테이블에서 인덱스를 삭제 하기 위해 호출 됩니다.|  
|[CDaoTableDef::GetAttributes](../Topic/CDaoTableDef::GetAttributes.md)|하나 이상의 특성을 나타내는 값을 반환 된 `CDaoTableDef` 개체입니다.|  
|[CDaoTableDef::GetConnect](../Topic/CDaoTableDef::GetConnect.md)|원본 테이블에 대 한 정보를 제공 하는 값을 반환 합니다.|  
|[CDaoTableDef::GetDateCreated](../Topic/CDaoTableDef::GetDateCreated.md)|기본 테이블의 기본 날짜 및 시간을 반환은 `CDaoTableDef` 개체를 만들었습니다.|  
|[CDaoTableDef::GetDateLastUpdated](../Topic/CDaoTableDef::GetDateLastUpdated.md)|기본 테이블의 디자인에 가장 최근 변경 시간과 날짜를 반환 합니다.|  
|[CDaoTableDef::GetFieldCount](../Topic/CDaoTableDef::GetFieldCount.md)|테이블의 필드 수를 나타내는 값을 반환 합니다.|  
|[CDaoTableDef::GetFieldInfo](../Topic/CDaoTableDef::GetFieldInfo.md)|테이블에서 특정 종류의 필드에 대 한 정보를 반환합니다.|  
|[CDaoTableDef::GetIndexCount](../Topic/CDaoTableDef::GetIndexCount.md)|테이블의 인덱스를 반환합니다.|  
|[CDaoTableDef::GetIndexInfo](../Topic/CDaoTableDef::GetIndexInfo.md)|특정 종류의 인덱스는 테이블에 대 한 정보를 반환합니다.|  
|[CDaoTableDef::GetName](../Topic/CDaoTableDef::GetName.md)|테이블의 사용자 정의 이름을 반환합니다.|  
|[CDaoTableDef::GetRecordCount](../Topic/CDaoTableDef::GetRecordCount.md)|테이블의 레코드 개수를 반환합니다.|  
|[CDaoTableDef::GetSourceTableName](../Topic/CDaoTableDef::GetSourceTableName.md)|원본 데이터베이스에 연결 된 테이블의 이름을 지정 하는 값을 반환 합니다.|  
|[CDaoTableDef::GetValidationRule](../Topic/CDaoTableDef::GetValidationRule.md)|변경 되거나 테이블에 추가 되는 데이터 필드의 유효성을 검사 하는 값을 반환 합니다.|  
|[CDaoTableDef::GetValidationText](../Topic/CDaoTableDef::GetValidationText.md)|Field 개체의 값은 지정 된 유효성 검사 규칙에 맞지 않는 경우 응용 프로그램을 표시 하는 메시지의 텍스트를 지정 하는 값을 반환 합니다.|  
|[CDaoTableDef::IsOpen](../Topic/CDaoTableDef::IsOpen.md)|연 표의 경우 0이 아닌 반환 합니다.|  
|[CDaoTableDef::Open](../Topic/CDaoTableDef::Open.md)|데이터베이스에서 기존 테이블 정의 저장 하는 열의 테이블 정의 컬렉션입니다.|  
|[CDaoTableDef::RefreshLink](../Topic/CDaoTableDef::RefreshLink.md)|연결된 된 테이블에 대 한 연결 정보를 업데이트합니다.|  
|[CDaoTableDef::SetAttributes](../Topic/CDaoTableDef::SetAttributes.md)|하나 이상의 특성을 나타내는 값을 설정는 `CDaoTableDef` 개체입니다.|  
|[CDaoTableDef::SetConnect](../Topic/CDaoTableDef::SetConnect.md)|원본 테이블에 대 한 정보를 제공 하는 값을 설정 합니다.|  
|[CDaoTableDef::SetName](../Topic/CDaoTableDef::SetName.md)|테이블의 이름을 설정 합니다.|  
|[CDaoTableDef::SetSourceTableName](../Topic/CDaoTableDef::SetSourceTableName.md)|원본 데이터베이스에 연결된 된 테이블의 이름을 지정 하는 값을 설정 합니다.|  
|[CDaoTableDef::SetValidationRule](../Topic/CDaoTableDef::SetValidationRule.md)|변경 되거나 테이블에 추가 되는 데이터 필드의 유효성을 검사 하는 값을 설정 합니다.|  
|[CDaoTableDef::SetValidationText](../Topic/CDaoTableDef::SetValidationText.md)|Field 개체의 값은 지정 된 유효성 검사 규칙에 맞지 않는 경우 응용 프로그램을 표시 하는 메시지의 텍스트를 지정 하는 값을 설정 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CDaoTableDef::m\_pDAOTableDef](../Topic/CDaoTableDef::m_pDAOTableDef.md)|테이블 정의 개체를 원본으로 사용 하는 DAO 인터페이스 포인터입니다.|  
|[CDaoTableDef::m\_pDatabase](../Topic/CDaoTableDef::m_pDatabase.md)|이 테이블에 대 한 원본 데이터베이스입니다.|  
  
## 설명  
 각 DAO 데이터베이스 개체 저장 된 DAO 테이블 정의 개체를 포함 하는 테이블 정의 라는 컬렉션을 유지 관리 합니다.  
  
 사용 하 여 테이블 정의 조작할는 `CDaoTableDef` 개체입니다.  예를 들어, 다음을 수행할 수 있습니다.  
  
-   로컬 연결 된, 또는 외부 데이터베이스에서 테이블의 필드 및 인덱스 구조를 검사 합니다.  
  
-   호출을 `SetConnect` 및 `SetSourceTableName` 멤버 함수를 사용 하 고 연결 된 테이블에는 `RefreshLink` 멤버 함수에 대 한 연결을 업데이트할 연결 테이블.  
  
-   호출 하는 `CanUpdate` 멤버 함수는 테이블에서 필드 정의 편집할 수 있는지 확인 합니다.  
  
-   Get 또는 set을 사용 하 여 유효성 검사 조건을 `GetValidationRule` 및 `SetValidationRule`, 및 `GetValidationText` 및 `SetValidationText` 멤버 함수입니다.  
  
-   사용 된  **열려** 멤버 함수는 테이블, 다이너셋 또는 스냅숏 형식 만들기 `CDaoRecordset` 개체.  
  
    > [!NOTE]
    >  DAO 데이터베이스 클래스는 개방형 데이터베이스 연결 \(ODBC\)에 따라 MFC 데이터베이스 클래스와는 별개입니다.  모든 DAO 데이터베이스 클래스 이름을 "CDao" 접두사가 있습니다.  여전히 DAO 클래스가 ODBC 데이터 소스를 액세스 할 수 있습니다. DAO 클래스 이므로 Microsoft Jet 데이터베이스 엔진에 특정 일반적으로 탁월한 능력을 제공 합니다.  
  
### 작업으로 기존 테이블 또는 새 테이블을 만들려면 테이블 정의 개체를 사용.  
  
1.  먼저 모든 경우에 구성에 `CDaoTableDef` 개체에 대 한 포인터를 제공 하는  [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체 테이블에 속한.  
  
2.  다음 따라 다음을 수행 합니다.  
  
    -   기존 테이블에 저장을 사용 하는 tabledef 개체 호출  [열려](../Topic/CDaoTableDef::Open.md) 멤버 함수, 저장 된 테이블의 이름을 제공 합니다.  
  
    -   새 테이블을 만들려면 테이블 정의 개체를 호출 합니다.  [만들기](../Topic/CDaoTableDef::Create.md) 멤버 함수를 제공 하는 테이블의 이름입니다.  호출  [CreateField](../Topic/CDaoTableDef::CreateField.md) 및  [CreateIndex](../Topic/CDaoTableDef::CreateIndex.md) 테이블에 필드와 인덱스를 추가 합니다.  
  
    -   호출  [추가](../Topic/CDaoTableDef::Append.md) 데이터베이스의 TableDefs 컬렉션에 추가 하 여 테이블을 저장 합니다.  **만들기** 테이블 정의 열린 상태로 전환 후 전화 등  **만들기** 호출 하지 않아야  **열**.  
  
        > [!TIP]
        >  저장 된 테이블을 만들 수 만들 수 있고 Microsoft Access를 사용 하 여 데이터베이스에 저장할 수 있습니다.  다음 열 및 MFC 코드를 사용 하 여 수 있습니다.  
  
 열거나 만든 tabledef 개체를 사용 하려면 만들기 및 열기는 `CDaoRecordset` 개체를 테이블 정의의 이름을 지정 하는  **dbOpenTable** 값은 `nOpenType` 매개 변수.  
  
 Tabledef 개체를 사용 하 여 만드는 `CDaoRecordset` 개체에서 일반적으로 만드는 또는 위 설명 처럼 테이블 정의 열기 하면 레코드 집합 개체를 호출 하면 tabledef 개체에 포인터를 전달 구성  [CDaoRecordset::Open](../Topic/CDaoRecordset::Open.md).  전달 테이블 정의 열린 상태 여야 합니다.  자세한 내용은 클래스를 참조 하십시오.  [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 Tabledef 개체를 사용 하 여 완료 되 면 호출의  [닫기](../Topic/CDaoRecordset::Close.md) 멤버 함수입니다. 다음 테이블 정의 개체를 파괴 하십시오.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoTableDef`  
  
## 요구 사항  
 **헤더:**  afxdao.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset Class](../../mfc/reference/cdaorecordset-class.md)