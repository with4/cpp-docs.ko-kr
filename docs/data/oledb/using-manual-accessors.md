---
title: 수동 접근자 사용 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- command handling, OLE DB Templates
- manual accessors
- accessors [C++], manual
ms.assetid: 29f00a89-0240-482b-8413-4120b9644672
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 236fd1809fa012262f3a98f0f1856f3bbff6b454
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340866"
---
# <a name="using-manual-accessors"></a>수동 접근자 사용
알 수 없는 명령을 처리 하는 경우 수행할 작업에 다음과 같은 4 가지 있습니다.  
  
-   매개 변수 확인  
  
-   명령을 실행 합니다.  
  
-   출력 열 확인  
  
-   여러 행 집합을 반환 하는 경우 확인  
  
 OLE DB 소비자 템플릿을 사용 하 여이 작업을 수행 하려면 사용 된 `CManualAccessor` 클래스 및 다음이 단계를 수행 합니다.  
  
1.  엽니다는 `CCommand` 개체를 `CManualAccessor` 템플릿 매개 변수로 합니다.  
  
    ```cpp  
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;  
    ```  
  
2.  세션에 대 한 쿼리는 `IDBSchemaRowset` 인터페이스 및 프로시저 매개 변수 행 집합을 사용 합니다. 경우는 `IDBSchemaRowset` 인터페이스를 사용할 수 없는 쿼리는 `ICommandWithParameters` 인터페이스입니다. 호출 `GetParameterInfo` 정보에 대 한 합니다. 두 인터페이스 모두를 사용할 수 있는 경우 매개 변수가 없는 가정할 수 있습니다.  
  
3.  각 매개 변수에 대 한 호출 `AddParameterEntry` 매개 변수를 추가 하 여 설정 합니다.  
  
4.  열지만 바인딩 매개 변수를 설정 **false**합니다.  
  
5.  호출 `GetColumnInfo` 에 출력 열을 검색 합니다. 사용 하 여 `AddBindEntry` 바인딩에 출력 열을 추가 합니다.  
  
6.  호출 `GetNextResult` 행 집합이 더 이상 사용할 수 있는 되는지 확인할 수 있습니다. 2 ~ 5 단계를 반복 합니다.  
  
 수동 접근자의 예제를 보려면 `CDBListView::CallProcedure` 에 [DBVIEWER](http://msdn.microsoft.com/07620f99-c347-4d09-9ebc-2459e8049832) 샘플입니다.  
  
## <a name="see-also"></a>참고 항목  
 [접근자 사용](../../data/oledb/using-accessors.md)