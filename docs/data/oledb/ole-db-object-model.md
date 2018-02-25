---
title: "OLE DB 개체 모델 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- rowsets, OLE DB object model
- OLE DB, object model
ms.assetid: 1a274a25-c310-4430-a1ec-bd2bd8120eff
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2cd8fb90b7418b45f6bc011e8d4d0db6e04c08df
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="ole-db-object-model"></a>OLE DB 개체 모델
OLE DB 개체 모델에는 다음 개체 또는 구성 요소 구성 됩니다. 처음 4 개의 개체나 나열 된 구성 요소 (데이터 원본, 세션, 명령 및 행 집합) 데이터 원본에 연결 하 고 볼 수 있도록 합니다. 접근자 이하의 나머지 표시 되 면 데이터 작업과 관련이 있습니다.  
  
## <a name="data-sources"></a>데이터 소스  
 데이터 원본 개체를 사용 하는 파일 또는 DBMS 같은 데이터 원본에 연결할 수 있습니다. 데이터 원본 개체 및 연결 관리 만들고 권한 및 인증 정보 (예: 로그인 이름 및 암호)를 포함 합니다. 데이터 원본 개체를 하나 이상의 세션을 만들 수 있습니다.  
  
## <a name="sessions"></a>세션  
 세션을 쿼리하고 데이터를 검색 하도록 데이터 소스와 특정 상호 작용을 관리 합니다. 각 세션은 단일 트랜잭션으로 합니다. 트랜잭션은은 ACID 테스트에 의해 정의 나눌 수 없는 작업 단위입니다. ACID의 정의 참조 하십시오. [트랜잭션을](#vcconoledbcomponents_transactions)합니다.  
  
 세션을 만든 데이터 원본 개체를 반환 하 고 행 집합 열기 등의 중요 한 작업을 수행 합니다. 세션 메타 데이터 또는 (예: 테이블 정보) 데이터 원본 자체에 대 한 정보를 반환할 수도 있습니다.  
  
 세션에는 하나 이상의 명령을 만들 수 있습니다.  
  
## <a name="commands"></a>명령  
 명령에는 SQL 문 처럼 텍스트 명령을 실행 합니다. 텍스트 명령 SQL 같은 행 집합을 지정 하는 경우 **선택** 문, 명령 행 집합을 만듭니다.  
  
 명령이 컨테이너 텍스트 명령 실행에서에서 전달 된 소비자 데이터 원본 개체에 의해 공급자의 기본 데이터 저장소 (예: SQL 문)는 문자열입니다. 일반적으로 텍스트 명령을 SQL **선택** 문 (때문에 경우 SQL **선택** 행 집합을 지정 명령을 행 집합을 자동으로 생성).  
  
## <a name="rowsets"></a>행 집합  
 행 집합 테이블 형식으로 데이터를 노출 합니다. 인덱스는 행 집합의 특수 한 경우. 세션 또는 명령에서 행 집합을 만들 수 있습니다.  
  
### <a name="schema-rowsets"></a>스키마 행 집합  
 스키마는 데이터베이스에 대 한 메타 데이터 (구조 정보)를 포함합니다. 스키마 행 집합은 스키마 정보를 포함 하는 행 집합입니다. DBMS에 대 한 일부 OLE DB 공급자 스키마 행 집합 개체를 지원 합니다. 스키마 행 집합에 대 한 자세한 내용은 참조 [스키마 행 집합 메타 데이터 구하기](../../data/oledb/obtaining-metadata-with-schema-rowsets.md) 및 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)합니다.  
  
### <a name="view-objects"></a>개체 보기  
 View 개체의 행과 행 집합에서 열 하위 집합을 정의합니다. 자체의 데이터가 없습니다. 뷰 개체는 여러 행 집합의 데이터를 결합할 수 없습니다.  
  
## <a name="accessors"></a>접근자  
 OLE DB만 접근자의 개념을 사용합니다. 접근자를 소비자에 데이터가 저장 되는 방법을 설명 합니다. 행 집합 필드 (열)와 소비자에서 선언 하는 데이터 멤버 (열 지도)는 바인딩 집합을 포함 합니다.  
  
##  <a name="vcconoledbcomponents_transactions"></a> 트랜잭션  
 트랜잭션 개체 커밋하거나 최하위 수준이 아닌 수준에서 중첩 된 트랜잭션을 중단할 때 사용 됩니다. 트랜잭션은은 ACID 테스트에 의해 정의 나눌 수 없는 작업 단위입니다. ACID를 나타냅니다.  
  
-   원자성: 더 작은 작업 단위로 나눌 수 없습니다.  
  
-   동시성: 한 번에 둘 이상의 트랜잭션이 발생할 수 있습니다.  
  
-   격리: 한 트랜잭션이 다른 변경에 대 한 지식을 제한 됩니다.  
  
-   내구성: 트랜잭션이 영구적으로 변경 하면 있습니다.  
  
## <a name="enumerators"></a>열거자  
 열거자는 사용 가능한 데이터 원본 및 기타 열거자에 대 한 검색합니다. 소비자는 특정 데이터 원본에 대 한 사용자 지정 되지 않은 열거자를 사용 하 여 사용할 데이터 원본을 검색 합니다.  
  
 Microsoft Data Access SDK에서 제공 하는 루트 열거자는 데이터 원본 및 다른 열거자를 찾고 레지스트리를 통과 합니다. 다른 표시기는 공급자 특정 방식으로 레지스트리 또는 검색을 통과 합니다.  
  
## <a name="errors"></a>오류  
 모든 OLE DB 개체에서 모든 인터페이스에는 오류가 발생할 수 있습니다. 오류는 필요에 따라 사용자 지정 오류 개체를 포함 한 오류에 대 한 추가 정보를 포함 합니다. 이 정보는 HRESULT 값에 포함 됩니다.  
  
## <a name="notifications"></a>알림  
 알림 (여기서 공유 경우 소비자가 동일한 트랜잭션 내에서 작동 가정 됩니다) 행 집합을 공유 하는 기업 소비자 그룹이 사용 됩니다. 알림을 사용 수행한 행 집합에 대 한 작업에 대 한 알림을 받을 기업 소비자 행 집합을 공유 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 프로그래밍](../../data/oledb/ole-db-programming.md)   
 [OLE DB 프로그래밍 개요](../../data/oledb/ole-db-programming-overview.md)