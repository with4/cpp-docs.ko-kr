---
title: 명령 및 테이블 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates, table support
- CCommand class, OLE DB consumer templates
- commands [C++], OLE DB Consumer Templates
- CTable class
- CAccessorRowset class, command and table classes
- rowsets, accessing
- tables [C++], OLE DB Consumer Templates
- OLE DB consumer templates, command support
ms.assetid: 4bd3787b-6d26-40a9-be0c-083080537c12
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 23d2739807a065b93b10a209a9ea68070b36970b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098682"
---
# <a name="commands-and-tables"></a>명령 및 테이블
명령 및 테이블에 액세스할 수 있도록 행 집합입니다. 즉, 행 집합을 열고 명령을 실행 하 고 열을 바인딩하십시오. [CCommand](../../data/oledb/ccommand-class.md) 및 [CTable](../../data/oledb/ctable-class.md) 클래스 각각 명령 및 테이블 개체를 인스턴스화합니다. 이러한 클래스에서 파생 [CAccessorRowset](../../data/oledb/caccessorrowset-class.md) 다음 그림에 나와 있는 것 처럼 합니다.  
  
 ![CCommand 및 CTable](../../data/oledb/media/vccommandstables.gif "vccommandstables")  
명령 및 테이블 클래스  
  
 앞의 표에 `TAccessor` 모든 접근자 형식이에 속할 수 있습니다 [접근자 형식](../../data/oledb/accessors-and-rowsets.md)합니다. *TRowset* 모든 행 집합 형식에 있는 [행 집합 형식](../../data/oledb/accessors-and-rowsets.md)합니다. *TMultiple* (단일 또는 여러 결과 집합) 결과 유형을 지정 합니다.  
  
 [ATL OLE DB 소비자 마법사](../../atl/reference/atl-ole-db-consumer-wizard.md) 명령 또는 테이블 개체를 사용할지를 지정할 수 있습니다.  
  
-   명령이 없는 데이터 원본에 대해 사용할 수 있습니다는 `CTable` 클래스입니다. 일반적으로 사용할 있습니다 매개 변수를 지정 하 고 여러 없는 결과 필요로 하는 단순 행 집합에 대 한. 이 간단한 클래스 지정 하는 테이블 이름을 사용 하 여 데이터 원본에서 테이블을 엽니다.  
  
-   명령을 지 원하는 데이터 원본에 사용할 수 있습니다는 `CCommand` 클래스를 대신 합니다. 명령을 실행 하려면 호출 [열려](../../data/oledb/ccommand-open.md) 이 클래스에 있습니다. 호출할 수 있습니다 `Prepare` 두 번 이상 실행할 명령을 준비를 합니다.  
  
     **CCommand** 세 개의 템플릿 인수가: 접근자 유형이, 집합 형식 및 결과 형식 (`CNoMultipleResults`, 기본적으로 또는 `CMultipleResults`). 지정 하는 경우 `CMultipleResults`, `CCommand` 클래스는 지원의 **IMultipleResults** 인터페이스 하 고 여러 행 집합을 처리 합니다. [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832) 샘플에서는 여러 개의 결과 처리 하는 방법을 보여 줍니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)