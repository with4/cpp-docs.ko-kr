---
title: OLE DB에서 트랜잭션 지원 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates [C++], transaction support
- transactions [C++], OLE DB support for
- nested transactions [C++]
- OLE DB [C++], transaction support
- databases [C++], transactions
- distributed transactions [C++]
ms.assetid: 3d72e583-ad38-42ff-8f11-e2166d60a5a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ecd5b7274e62508289a83d6c0420d5f76e239e4d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="supporting-transactions-in-ole-db"></a>OLE DB에서 트랜잭션 지원
A [트랜잭션](../../data/transactions-mfc-data-access.md) 그룹 또는 일괄 처리는 일련의 데이터 원본에 대 한 업데이트 커밋되지 않으며 (경우 중 하나라도 실패할) 또는 실패 하 고 한 번에 커밋됩니다 모든 되도록 하는 방법 및 전체 트랜잭션이 롤백됩니다. 이 프로세스는 데이터 원본에 대 한 결과의 무결성을 보장 합니다.  
  
 OLE DB는 다음과 같은 세 가지 방법을 사용 하 여 트랜잭션을 지원합니다.  
  
-   [ITransactionLocal::StartTransaction](https://msdn.microsoft.com/en-us/library/ms709786.aspx)  
  
-   [ITransaction::Commit](https://msdn.microsoft.com/en-us/library/ms713008.aspx)  
  
-   [ITransaction::Abort](https://msdn.microsoft.com/en-us/library/ms709833.aspx)  
  
## <a name="relationship-of-sessions-and-transactions"></a>세션 및 트랜잭션이의 관계  
 단일 데이터 원본 개체 내부 또는 지정된 된 시간에는 트랜잭션의 범위 외부 수는 각각 하나 이상의 세션 개체를 만들 수 있습니다.  
  
 세션 트랜잭션이 입력 하지 않는 각 메서드 호출에서 데이터 저장소에서 해당 세션 내에서 수행 하는 작업을 즉시 커밋됩니다. (이것은 라고도 암시적 모드나 자동 커밋 모드입니다.)  
  
 세션에 트랜잭션이 들어가면 데이터 저장소에서 해당 세션 내에서 수행 하는 작업을 해당 트랜잭션의 일부인 및 커밋 또는 중단으로 하나의 단위로. (이것은 라고도 수동 커밋 모드입니다.)  
  
 트랜잭션 지원은 공급자별으로 다릅니다. 사용 중인 공급자에서 트랜잭션을 지 원하는 세션 개체를 지원 하면 **ITransaction** 및 **ITransactionLocal** 단순을 입력할 수 있습니다 (즉, 중첩 되지 않은) 트랜잭션. OLE DB 템플릿 클래스 [CSession](../../data/oledb/csession-class.md) 이러한 인터페이스를 지원 하 고 Visual c + +에 트랜잭션 지원을 구현 하는 권장된 방법입니다.  
  
## <a name="starting-and-ending-the-transaction"></a>시작 및 끝 트랜잭션  
 호출 하는 `StartTransaction`, **커밋**, 및 **중단** 소비자에서 행 집합 개체의 메서드.  
  
 호출 **itransactionlocal:: Starttransaction** 새로운 로컬 트랜잭션을 시작 합니다. 트랜잭션을 시작할 때 트랜잭션을 커밋할 때까지 후속 작업에서 수행 된 변경은 실제로 데이터 저장소에 적용 되지 않습니다.  
  
 호출 **itransaction:: Commit** 또는 **itransaction:: Abort** 트랜잭션을 종료 합니다. **커밋** 데이터 저장소에 적용 하는 트랜잭션의 범위 내에서 모든 항목은 변경 합니다. **중단** 트랜잭션이 시작 전의 모든 변경 내용을 취소 해야 하는 트랜잭션 및 데이터 저장소의 범위 내에서 상태로 남아가 원인입니다.  
  
## <a name="nested-transactions"></a>중첩된 트랜잭션  
 A [트랜잭션 중첩](https://msdn.microsoft.com/en-us/library/ms716985.aspx) 세션에 활성 트랜잭션이 이미 있는 경우 새 로컬 트랜잭션을 시작할 때 발생 합니다. 새 트랜잭션은 현재 트랜잭션 아래 중첩된 트랜잭션을으로 시작 됩니다. 공급자는 중첩 된 트랜잭션을 지원 하지 않으면, 호출 `StartTransaction` 세션에 활성 트랜잭션이 이미가 하는 경우 반환 **XACT_E_XTIONEXISTS**합니다.  
  
## <a name="distributed-transactions"></a>분산 트랜잭션  
 분산된 트랜잭션에 분산 된 데이터를 업데이트 하는 트랜잭션을 즉, 둘 이상의 네트워크로 연결 된 컴퓨터 시스템에서 데이터입니다. 분산된 시스템을 통해 트랜잭션을 지원 하려는 경우 OLE DB 트랜잭션 지원이 아닌.NET Framework를 사용 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [접근자 사용](../../data/oledb/using-accessors.md)