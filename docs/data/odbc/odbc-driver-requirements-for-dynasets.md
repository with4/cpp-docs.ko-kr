---
title: 다이너셋에 대 한 ODBC 드라이버 요구 사항 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets, dynasets
- drivers, for dynasets
- drivers, ODBC
- recordsets, dynasets
- dynasets
- ODBC drivers, dynasets
ms.assetid: 585cc67b-4d92-404b-9903-d769cd17badc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d9fad26440cea2c8ec2efd7d07dacb83547252e3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="odbc-driver-requirements-for-dynasets"></a>다이너셋에 대한 ODBC 드라이버 요구 사항
MFC ODBC 데이터베이스 클래스에서 다이너셋 되 고 동적 속성을 갖는 레코드 집합 다양 한 방식으로 데이터 소스와 동기화 상태로 남아 있습니다. MFC 다이너셋 (그러나 정방향 전용 레코드 집합)에 수준 2 API 규칙을 따르는 한 ODBC 드라이버가 필요 합니다. 경우에 대 한 드라이버 프로그램 [데이터 원본](../../data/odbc/data-source-odbc.md) 수준 1 API를 준수 설정, 있습니다 사용할 수 모두 업데이트 가능 하 고 읽기 전용 스냅숏 및 앞 으로만 이동 가능한 레코드 집합 있지만 다이너셋 되지 않습니다. 그러나 확장된 fetch와 키 집합 커서를 지 원하는 경우 수준 1 드라이버 다이너셋을 지원할 수 있습니다.  
  
 ODBC 용어로 다이너셋 및 스냅숏을 라고 커서입니다. 커서는 한 레코드 집합에서의 위치를 추적에 사용 되는 메커니즘입니다. 다이너셋에 대 한 드라이버 요구 사항에 대 한 자세한 내용은 참조 [다이너셋](../../data/odbc/dynaset.md)합니다. 커서에 대 한 자세한 내용은 참조는 [ODBC Open Database Connectivity ()](https://msdn.microsoft.com/en-us/library/ms710252.aspx) MSDN 설명서에서 SDK입니다.  
  
> [!NOTE]
>  업데이트 가능한 레코드 집합에 대 한 ODBC 드라이버가 위치 지정된 update 문 중 하나를 지원 해야 합니다 또는 **:: SQLSetPos** ODBC API 함수입니다. MFC를 사용 하는 둘 다 지 원하는 경우 **:: SQLSetPos** 효율성에 대 한 합니다. 또는, 스냅숏에 대 한 스냅숏을 업데이트할 수 (정적 커서 및 위치 지정된 update 문)에 대 한 필요한 지원을 제공 하는 커서 라이브러리를 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [ODBC 기본 사항](../../data/odbc/odbc-basics.md)